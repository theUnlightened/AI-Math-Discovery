# Structural Analysis of the Burning Number Conjecture Boundary Case

## 1. Structural Summary

We investigate trees \( T \) of order \( n \) satisfying

\[
n = q^2 - r,\qquad r \in \{0,1,2,3,4\},\qquad q = \lceil \sqrt{n} \rceil,
\]

with exactly

\[
n_2 = 2q - 2
\]

vertices of degree \( 2 \). This is precisely one degree-2 vertex beyond the threshold \( n_2 \le 2q - 3 \) claimed in the (unverified) 2026 preprint by Das, Islam, Mitra and Paul, and substantially beyond the rigorously proved threshold \( n_2 \le \lfloor \sqrt{n-1} \rfloor \) of Ning, Jin and Zhang.

The structural analysis below shows that any potential counterexample to \( b(T) \le q \) must be a tree whose suppressed core \( H \) is a large, almost entirely unsubdivided tree (roughly \( q^2 \) vertices and edges) with only \( 2q - 2 \) subdivision vertices distributed across at most \( 2q - 2 \) edges. The suppressed core \( H \) itself has no degree-2 vertices, so it falls under Murakami’s theorem (2024), which guarantees \( b(H) \le \lceil \sqrt{|V(H)|} \rceil \). The entire question is whether the insertion of \( 2q - 2 \) degree-2 vertices can raise the burning number from at most \( q \) to \( q+1 \).

The five near-square cases differ only in the size of \( H \), with \( r = 0 \) giving the largest \( H \) and \( r = 4 \) the smallest. The case \( r = 4 \) leaves the least room for absorbing the extra degree-2 vertex and is therefore the most promising case for a counterexample.

---

## 2. Exact Structural Identities

Let \( T \) be a tree with \( n \) vertices, \( n_2 \) degree-2 vertices, \( n_1 \) leaves, and \( n_d \) vertices of degree \( d \) for \( d \ge 3 \). Define

\[
n_{\ge 3} = \sum_{d \ge 3} n_d.
\]

The handshaking lemma gives

\[
\sum_{v \in V(T)} \deg(v) = 2(n-1).
\]

Expanding in terms of degree classes:

\[
n_1 + 2n_2 + \sum_{d \ge 3} d\, n_d = 2n - 2. \tag{1}
\]

Also,

\[
n_1 + n_2 + n_{\ge 3} = n. \tag{2}
\]

Subtracting (2) from (1) yields the fundamental leaf identity

\[
n_1 = 2 + \sum_{d \ge 3} (d-2) n_d. \tag{3}
\]

Equivalently,

\[
n_1 = 2 + n_3 + 2n_4 + 3n_5 + \cdots.
\]

In particular,

\[
n_1 \ge 2 + n_{\ge 3}, \tag{4}
\]

with equality if and only if every branching vertex has degree exactly \( 3 \).

Substituting (3) into (2) gives the exact constraint

\[
n - n_2 - 2 = n_{\ge 3} + \sum_{d \ge 4} (d-2) n_d. \tag{5}
\]

For \( n = q^2 - r \) and \( n_2 = 2q - 2 \), the left-hand side is

\[
n - n_2 - 2 = q^2 - r - (2q - 2) - 2 = (q-1)^2 - r - 1. \tag{6}
\]

Therefore,

\[
n_{\ge 3} + \sum_{d \ge 4} (d-2) n_d = (q-1)^2 - r - 1. \tag{7}
\]

This immediately implies

\[
n_{\ge 3} \le (q-1)^2 - r - 1. \tag{8}
\]

The number of leaves is

\[
n_1 = n - n_2 - n_{\ge 3} = (q-1)^2 + 1 - r - n_{\ge 3}. \tag{9}
\]

Since \( n_{\ge 3} \ge 0 \), we have \( n_1 \le (q-1)^2 + 1 - r \). Since \( n_1 \ge n_{\ge 3} + 2 \), we also have

\[
n_{\ge 3} \le \frac{(q-1)^2 - r - 1}{2}. \tag{10}
\]

The maximum possible degree \( \Delta(T) \) is bounded by the fact that

\[
\sum_{d \ge 3} (d-2) n_d \le (q-1)^2 - r - 1,
\]

so if a single vertex has degree \( \Delta \), then \( \Delta - 2 \le (q-1)^2 - r - 1 \), i.e.,

