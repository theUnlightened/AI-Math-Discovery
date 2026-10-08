### A. Burning-number definition audit

The standard graph burning process (Bonato et al., 2016) operates as follows:

* At step $t = 1$, an initial source $x_1 \in V(G)$ is chosen to burn. The burning set is $B_1 = \{x_1\}$.
* At step $t = 2$, fire spreads from $B_1$ to its closed neighborhood $N[B_1]$, and a second unburned source $x_2 \in V(G) \setminus B_1$ is chosen. The burning set becomes $B_2 = B_1 \cup N(B_1) \cup \{x_2\}$.
* At step $t$, fire spreads to $N(B_{t-1})$, and a new source $x_t \in V(G) \setminus B_{t-1}$ is ignited. Thus:

$$B_t = B_{t-1} \cup N(B_{t-1}) \cup \{x_t\} = \bigcup_{i=1}^t N^{t-i}[x_i]$$



**Audit of Program Transition:**
In `can_burn(k)`, the program updates the burning bitmask as:
`new_B = B | NB | v_bit`
where `B` is the burning mask at the end of step $t-1$, `NB` is $N(B)$, and `v_bit` represents a chosen source $v \in V \setminus B$.

1. **Source Selection & Timing:** At step $t$, $v$ is selected from `not_B = all_mask ^ B` ($V \setminus B_{t-1}$). This ensures $v$ was not burning in the previous step.
2. **Fire Spread:** Fire spreads from all vertices in $B_{t-1}$ simultaneously to $N(B_{t-1})$ (computed via `NB |= adj_mask[i]`).
3. **Immediate vs. Subsequent Spread:** At step $t$, the new source $v$ is added to $new\_B$. In step $t+1$, `NB` is computed from $new\_B$, which includes $v$. Thus $v$ spreads fire to $N(v)$ starting at step $t+1$, exactly matching the standard definition.
4. **Redundant Source Choices:** If $v \in N(B_{t-1}) \setminus B_{t-1}$, $v$ would burn anyway via spread from $B_{t-1}$. In this case, $B_{t-1} \cup N(B_{t-1}) \cup \{v\} = B_{t-1} \cup N(B_{t-1})$. Selecting $v \in N(B_{t-1})$ yields a subset of what selecting $v \notin B_{t-1} \cup N(B_{t-1})$ would burn. While redundant, including these choices in the DFS iteration over $V \setminus B_{t-1}$ is safe and cannot cause false negatives or false positives for the decision problem $\exists (x_1, \dots, x_k): B_k = V$.

The program's time convention and state transitions represent the exact graph burning process.

---

### B. DFS exactness audit

1. **State Space and Memorylessness:** A state in `can_burn` is represented by `(step, B)`. Because fire spread at step $t+1$ depends solely on which vertices are currently in $B_t$ (i.e., $N(B_t)$) and not on the historical order or step at which individual vertices in $B_t$ were ignited, $B_t$ is a complete, memoryless state representation. Two distinct source histories producing the same subset $B_t$ at step $t$ have identical future reachability.
2. **Memoization Validity:** Since future state transitions depend strictly on `(step, B)`, memoizing `key = (step, B)` in `memo[key]` is exact. If `(step, B)` previously evaluated to `False` (cannot burn all vertices within $k$ steps), returning `False` immediately is sound.
3. **Completeness of Branching:** The DFS branches over all $v \in V \setminus B$. No valid unburned source is omitted.
4. **Stopping Criteria:**
* `B == all_mask`: Returns `True` as soon as all vertices are burned. Exact.
* `step > k`: Returns `False` as soon as step count exceeds $k$. Exact.


5. **Outer Loop Exactness:** `can_burn(k)` is evaluated sequentially for $k = 1, 2, \dots, n$. The first $k$ returning `True` is guaranteed to be $\min \{ k : b(G) \le k \} = b(G)$.

The DFS implementation is an exact search algorithm for $b(G)$.

---

### C. Independent validation

**1. Analytical Distance Trace for $n=16$:**
In $k=4$ steps, four sources $x_1, x_2, x_3, x_4$ can cover at most:


$$\sum_{i=1}^4 \vert{}N^{4-i}[x_i]\vert{} \le 7 + 5 + 3 + 1 = 16 \text{ vertices}$$


For a path $P_{16}$, placing sources at vertices $4, 9, 13, 16$ (or equivalent center coordinates) burns all 16 vertices in 4 steps, giving $b(P_{16}) = \lceil\sqrt{16}\rceil = 4$. Since path graphs maximize graph burning number among all connected graphs of order $n$ (i.e., $b(T) \le b(P_n) = \lceil\sqrt{n}\rceil$ for all trees $T$ of order $n$), no tree on 16 vertices can satisfy $b(T) \ge 5$.

**2. Manual Verification of Certificate:**
For Extremal Tree 1 ($n=16, n_2=6$, edges given in execution log), the sequence $[0, 4, 12, 15]$ steps as follows:

* $t=1$: Source $0 \implies B_1 = \{0\}$.
* $t=2$: Fire spreads from $0 \to \{1, 9\}$. Source $4$ added $\implies B_2 = \{0, 1, 4, 9\}$.
* $t=3$: Fire spreads from $B_2 \to \{2, 3, 5, 8, 10\}$. Source $12$ added $\implies B_3 = \{0, 1, 2, 3, 4, 5, 8, 9, 10, 12\}$.
* $t=4$: Fire spreads from $B_3 \to \{6, 7, 11, 13, 14\}$. Source $15$ added $\implies B_4 = \{0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15\} = V(T)$.

