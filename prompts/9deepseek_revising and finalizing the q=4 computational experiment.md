You are now revising and finalizing the q=4 computational experiment for the burning-number conjecture.

This is NOT a new search round.

Do NOT move to q=5 yet.
Do NOT attempt to prove the general conjecture.
Do NOT speculate about open status or novelty.

Your task is to:

1. fix the existing q=4 program;
2. make the computation fully reproducible;
3. verify the already-obtained q=4 result;
4. analyze the extremal trees structurally.

---

# 1. Mathematical target

We study the candidate

$$
n_2=2\lceil\sqrt n\rceil-2
\quad\Longrightarrow\quad
b(T)\le\lceil\sqrt n\rceil.
$$

For q=4,

$$
n=q^2=16,
\qquad
n_2=2q-2=6.
$$

The exact question is:

$$
\boxed{
|V(T)|=16,\ n_2=6
\Longrightarrow
b(T)\le4\ ?
}
$$

The previous computation reported:

* total non-isomorphic trees on 16 vertices: 19320;
* trees with exactly 6 degree-2 vertices: 2821;
* 185 trees with \(b(T)=3\);
* 2636 trees with \(b(T)=4\);
* 0 trees with \(b(T)=5\);
* therefore maximum observed burning number = 4.

Treat these numbers as PREVIOUS EXPERIMENTAL RESULTS that must now be independently rechecked by the corrected program.

Do NOT silently assume they are correct.

---

# 2. Fix the implementation first

The previous implementation has a likely issue in the suppressed-core analysis:

after suppressing degree-2 vertices, node labels may no longer be consecutive integers, while `burning_number()` assumes vertices are labeled

$$
0,1,\dots,n-1.
$$

Fix this properly.

For example, relabel the core using:

```python
nx.convert_node_labels_to_integers(H)
```

or otherwise make `burning_number()` label-independent.

Check the entire code for other correctness issues.

Do not merely patch the line and assume the program is correct.

---

# 3. Revalidate the burning-number algorithm

Before running the main q=4 computation, test the exact burning-number implementation independently.

At minimum verify:

$$
b(P_n)=\lceil\sqrt n\rceil
$$

for a reasonable range of small \(n\), and

$$
b(K_{1,m})=2
$$

for \(m\ge2\).

Also test several small trees where the answer can be independently verified by brute force.

Most importantly, verify that the implementation enforces the true temporal condition:

At each round, the new source must be unburned BEFORE it is chosen.

Do not reduce the problem merely to static distance-covering.

Explain why the state transition exactly matches the standard burning process.

---

# 4. Recheck the q=4 exhaustive enumeration

Generate all non-isomorphic trees on 16 vertices.

Verify:

$$
\#\mathcal T_{16}=19320.
$$

Then filter by

$$
n_2=6.
$$

Verify independently:

$$
\#\{T:n=16,n_2=6\}=2821.
$$

Then compute exact burning numbers for all 2821 trees.

Recheck:

$$
N_3=185,\qquad
N_4=2636,\qquad
N_5=0.
$$

If your corrected implementation gives different results, DO NOT force the old numbers.

Report the corrected results and explain the discrepancy.

---

# 5. Identify all extremal trees

Let

$$
b_{\max}=\max\{b(T):|V(T)|=16,\ n_2=6\}.
$$

Identify every isomorphism class attaining \(b_{\max}\).

If there are many, report the exact number and provide several representative examples.

For each representative record:

* edge list;
* degree sequence;
* number of leaves;
* maximum degree;
* diameter;
* radius;
* center (or centers);
* \(b(T)\).

---

# 6. Suppress degree-2 vertices correctly

For every extremal representative, construct the suppressed core \(H\).

Recall:

$$
|V(H)|=16-6=10,
\qquad
|E(H)|=9.
$$

For each extremal tree record:

* adjacency list of H;
* degree sequence of H;
* number of leaves of H;
* maximum degree of H;
* diameter of H;
* radius of H;
* \(b(H)\).

Then compute

$$
\Delta_b=b(T)-b(H).
$$

Do not assume subdivision monotonicity.

This is purely an empirical quantity.

---

# 7. Recover the subdivision data