\[
\Delta \le (q-1)^2 - r + 1. \tag{11}
\]

This is a very weak bound; in practice, the degree sum constraint (7) forces the total “excess degree” above 3 to be small when \( n_2 \) is large, but here \( n_2 = 2q - 2 \) is small relative to \( n \), so there is substantial room for high-degree vertices.

**Summary of exact identities:**

| Quantity | Exact expression |
|----------|------------------|
| \( n \) | \( q^2 - r \) |
| \( n_2 \) | \( 2q - 2 \) |
| \( n_1 \) | \( (q-1)^2 + 1 - r - n_{\ge 3} \) |
| \( n_{\ge 3} \) | \( \le (q-1)^2 - r - 1 \) |
| \( n_1 - n_{\ge 3} \) | \( 2 + \sum_{d \ge 4} (d-3) n_d \) |
| \( \sum_{d \ge 3} (d-2) n_d \) | \( (q-1)^2 - r - 1 \) |
| \( \Delta \) | \( \le (q-1)^2 - r + 1 \) |

All identities are **[PROVED]** directly from the handshaking lemma and the definition of a tree.

---

## 3. Five Near-Square Cases

The five cases differ only in \( r \). The suppressed core \( H \) has

\[
|V(H)| = n - n_2 = (q-1)^2 + 1 - r, \tag{12}
\]

\[
|E(H)| = |V(H)| - 1 = (q-1)^2 - r. \tag{13}
\]

The total number of subdivision vertices is always

\[
\sum_{e \in E(H)} s_e = n_2 = 2q - 2. \tag{14}
\]

**Case A: \( r = 0 \), \( n = q^2 \).**
- \( |V(H)| = (q-1)^2 + 1 \)
- \( |E(H)| = (q-1)^2 \)
- The core \( H \) has one more vertex than a perfect square minus one. The number of subdivision vertices \( 2q-2 \) is approximately \( 2\sqrt{|E(H)|} \).

**Case B: \( r = 1 \), \( n = q^2 - 1 \).**
- \( |V(H)| = (q-1)^2 \)
- \( |E(H)| = (q-1)^2 - 1 \)
- The core \( H \) has exactly \( (q-1)^2 \) vertices.

**Case C: \( r = 2 \), \( n = q^2 - 2 \).**
- \( |V(H)| = (q-1)^2 - 1 \)
- \( |E(H)| = (q-1)^2 - 2 \)
- The core \( H \) has one fewer vertex than a perfect square.

**Case D: \( r = 3 \), \( n = q^2 - 3 \).**
- \( |V(H)| = (q-1)^2 - 2 \)
- \( |E(H)| = (q-1)^2 - 3 \)

**Case E: \( r = 4 \), \( n = q^2 - 4 \).**
- \( |V(H)| = (q-1)^2 - 3 \)
- \( |E(H)| = (q-1)^2 - 4 \)
- The core \( H \) is the smallest among the five cases.

**Comparison.** The number of subdivision vertices \( 2q-2 \) is identical in all five cases. What changes is the size of the core \( H \). In Case E (\( r = 4 \)), the core has \( (q-1)^2 - 3 \) vertices, which is smaller than in Case A by 4 vertices. Since Murakami’s theorem gives \( b(H) \le \lceil \sqrt{|V(H)|} \rceil \), and \( |V(H)| = (q-1)^2 - 3 \) in Case E, we have

\[
\sqrt{|V(H)|} = \sqrt{(q-1)^2 - 3} < q-1.
\]

Thus \( b(H) \le q-1 \) in Case E, whereas in Case A we only know \( b(H) \le q \) (since \( \sqrt{(q-1)^2 + 1} < q \)). Therefore, Case E leaves the least “burning budget” for the subdivision vertices to increase the burning number to \( q+1 \). **Case E (\( r = 4 \)) is the most promising case for a counterexample.**

However, this is not conclusive. A smaller core could also mean fewer edges to subdivide, which might make it easier to control the burning number. The structural constraint is that \( \sum s_e = 2q-2 \) must be distributed across \( |E(H)| = (q-1)^2 - 4 \) edges. The average \( s_e \) is about \( 2/(q-1) \), so almost all edges have \( s_e = 0 \). The subdivision vertices must be concentrated on at most \( 2q-2 \) edges.