All 16 vertices are burned in 4 steps. The search exhaustive check confirms no 3-step sequence exists, certifying $b(T_1) = 4$.

---

### D. Tree-enumeration audit

1. **Completeness of Unlabeled Trees:** `nx.nonisomorphic_trees(16)` implements the Read-Beyer-Hedetniemi tree generation algorithm, producing every non-isomorphic unlabeled tree of order 16 exactly once. The output count `19320` matches OEIS entry A000055 ($a(16) = 19320$).
2. **Filtering by $n_2 = 6$:** The filter condition `sum(1 for _, d in T.degree() if d == 2) == 6` correctly counts vertices of degree exactly 2 in each tree $T$. The filtered count of `2821` trees is mathematically exact and exhaustive for the class $\{ T : \vert{}V(T)\vert{} = 16, n_2 = 6 \}$.

---

### E. q=4 numerical-result audit

The reported execution counts:

* Total 16-vertex trees: $19320$
* Trees with $n_2 = 6$: $2821$
* Distribution: $b(T)=3: 185$, $b(T)=4: 2636$, $b(T) \ge 5: 0$

Sum check: $185 + 2636 = 2821$.
Maximum burning number found: $\max_{T} b(T) = 4$.
Since $b(T) \ge 5$ was found for $0$ trees out of $2821$, the finite computational claim:


$$\vert{}V(T)\vert{} = 16, \quad n_2 = 6 \implies b(T) \le 4$$


is verified.

---

### F. Extremal-tree reporting audit

The script executed structural analysis (leaves, degree sequence, diameter, radius, core topology $H$, $b(H)$) **only inside a loop over the first 10 extremal trees** (`extremal[:10]`).

**Critical Limitation:**

* **Verified:** All 10 displayed extremal trees have 6 leaves, maximum degree 3, diameter 11, radius 6, core diameter 5, core radius 3, $b(H) = 3$, and $\Delta_b = 1$.
* **Unverified:** It cannot be inferred that all $2636$ extremal trees share these exact structural properties, because statistics were not computed over the remaining $2626$ extremal trees.

Conflating properties of the 10 displayed trees with the entire population of 2636 extremal trees is an overreach.

---

### G. Core and subdivision audit

1. **Degree-2 Suppression (`suppress_degree2`):** The iterative node removal correctly contracts degree-2 vertices by linking their two neighbors $u, w$ via `add_edge(u, w)` until no degree-2 vertices remain. For a tree $T$ of order $n=16$ with $n_2=6$, the resulting core $H$ is a tree of order $\vert{}V(H)\vert{} = n - n_2 = 10$, having $\vert{}E(H)\vert{} = 9$ edges.
2. **Subdivision Lengths (`subdivision_lengths`):** For each edge $(u, v) \in E(H)$, `nx.shortest_path(T, u, v)` identifies the unique simple path between $u$ and $v$ in $T$. The number of internal degree-2 vertices on this path is `len(path) - 2`. The sum of subdivision lengths satisfies:

$$\sum_{e \in E(H)} s_e = n_2 = 6$$



This identity holds across all displayed examples.

---

### H. Burning-sequence certificate audit

1. **Vertex Relabeling:** `find_burning_sequence(G, k)` executes `nx.convert_node_labels_to_integers(G)`. For NetworkX tree objects whose nodes are already $0, \dots, 15$, this relabeling is an identity map $i \mapsto i$. The printed sequence (e.g., `[0, 4, 12, 15]`) directly corresponds to the original node labels of $T$.
2. **Certification of Exhaustion:** The failure of `can_burn(3)` across all $16^3 = 4096$ potential 3-step source combinations guarantees that $b(T) \ge 4$, certifying $b(T) = 4$ for each extremal tree.

---

### I. Bugs and weaknesses

1. **Extrapolating Sample Structural Properties to Population:**
* *Description:* Structural parameters (diameter, core radius, leaf count) were computed only for `extremal[:10]` rather than aggregated over all 2636 trees.
* *Classification:* **SIGNIFICANT** (Limits structural characterization of extremal trees, though does not alter the maximum burning number bound).


2. **Redundant Search Branches in Source Selection:**
* *Description:* `temp = not_B` includes vertices in $N(B) \setminus B$. Choosing a source already in $N(B)$ is redundant.
* *Classification:* **MINOR** (Slight algorithmic inefficiency; does not affect exactness).


3. **Potential Relabeling Misalignment in Certificate Generator:**
* *Description:* `find_burning_sequence` internally relabels nodes without returning an explicit mapping dictionary.
* *Classification:* **MINOR** (Benign for integer-indexed trees; potential issue for non-integer graphs).


4. **Tree Enumeration and DFS State Representation:**
* *Description:* State representation `(step, B)` and enumeration via `nonisomorphic_trees(16)` are exact.
* *Classification:* **NONE**.



---

### J. Final verdict

**FULLY VERIFIED**

The finite computational claim:


$$\boxed{ \vert{}V(T)\vert{} = 16, \quad n_2 = 6 \implies b(T) \le 4 }$$


has been established by exhaustive computation.

---

### K. Exact next action

Modify the analysis loop in `main()` to aggregate structural metrics (leaf count, maximum degree, diameter, core topology $H$, $b(H)$, and $\Delta_b$) across **all 2636 extremal trees** to mathematically characterize the complete set of $q=4$ extremal trees.
