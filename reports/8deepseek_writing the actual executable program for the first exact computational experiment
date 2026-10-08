## A. Mathematical correctness of the implementation

The burning number is computed by an exact depth-first search over all valid burning sequences. The simulation follows the standard process: at round \(i\), a new source \(v_i\) is chosen that is not currently burning; then fire spreads from all vertices that were already burning before this round; finally \(v_i\) is added to the burning set. Formally, if \(B\) is the burning set before round \(i\), we choose \(v \notin B\), then set

\[
B \leftarrow B \cup N(B) \cup \{v\}.
\]

This exactly matches the standard definition: \(v_i\) does not spread until the next round. The search tries all possible \(v\) at each round and returns success as soon as all vertices are burned. The minimum \(k\) for which this succeeds is the burning number. The implementation uses bitmasks for speed; \(n=16\) fits comfortably in a 32-bit integer. The unburned-source condition is enforced by only iterating over vertices not in the current burning set.

Suppression of degree-2 vertices is performed by repeatedly removing a degree-2 vertex and connecting its two neighbours, until no degree-2 vertices remain. This produces the homeomorphically irreducible core \(H\).

## B. Complete executable code

```python
import networkx as nx
from collections import Counter
import sys

def burning_number(G):
    """Return the exact burning number of graph G."""
    n = len(G)
    if n == 0:
        return 0
    adj_mask = [0] * n
    for i in range(n):
        for j in G.neighbors(i):
            adj_mask[i] |= (1 << j)
    all_mask = (1 << n) - 1

    def can_burn(k):
        def dfs(step, B):
            if B == all_mask:
                return True
            if step > k:
                return False
            not_B = all_mask ^ B
            temp = not_B
            while temp:
                v_bit = temp & -temp
                v = v_bit.bit_length() - 1
                # Compute N(B)
                NB = 0
                t = B
                while t:
                    i_bit = t & -t
                    i = i_bit.bit_length() - 1
                    NB |= adj_mask[i]
                    t ^= i_bit
                new_B = B | NB | v_bit
                if dfs(step + 1, new_B):
                    return True
                temp ^= v_bit
            return False
        return dfs(1, 0)

    for k in range(1, n + 1):
        if can_burn(k):
            return k
    return n

def find_burning_sequence(G, k):
    """Return a valid burning sequence of length k, or None."""
    n = len(G)
    if n == 0:
        return []
    adj_mask = [0] * n
    for i in range(n):
        for j in G.neighbors(i):
            adj_mask[i] |= (1 << j)
    all_mask = (1 << n) - 1

    def dfs(step, B, seq):
        if B == all_mask:
            return seq
        if step > k:
            return None
        not_B = all_mask ^ B
        temp = not_B
        while temp:
            v_bit = temp & -temp
            v = v_bit.bit_length() - 1
            NB = 0
            t = B
            while t:
                i_bit = t & -t
                i = i_bit.bit_length() - 1
                NB |= adj_mask[i]
                t ^= i_bit
            new_B = B | NB | v_bit
            res = dfs(step + 1, new_B, seq + [v])
            if res is not None:
                return res
            temp ^= v_bit
        return None
    return dfs(1, 0, [])

def suppress_degree2(G):
    """Return the tree obtained by suppressing all degree-2 vertices."""
    H = G.copy()
    changed = True
    while changed:
        changed = False
        for v in list(H.nodes()):
            if H.degree(v) == 2:
                neighbors = list(H.neighbors(v))
                if len(neighbors) == 2:
                    u, w = neighbors
                    H.remove_node(v)
                    if not H.has_edge(u, w):
                        H.add_edge(u, w)
                    changed = True
                    break
    return H

def main():
    n = 16
    q = 4
    target_n2 = 2 * q - 2  # 6
    print(f"Exact search for q={q}, n={n}, n2={target_n2}")
    print(f"Target: find any tree with b(T) >= {q+1}")

    trees = list(nx.nonisomorphic_trees(n))
    print(f"Total non-isomorphic trees on {n} vertices: {len(trees)}")
    # Correct number for n=16 is 19320. The problem statement's 7741 is for n=15.
    expected = 19320
    if len(trees) != expected:
        print(f"WARNING: Expected {expected} trees, got {len(trees)}")

    filtered = []
    for T in trees:
        n2 = sum(1 for _, d in T.degree() if d == 2)
        if n2 == target_n2:
            filtered.append(T)
    print(f"Number of trees with n2 = {target_n2}: {len(filtered)}")

    max_b = 0
    extremal = []
    b_counts = Counter()

    for T in filtered:
        b = burning_number(T)
        b_counts[b] += 1
        if b > max_b:
            max_b = b
            extremal = [T.copy()]
        elif b == max_b:
            extremal.append(T.copy())

    print(f"\nMaximum burning number among filtered trees: {max_b}")
    print(f"Counts: {dict(b_counts)}")
    print(f"Trees with b(T) = {q+1}: {b_counts.get(q+1, 0)}")
    print(f"Trees with b(T) = {q}: {b_counts.get(q, 0)}")
    print(f"Number of extremal trees (b = {max_b}): {len(extremal)}")

    print("\n--- Extremal tree analysis ---")
    for i, T in enumerate(extremal[:5]):
        print(f"\nExtremal tree {i+1}:")
        print(f"Edges: {list(T.edges())}")
        deg = sorted([d for _, d in T.degree()], reverse=True)
        print(f"Degree sequence: {deg}")
        print(f"Leaves: {sum(1 for d in deg if d == 1)}")
        print(f"Max degree: {max(deg)}")
        try:
            diam = nx.diameter(T)
            rad = nx.radius(T)
        except Exception:
            diam = rad = None
        print(f"Diameter: {diam}, Radius: {rad}")
        H = suppress_degree2(T)
        print(f"Core H edges: {list(H.edges())}")
        print(f"Core degrees: {sorted([d for _, d in H.degree()], reverse=True)}")
        bH = burning_number(H) if len(H) > 0 else 0
        print(f"b(H) = {bH}, Delta_b = {max_b - bH}")

    if max_b >= q + 1:
        print("\n!!! COUNTEREXAMPLE FOUND !!!")
        for T in extremal:
            if burning_number(T) >= q + 1:
                print("Counterexample tree:")
                print(f"Edges: {list(T.edges())}")
                print(f"Degree sequence: {sorted([d for _, d in T.degree()], reverse=True)}")
                b = burning_number(T)
                print(f"b(T) = {b}")
                seq_upper = find_burning_sequence(T, q + 1)
                print(f"Burning sequence of length {q+1}: {seq_upper}")
                print(f"No burning sequence of length {q} exists (exhaustive DFS failed).")
                break
    else:
        print("\nNo counterexample found (no tree with b(T) >= 5).")

if __name__ == "__main__":
    main()
```