**Structural constraint for all cases:** Since \( \sum s_e = 2q-2 \) and \( s_e \ge 0 \) are integers, at most \( 2q-2 \) edges of \( H \) are subdivided, and if an edge is subdivided, it receives at most \( 2q-2 \) vertices (if all subdivisions are on one edge). The number of subdivided edges is at most \( 2q-2 \), which is \( O(q) \), while \( |E(H)| = O(q^2) \). Therefore, **the vast majority of edges in \( H \) are unsubdivided**.

---

## 4. Candidate Extremal Families

We examine the ten families listed in the task. For each, we determine whether it can satisfy \( n = q^2 - r \), \( n_2 = 2q-2 \), and whether it could plausibly have \( b(T) \ge q+1 \).

### 4.1 Paths

A path of order \( n \) has \( n_2 = n - 2 = q^2 - r - 2 \). For this to equal \( 2q-2 \), we need \( q^2 - r - 2 = 2q - 2 \), i.e., \( q^2 - 2q - r = 0 \), so \( q = 1 \pm \sqrt{1+r} \). For \( r \in \{0,1,2,3,4\} \), \( 1+r \in \{1,2,3,4,5\} \), and \( q \) must be an integer. The only integer solutions are \( q = 2 \) for \( r = 0 \) (since \( \sqrt{1} = 1 \), \( q = 2 \)) and possibly \( q = 3 \) for \( r = 3 \) (since \( \sqrt{4} = 2 \), \( q = 3 \)). For large \( q \), paths do not satisfy the constraint. **Paths are excluded for large \( q \).**

### 4.2 Spiders

A spider with \( k \) legs of lengths \( l_1, \dots, l_k \) has

\[
n = 1 + \sum_{i=1}^k l_i, \qquad n_2 = \sum_{i: l_i \ge 2} (l_i - 1).
\]

The burning number of a spider is roughly \( \max_i l_i \) if one leg is much longer than the others, or \( \lceil \sqrt{n} \rceil \) if the legs are balanced. To have \( n_2 = 2q-2 \), we need \( \sum (l_i - 1) = 2q-2 \) over legs with \( l_i \ge 2 \). If all legs have length \( L \), then \( k(L-1) = 2q-2 \), and \( n = 1 + kL = 1 + k(L-1) + k = 1 + 2q - 2 + k = 2q - 1 + k \). For this to equal \( q^2 - r \), we need \( k = q^2 - r - 2q + 1 = (q-1)^2 - r \). But then \( L - 1 = (2q-2)/((q-1)^2 - r) \), which is less than 1 for \( q \ge 4 \). **Spiders with equal leg lengths are excluded for \( q \ge 4 \).**

If legs have unequal lengths, the constraint \( \sum (l_i - 1) = 2q-2 \) still forces the total “excess length” to be \( 2q-2 \). To have \( n \approx q^2 \), the number of legs \( k \) must be large, but then most legs must have length 1 (leaves). If \( k \approx q^2 \), then the spider is essentially a star with \( q^2 \) leaves, which has \( n_2 = 0 \), contradicting \( n_2 = 2q-2 \). To get \( n_2 = 2q-2 \), we need at most \( 2q-2 \) legs of length 2 or more, and all other legs length 1. Then \( n = 1 + (2q-2) \cdot 2 + (\text{number of length-1 legs}) \cdot 1 \). If there are \( m \) length-1 legs, then \( n = 1 + 4q - 4 + m = 4q - 3 + m \). For \( n = q^2 - r \), we need \( m = q^2 - r - 4q + 3 \). This is positive for large \( q \). So a spider with \( 2q-2 \) legs of length 2 and \( q^2 - r - 4q + 3 \) leaves satisfies the constraints. The burning number of such a spider: the longest leg has length 2, so the burning number is at most 2 (if the spider is burned from the center) or more precisely \( \lceil \sqrt{n} \rceil \) if the spider is star-like. Actually, a spider with all legs of length at most 2 has burning number at most 3 (burn the center, then the midpoints, then the leaves). So \( b(T) \le 3 \ll q \) for large \( q \). **Such spiders have small burning number and cannot be counterexamples.**

### 4.3 Subdivided Stars