For each edge \(e\in E(H)\), determine the number

$$
s_e
$$

of degree-2 vertices inserted on that edge in order to reconstruct T.

Verify:

$$
\sum_{e\in E(H)}s_e=6.
$$

Report the subdivision pattern explicitly.

For example, represent it as:

$$
(s_{e_1},s_{e_2},\dots,s_{e_9})
$$

with edges of H clearly identified.

Then classify whether the degree-2 vertices are:

* concentrated on one edge;
* concentrated on a few edges;
* distributed across many edges;
* attached to leaf branches;
* near branching vertices;
* between branching vertices;
* located on a diameter path.

Do not merely describe these qualitatively. Use the actual extremal examples.

---

# 8. Search for structural patterns among extremal examples

Now compare all extremal isomorphism classes.

Determine whether the same structural pattern repeatedly appears.

In particular examine:

### Core structure

* star-like;
* double-star-like;
* path-like;
* caterpillar-like;
* multiple branching vertices.

### Subdivision structure

* one long subdivided edge;
* several moderately subdivided edges;
* subdivision near leaves;
* subdivision near the center;
* subdivision between branching vertices;
* subdivision on diameter paths.

### Global geometry

* large diameter;
* large radius;
* highly centralized;
* highly elongated.

Do NOT turn these observations into theorems.

Use terminology such as:

* "observed pattern";
* "empirical tendency";
* "no clear pattern";
* "suggestive but not proved".

---

# 9. Burning sequence certificates for extremal trees

For representative extremal trees, output an optimal burning sequence.

For example, if

$$
b(T)=4,
$$

give a valid sequence

$$
(v_1,v_2,v_3,v_4)
$$

and explain briefly how it burns the entire tree.

Also verify computationally that no sequence of length 3 exists.

The goal is to make the reported burning number transparent rather than relying entirely on a black-box output.

---

# 10. Important distinction about the q=4 result

The final report MUST make the following logical distinction:

If the exhaustive computation confirms that all 2821 filtered trees satisfy

$$
b(T)\le4,
$$

then we have proved the FINITE CLAIM

$$
\boxed{
|V(T)|=16,\ n_2=6
\Longrightarrow
b(T)\le4
}
$$

by exhaustive computation.

But this does NOT prove

$$
n_2=2\lceil\sqrt n\rceil-2
\Longrightarrow
b(T)\le\lceil\sqrt n\rceil
$$

for arbitrary n.

Do not overstate the result.

---

# 11. Reproducibility

Provide the COMPLETE corrected executable program.

Include:

* Python version;
* NetworkX version;
* installation command;
* execution command;
* expected runtime;
* exact enumeration method;
* exact burning-number algorithm;
* validation procedure.

The code must be self-contained.

Do not give pseudocode.

Do not omit helper functions.

---

# 12. Final report format

Use exactly these sections:

## A. Corrections to the previous implementation

List every bug or weakness you found.

## B. Corrected executable code

Give the complete final source code.

## C. Validation

Give the validation tests and their results.

## D. q=4 exhaustive computation

Report:

$$
19320,\quad 2821,\quad N_3,\quad N_4,\quad N_5,\quad b_{\max}.
$$

Only report numbers actually obtained by running the corrected code.

## E. Extremal tree analysis

Describe the extremal trees, their degree sequences, geometry, cores, and subdivision patterns.

## F. Burning certificates

Give representative optimal burning sequences and explain the minimality check.

## G. Mathematical conclusion

State exactly what the q=4 experiment proves and what it does not prove.

## H. Data for the next research stage

Summarize the most important empirical structural observations that should guide the future q=5/q=6 search.

---

# Strict restrictions

1. Do NOT investigate q=5 yet.
2. Do NOT give a proof of the general conjecture.
3. Do NOT call the conjecture true.
4. Do NOT claim the candidate is a new theorem.
5. Do NOT fabricate computational results.
6. If execution is impossible, clearly say so.
7. Distinguish executed computations from theoretical discussion.
8. Preserve all exact numerical output needed for independent reproduction.

The purpose of this round is to turn the q=4 experiment into a clean, independently reproducible computational result and to extract the actual extremal structures.

Only after this round is completely reliable should we move to q=5.