## C. Validation tests

Before running the main experiment, validate `burning_number` on known graphs:

- Paths \(P_n\): \(b(P_n) = \lceil \sqrt{n} \rceil\). For \(n=1,2,3,4,5,6,7,8,9,10\), expected values: 1,2,2,2,3,3,3,3,3,4.
- Stars \(K_{1,m}\): \(b(K_{1,m}) = 2\) for \(m \ge 2\).
- Small random trees: compare against brute-force enumeration of all burning sequences (the same algorithm, but with a different implementation) for \(n \le 8\).

If any validation fails, stop and fix the implementation.

## D. Experimental output

The program was not executed, so no experimental results are reported.

## E. Reproducibility instructions

1. Install Python 3.8+ and NetworkX:
   ```
   pip install networkx
   ```
2. Save the code above to a file, e.g. `burning_q4.py`.
3. Run:
   ```
   python burning_q4.py
   ```
4. Expected runtime: for \(n=16\), there are 19320 non-isomorphic trees. Filtering by \(n_2=6\) leaves a few hundred trees. Exact burning number via DFS is fast for \(k \le 5\). Total runtime should be well under one minute on a modern laptop.
5. The program prints the total number of generated trees, the number passing the filter, the maximum burning number, counts of each burning number, and structural details of extremal trees. If a counterexample exists, it prints its edges, degree sequence, burning sequence of length \(q+1\), and notes that no sequence of length \(q\) exists.

## F. What the experiment will establish

A successful exhaustive computation of the \(q=4\) case will establish one of the following:

- **Counterexample found:** There exists a 16-vertex tree with exactly 6 degree-2 vertices and burning number at least 5. This would disprove the candidate implication \(n_2 = 2\lceil\sqrt n\rceil-2 \implies b(T) \le \lceil\sqrt n\rceil\) for \(q=4\).
- **No counterexample found:** Every 16-vertex tree with exactly 6 degree-2 vertices has burning number at most 4. This confirms the candidate implication for \(q=4\) only. It does **not** prove the conjecture for any other \(q\), nor does it prove the general statement. It is a single data point.

The experiment is exhaustive for \(q=4\) and therefore provides a rigorous computational certificate for that specific case. It does not address \(q \ge 5\), nor does it constitute a mathematical proof of the general conjecture.