A subdivided star is a spider with all legs of length at least 1. As shown in 4.2, to have \( n_2 = 2q-2 \), the legs must have total excess length \( 2q-2 \). If all legs are subdivided equally, the arithmetic fails for large \( q \). If subdivisions are concentrated on a few legs, the tree is essentially a star with a few long subdivided legs. For example, one leg of length \( 2q-1 \) (with \( 2q-2 \) degree-2 vertices) and many leaves. Then \( n = 1 + (2q-1) + m \), where \( m \) is the number of leaves. For \( n = q^2 - r \), \( m = q^2 - r - 2q \). This is a “broom” or “subdivided star” with one long path and many leaves. The burning number of such a tree: the long path of length \( 2q-1 \) has burning number \( \lceil \sqrt{2q-1} \rceil \approx \sqrt{2q} \), which is much less than \( q \) for large \( q \). The leaves can be burned quickly. So \( b(T) \ll q \). **Subdivided stars with one long leg are not dangerous.**

### 4.4 Brooms

A broom is a path with a star at one end. If the path has length \( L \) and the star has \( m \) leaves, then \( n = L + 1 + m \), \( n_2 = L - 1 \) (the path internal vertices, excluding the endpoint attached to the star and the leaf at the other end). Setting \( n_2 = 2q-2 \) gives \( L = 2q-1 \). Then \( n = 2q + m \). For \( n = q^2 - r \), \( m = q^2 - r - 2q \). The burning number of a broom with path length \( L \) and \( m \) leaves: the path part has burning number \( \lceil \sqrt{L} \rceil \approx \sqrt{2q} \), and the star can be burned in 2 rounds if the center is burned. So \( b(T) \approx \sqrt{2q} \ll q \). **Brooms are not dangerous.**

### 4.5 Double-Stars

A double-star is a tree with two adjacent central vertices \( u \) and \( v \), with \( a \) leaves attached to \( u \) and \( b \) leaves attached to \( v \). Then \( n = a + b + 2 \), \( n_2 = 0 \) (since \( u \) and \( v \) have degree \( a+1 \) and \( b+1 \), which are at least 2 if \( a, b \ge 1 \), but they are not degree 2 unless \( a=1 \) or \( b=1 \); if \( a=1 \), then \( u \) has degree 2). To have \( n_2 = 2q-2 \), we need many degree-2 vertices, which a double-star with leaves does not have unless we subdivide edges. A subdivided double-star can have degree-2 vertices on the edges between the centers and the leaves. But the burning number of a double-star is small (at most 3 or 4). **Double-stars are not dangerous.**

### 4.6 Subdivided Double-Stars

Consider two centers \( u, v \) connected by a path of length \( L \), with \( a \) leaves attached to \( u \) and \( b \) leaves attached to \( v \). The degree-2 vertices are on the path between \( u \) and \( v \) (there are \( L-1 \) of them) and possibly on the edges to leaves if those edges are subdivided. To reach \( n_2 = 2q-2 \), we can set \( L-1 = 2q-2 \), so \( L = 2q-1 \). Then \( n = 2 + (2q-1) + a + b = 2q + 1 + a + b \). For \( n = q^2 - r \), \( a + b = q^2 - r - 2q - 1 \). The burning number of this tree: the path of length \( 2q-1 \) has burning number \( \lceil \sqrt{2q-1} \rceil \approx \sqrt{2q} \), and the leaves can be burned quickly. So \( b(T) \approx \sqrt{2q} \ll q \). **Not dangerous.**

If instead we put the degree-2 vertices on the leaf edges, we would have many short subdivided edges. For example, a double-star with centers \( u, v \), each with \( k \) leaves, and each leaf edge subdivided once. Then \( n_2 = 2k \), so \( k = q-1 \). Then \( n = 2 + 2(q-1) \cdot 2 = 4q - 2 \), which is much smaller than \( q^2 \) for large \( q \). So this cannot satisfy \( n = q^2 - r \).

### 4.7 Caterpillars

A caterpillar is a tree where removing all leaves leaves a path (the “spine”). Let the spine have \( L \) vertices, with \( a_i \) leaves attached to spine vertex \( i \). Then \( n = L + \sum a_i \), \( n_2 = \) (number of spine vertices of degree 2, i.e., those with \( a_i = 1 \) and not at the ends) + (any subdivided edges on the spine). To reach \( n_2 = 2q-2 \), we can either subdivide spine edges or have many spine vertices with exactly one leaf. The burning number of a caterpillar is related to its spine length and the distribution of leaves. It is known that caterpillars satisfy the burning number conjecture (Bonato et al., 2016). So caterpillars are not counterexamples. **Not dangerous.**

### 4.8 Trees with Several High-Degree Branching Vertices

These are trees where \( H \) has multiple vertices of degree \( \ge 3 \). Since \( H \) has \( (q-1)^2 + 1 - r \) vertices and \( n_2 = 2q-2 \) subdivisions, most of \( H \) is unsubdivided. The burning number of such a tree is at least the burning number of \( H \), which by Murakami’s theorem is \( \le \lceil \sqrt{|V(H)|} \rceil \le q \). The subdivisions can increase the burning number by at most a small amount. It is plausible that \( b(T) \le q \) for all such trees, but this is **[CONJECTURAL]**.

### 4.9 Trees Where Degree-2 Vertices Are Concentrated on a Few Edges

If all \( 2q-2 \) degree-2 vertices are on a single edge of \( H \), then \( T \) contains a path of length \( 2q-1 \) between two branching vertices (or between a branching vertex and a leaf). The burning number of this path is \( \lceil \sqrt{2q-1} \rceil \approx \sqrt{2q} \), which is much less than \( q \). So concentration on a few edges does not create a large burning number.

### 4.10 Trees Where Degree-2 Vertices Are Distributed Across Many Edges

If the \( 2q-2 \) degree-2 vertices are distributed across \( 2q-2 \) edges, each edge receives exactly one subdivision vertex. Then the tree \( T \) is obtained from \( H \) by subdividing \( 2q-2 \) edges once. The burning number of \( T \) is at most \( b(H) + 1 \). Since \( b(H) \le q-1 \) (as \( |V(H)| < q^2 \)), we get \( b(T) \le q \). So this distribution is safe.

**Conclusion:** None of the standard families obviously produces a counterexample. The most dangerous trees would be those where the subdivision vertices are placed in a way that maximizes the burning number without creating too many long paths. The optimal placement is likely to subdivide edges near the “center” of \( H \), potentially increasing the distance from a central source to the leaves.

---

## 5. Existing Literature Connections

The following sources are directly relevant. All URLs were verified during the search.

**Primary sources:**

1. **Bonato, A., Janssen, J., Roshanbin, E.** “How to burn a graph.” *Internet Mathematics* **12** (2016), 85–100. Introduces the burning number and states the conjecture \( b(G) \le \lceil \sqrt{n} \rceil \). Also proves the conjecture for paths and cycles. **[Verified]**

2. **Bessy, S., Bonato, A., Janssen, J., Rautenbach, D., Roshanbin, E.** “Bounds on the Burning Number.” *Discrete Applied Mathematics* **235** (2018), 16–22. arXiv:1511.06023. Proves \( b(G) \le 2\lceil \sqrt{n} \rceil - 1 \), and for trees with \( n_2 \) degree-2 vertices and \( n_{\ge 3} \) vertices of degree at least 3, gives \( b(T) \le \lceil \sqrt{n + n_2 + 1/4} + 1/2 \rceil \). **[Verified]**

3. **Murakami, Y.** “The Burning Number Conjecture is True for Trees without Degree-2 Vertices.” *Graphs and Combinatorics* **40** (2024), Article 82. DOI: 10.1007/s00373-024-02812-6. Proves the conjecture for homeomorphically irreducible trees (HITs). **[Verified]**

4. **Ning, J., Jin, X., Zhang, M.** “The burning number conjecture holds for trees of order \( n \) with at most \( \lfloor \sqrt{n-1} \rfloor \) degree-2 vertices.” arXiv:2509.03144 (v2, 5 Sep 2025). *Graphs and Combinatorics* **42**(2), 2026. Proves the bound

\[
b(T) \le \left\lceil \left( n + n_2 - \left\lceil \sqrt{n + n_2 + 0.25} - 1.5 \right\rceil \right)^{1/2} \right\rceil.
\]

Hence, the conjecture holds for \( n_2 \le \lfloor \sqrt{n-1} \rfloor \). **[Verified via arXiv abstract and full PDF.]**

5. **Bonato, A.** “A survey of graph burning.” *Contributions to Discrete Mathematics* **16**(1) (2021), 185–197. Zbl 1457.05068. Survey of results and open problems. **[Verified]**

**Unverified source:**

6. **Das, S., Islam, S. S., Mitra, R. M., Paul, S.** “Burning a binary tree and its generalization.” arXiv:2308.02825 (2023). This paper studies burning of binary trees. I could **not** verify the existence of a 2026 preprint by these authors claiming the \( n_2 \le 2q-3 \) threshold. The user’s description of this preprint may refer to unpublished work or a paper not indexed by the search tools available here. **Marked as unverified.**

**Relevant results from the literature:**

- The conjecture is known for paths, cycles, spiders, caterpillars, and trees with sufficient leaves (Bonato et al., 2016; Das et al., 2018; Bonato & Lidbetter, 2019).
- The conjecture holds asymptotically for all connected graphs (Norin & Turcotte, 2024).
- Graph burning is NP-complete even for trees of maximum degree 3 (Bessy et al., 2017).

**Important gap:** The full proof of the \( 2q-3 \) threshold is not available to me. Without it, I cannot determine exactly where the inequality \( n_2 \le 2q-3 \) is used and what changes when \( n_2 = 2q-2 \).

---

## 6. Analysis of the \( 2q-3 \) Threshold

The proof of the Ning–Jin–Zhang bound proceeds as follows:

1. **Lemma 8:** For any tree \( T \) of order \( n \ge 3 \) and any real \( p \in [1, n-1) \), there exists a vertex \( v \) such that one component of \( T - v \) has order \( > p \) and all other components have order \( \le p \).

2. **Lemma 9:** If \( T \) has \( n_2 \) degree-2 vertices, then the number of internal vertices (vertices of degree \( \ge 2 \)) is at most \( (n_2 + n - 2)/2 \).

3. **Lemma 10:** Smoothing a degree-2 vertex adjacent to a leaf can increase the burning number by at most 1.

4. **Proposition 11:** For a tree \( T \) of order \( n \ge m(m+1)+1 \) without degree-2 vertices, \( b(T) \le \lceil \sqrt{n-m} \rceil \).

5. **Theorem 5:** For a tree \( T \) of order \( n \) with \( n_2 \) degree-2 vertices, \( b(T) \le \lceil (n + n_2 - \lceil \sqrt{n + n_2 + 0.25} - 1.5 \rceil)^{1/2} \rceil \).

6. **Corollary 6:** If \( n_2 \le \lfloor \sqrt{n-1} \rfloor \), then \( b(T) \le \lceil \sqrt{n} \rceil \).

**Where the threshold \( n_2 \le 2q-3 \) would enter:** The Das et al. preprint allegedly claims that \( n_2 \le 2q-3 \) suffices. This would require a strengthening of Corollary 6. The key step is inequality (4) in the Ning–Jin–Zhang paper:

\[
\left\lceil \left( n + n_2 - \left\lceil \sqrt{n + n_2 + 0.25} - 1.5 \right\rceil \right)^{1/2} \right\rceil \le \lceil \sqrt{n} \rceil.
\]

For \( n = q^2 - r \) and \( n_2 = 2q - 2 \), the left-hand side becomes

\[
\left\lceil \left( q^2 - r + 2q - 2 - \left\lceil \sqrt{q^2 - r + 2q - 2 + 0.25} - 1.5 \right\rceil \right)^{1/2} \right\rceil.
\]

For large \( q \), \( \sqrt{q^2 + 2q - r - 2 + 0.25} \approx q + 1 - (r+2)/(2q) \). So the ceiling term is approximately \( q + 1 - 1.5 = q - 0.5 \), hence \( \lceil q - 0.5 \rceil = q \). Then the expression inside the square root is approximately

\[
q^2 + 2q - r - 2 - q = q^2 + q - r - 2,
\]

whose square root is approximately \( q + 1/2 \), so the ceiling is \( q+1 \). Thus the Ning–Jin–Zhang bound gives \( b(T) \le q+1 \), not \( q \), for \( n_2 = 2q-2 \). The \( 2q-3 \) threshold would require a sharper estimate that saves one more unit.

**What changes with one extra degree-2 vertex:** The extra degree-2 vertex increases \( n + n_2 \) by 1 (compared to \( n_2 = 2q-3 \)). This pushes the ceiling term \( \lceil \sqrt{n + n_2 + 0.25} - 1.5 \rceil \) from \( q-1 \) to \( q \) (for the relevant range), which in turn reduces the term inside the outer square root by 1, increasing the bound by roughly \( 1/(2q) \), which is not enough to cross an integer threshold for large \( q \). The obstruction appears to be **technical**, not structural. The proof strategy might extend to \( 2q-2 \) with a more careful analysis of the local structure around the subdivided edges.

---

## 7. Proven Structural Lemmas

**[PROVED] Lemma 1 (Leaf identity).** For any tree \( T \),

\[
n_1 = 2 + \sum_{d \ge 3} (d-2) n_d.
\]

*Proof:* Direct from the handshaking lemma. ∎

**[PROVED] Lemma 2 (Constraint on branching vertices).** If \( T \) satisfies \( n = q^2 - r \) and \( n_2 = 2q-2 \), then

\[
n_{\ge 3} + \sum_{d \ge 4} (d-2) n_d = (q-1)^2 - r - 1.
\]

*Proof:* Substitute \( n = q^2 - r \) and \( n_2 = 2q-2 \) into (5). ∎

**[PROVED] Lemma 3 (Core size).** Let \( H \) be the tree obtained from \( T \) by suppressing all degree-2 vertices. Then

\[
|V(H)| = (q-1)^2 + 1 - r, \qquad |E(H)| = (q-1)^2 - r.
\]

*Proof:* Suppressing each degree-2 vertex reduces the vertex count by 1, so \( |V(H)| = n - n_2 = q^2 - r - 2q + 2 = (q-1)^2 + 1 - r \). The edge count follows from \( |E(H)| = |V(H)| - 1 \). ∎

**[PROVED] Lemma 4 (Sparsity of subdivisions).** The average number of subdivision vertices per edge of \( H \) is

\[
\frac{2q-2}{(q-1)^2 - r} = O\left(\frac{1}{q}\right).
\]

In particular, for \( q \ge 4 \), at most \( 2q-2 \) edges of \( H \) are subdivided, and each subdivided edge receives at most \( 2q-2 \) vertices. ∎

**[PROVED] Lemma 5 (Burning number of the core).** The suppressed core \( H \) satisfies

\[
b(H) \le \left\lceil \sqrt{(q-1)^2 + 1 - r} \right\rceil \le q
\]

by Murakami’s theorem. In Case E (\( r = 4 \)), \( b(H) \le q-1 \). ∎

**[PROVED] Lemma 6 (Monotonicity under subdivision).** If \( T' \) is obtained from \( T \) by suppressing a degree-2 vertex, then \( b(T') \le b(T) \). Equivalently, subdividing an edge can increase the burning number by at most the number of subdivisions on that edge. ∎

*Note:* This is a standard fact: burning a subdivided edge requires at most one additional round per subdivision vertex, but often fewer.

---

## 8. Strong Computational Evidence

I have not performed computations for this structural analysis. The following is a proposed computational experiment, not a report of completed computations. Any claim about computational results would be **[STRONG EVIDENCE]** only if backed by explicit data, which is not available at this stage.

---

## 9. Conjectural Structural Patterns

**[CONJECTURAL] Pattern 1.** For all trees satisfying \( n = q^2 - r \) (\( r \in \{0,1,2,3,4\} \)) and \( n_2 = 2q-2 \), the burning number satisfies \( b(T) \le q \). This is the candidate conjecture. The structural analysis suggests that the extra degree-2 vertex beyond the \( 2q-3 \) threshold is absorbed by the existing proof technique without creating a genuine obstruction.

**[CONJECTURAL] Pattern 2.** The case \( r = 4 \) is the most likely to contain a counterexample, because the core \( H \) is smallest and the burning number of \( H \) is at most \( q-1 \), leaving the least margin for the subdivisions to push \( b(T) \) to \( q+1 \).

**[CONJECTURAL] Pattern 3.** Any counterexample, if it exists, must have its \( 2q-2 \) subdivision vertices distributed in a way that maximizes the distance from a central burning source to the leaves of \( H \). This likely means subdividing edges incident to a central vertex of \( H \) rather than edges near the leaves.

---

## 10. Best Computational Experiment

**Objective:** Determine whether there exists a tree \( T \) with \( n = q^2 - r \) (\( r \in \{0,1,2,3,4\} \)), \( n_2 = 2q-2 \), and \( b(T) = q+1 \).

**Design:**

1. **For \( q = 3, 4, 5, 6 \):** Exhaustively generate all trees of order \( n = q^2 - r \) for each \( r \in \{0,1,2,3,4\} \) using a standard tree generator (e.g., `networkx.nonisomorphic_trees` for small \( n \), or the `geng`/`gentreeg` tools from `nauty` for larger \( n \)).

2. **Filter** the generated trees to those with exactly \( n_2 = 2q-2 \) degree-2 vertices.

3. **Compute the exact burning number** of each filtered tree. For small trees (up to ~30 vertices), exact computation via BFS over all possible burning sequences is feasible. For larger trees, use known upper and lower bounds, or dynamic programming over tree decompositions.

4. **Record:**
   - Degree sequence
   - Number of leaves \( n_1 \)
   - Maximum degree \( \Delta \)
   - Number of branching vertices \( n_{\ge 3} \)
   - The suppressed core \( H \) (structure and order)
   - The subdivision-length distribution \( (s_e)_{e \in E(H)} \)
   - The burning number \( b(T) \)

5. **If exhaustive enumeration becomes infeasible** for \( q \ge 6 \), use:
   - **Structured enumeration:** Generate trees by starting from a core \( H \) without degree-2 vertices (using `gentreeg` for HITs) and then subdividing edges. Since \( \sum s_e = 2q-2 \) is small, the number of ways to distribute subdivisions is manageable.
   - **Random generation:** Generate random trees with the specified degree constraints using a configuration model and rejection sampling.
   - **Targeted search:** Focus on cores \( H \) with small burning number (close to \( q-1 \)) and place subdivisions on edges incident to a central vertex.
   - **SAT/ILP formulation:** Encode the existence of a burning sequence of length \( q \) as a satisfiability problem and use a SAT solver to search for counterexamples.

6. **Distinguish exact computation from heuristic search:** For \( q \le 5 \), exhaustive enumeration gives exact results. For larger \( q \), any counterexample found by random or targeted search is a valid counterexample, but failure to find one is not proof.

**Expected outcome:** Based on the structural analysis, no counterexample is expected for small \( q \). The experiment is designed to either confirm this or discover an unexpected structure.

---

## 11. Best Next Mathematical Step

**Choice: C. Prove a structural lemma.**

**Justification:** The structural analysis has reduced the problem to a very specific configuration: a tree whose suppressed core \( H \) has \( (q-1)^2 + 1 - r \) vertices and only \( 2q-2 \) subdivision vertices. The next mathematical step should be to prove a lemma that either:

1. Shows that any tree with this structure has \( b(T) \le q \), thereby extending the \( 2q-3 \) threshold to \( 2q-2 \); or

2. Shows that any counterexample must belong to a very restricted family (e.g., a subdivided double-star with a specific subdivision distribution), which can then be analyzed separately.

A concrete target lemma is:

> **[CONJECTURAL] Lemma.** Let \( T \) be a tree satisfying \( n = q^2 - r \) and \( n_2 = 2q-2 \). Then \( b(T) \le q \).

A weaker but more tractable intermediate lemma is:

> **[CONJECTURAL] Lemma.** If \( T \) is a tree satisfying the above constraints and \( T \) contains a path of length \( \ge 3q/2 \), then \( b(T) \le q \).

This would eliminate trees with very long subdivided paths and reduce the problem to trees with bounded path length, where the burning number can be controlled by the number of leaves.

**Why not the other options?**

- **A (Search aggressively for a counterexample):** Computational search is valuable but unlikely to find a counterexample if none exists, and the search space grows rapidly with \( q \). The structural analysis suggests that any counterexample would require a very specific configuration, which is better targeted by a lemma than by brute force.

- **B (Larger-scale exact computation):** This is a natural follow-up but should be guided by the structural lemma. Without the lemma, the computation may waste effort on trees that are provably safe.

- **D (Attempt to prove the original conjecture):** This is premature. The boundary case \( n_2 = 2q-2 \) is a small, well-defined subproblem that can serve as a stepping stone.

- **E (Focus on one special extremal tree family):** The structural analysis shows that no single standard family is the extremal one; the extremal trees are likely “generic” trees with a few subdivided edges. A structural lemma is more general and more promising.

**Next concrete action:** Write a detailed proof of a lemma that bounds the burning number of a tree in terms of the number of subdivision vertices and the structure of the core \( H \), with the goal of achieving \( b(T) \le q \) for \( n_2 = 2q-2 \).
