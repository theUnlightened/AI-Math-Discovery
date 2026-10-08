You are acting ONLY as a computational runner.
Do not act as a mathematical research editor.
Do not redesign the research problem.
Do not discuss novelty or literature.
Do not attempt to prove the general conjecture.
Your ONLY task is to execute the Python program provided below and return the actual computational results.
import networkx as nx
from collections import Counter
import sys

def burning_number(G):
    """Exact burning number of G. Relabels nodes internally."""
    G = nx.convert_node_labels_to_integers(G)
    n = len(G)
    if n == 0:
        return 0
    adj_mask = [0] * n
    for i in range(n):
        for j in G.neighbors(i):
            adj_mask[i] |= (1 << j)
    all_mask = (1 << n) - 1

    def can_burn(k):
        memo = {}
        def dfs(step, B):
            if B == all_mask:
                return True
            if step > k:
                return False
            key = (step, B)
            if key in memo:
                return memo[key]
            not_B = all_mask ^ B
            NB = 0
            t = B
            while t:
                i_bit = t & -t
                i = i_bit.bit_length() - 1
                NB |= adj_mask[i]
                t ^= i_bit
            temp = not_B
            while temp:
                v_bit = temp & -temp
                v = v_bit.bit_length() - 1
                new_B = B | NB | v_bit
                if dfs(step + 1, new_B):
                    memo[key] = True
                    return True
                temp ^= v_bit
            memo[key] = False
            return False
        return dfs(1, 0)

    for k in range(1, n + 1):
        if can_burn(k):
            return k
    return n

def find_burning_sequence(G, k):
    """Return a valid burning sequence of length k, or None."""
    G = nx.convert_node_labels_to_integers(G)
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
        NB = 0
        t = B
        while t:
            i_bit = t & -t
            i = i_bit.bit_length() - 1
            NB |= adj_mask[i]
            t ^= i_bit
        temp = not_B
        while temp:
            v_bit = temp & -temp
            v = v_bit.bit_length() - 1
            new_B = B | NB | v_bit
            res = dfs(step + 1, new_B, seq + [v])
            if res is not None:
                return res
            temp ^= v_bit
        return None
    return dfs(1, 0, [])

def suppress_degree2(G):
    """Suppress all degree-2 vertices. Labels are preserved."""
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

def subdivision_lengths(T, H):
    """For each edge of H, return number of degree-2 vertices inserted in T."""
    s = []
    for u, v in H.edges():
        path = nx.shortest_path(T, u, v)
        s.append(len(path) - 2)
    return s

def validate():
    print("Validation tests:")
    for n in range(1, 11):
        P = nx.path_graph(n)
        b = burning_number(P)
        expected = int(n ** 0.5) if int(n ** 0.5) ** 2 == n else int(n ** 0.5) + 1
        print(f"P_{n}: b={b}, expected={expected}, ok={b==expected}")
    for m in range(2, 7):
        K = nx.star_graph(m)
        b = burning_number(K)
        print(f"K_{{1,{m}}}: b={b}, expected=2, ok={b==2}")

def main():
    n = 16
    q = 4
    target_n2 = 2 * q - 2  # 6
    print(f"q={q}, n={n}, target n2={target_n2}")
    print(f"Target: determine if any tree has b(T) >= {q+1}")

    trees = list(nx.nonisomorphic_trees(n))
    print(f"Total non-isomorphic trees on {n} vertices: {len(trees)}")
    if len(trees) != 19320:
        print(f"WARNING: expected 19320, got {len(trees)}")

    filtered = []
    for T in trees:
        n2 = sum(1 for _, d in T.degree() if d == 2)
        if n2 == target_n2:
            filtered.append(T)
    print(f"Trees with n2 = {target_n2}: {len(filtered)}")

    b_counts = Counter()
    max_b = 0
    extremal = []
    for T in filtered:
        b = burning_number(T)
        b_counts[b] += 1
        if b > max_b:
            max_b = b
            extremal = [T.copy()]
        elif b == max_b:
            extremal.append(T.copy())

    print(f"\nBurning number distribution: {dict(b_counts)}")
    print(f"Maximum burning number: {max_b}")
    print(f"Number with b=5: {b_counts.get(5, 0)}")
    print(f"Number with b=4: {b_counts.get(4, 0)}")
    print(f"Number with b=3: {b_counts.get(3, 0)}")
    print(f"Number of extremal trees (b={max_b}): {len(extremal)}")

    print("\n--- Extremal tree analysis (first few) ---")
    for idx, T in enumerate(extremal[:10]):
        print(f"\nExtremal tree {idx+1}:")
        print(f"Edges: {list(T.edges())}")
        deg_seq = sorted([d for _, d in T.degree()], reverse=True)
        print(f"Degree sequence: {deg_seq}")
        print(f"Leaves: {sum(1 for d in deg_seq if d == 1)}")
        print(f"Max degree: {max(deg_seq)}")
        try:
            diam = nx.diameter(T)
            rad = nx.radius(T)
            centers = nx.center(T)
        except Exception:
            diam = rad = centers = None
        print(f"Diameter: {diam}, Radius: {rad}, Centers: {centers}")

        H = suppress_degree2(T)
        s_list = subdivision_lengths(T, H)
        print(f"Subdivision lengths (sum={sum(s_list)}): {s_list}")

        H_relabeled = nx.convert_node_labels_to_integers(H)
        print(f"Core H edges: {list(H_relabeled.edges())}")
        H_deg = sorted([d for _, d in H_relabeled.degree()], reverse=True)
        print(f"Core degree sequence: {H_deg}")
        print(f"Core leaves: {sum(1 for d in H_deg if d == 1)}")
        print(f"Core max degree: {max(H_deg) if H_deg else 0}")
        try:
            H_diam = nx.diameter(H_relabeled)
            H_rad = nx.radius(H_relabeled)
        except Exception:
            H_diam = H_rad = None
        print(f"Core diameter: {H_diam}, Core radius: {H_rad}")
        bH = burning_number(H_relabeled) if len(H_relabeled) > 0 else 0
        print(f"b(H) = {bH}, Delta_b = {max_b - bH}")

        # Certificate: optimal burning sequence
        seq = find_burning_sequence(T, max_b)
        print(f"Optimal burning sequence of length {max_b}: {seq}")

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
    validate()
    main()

---

# Mathematical experiment

We study the finite case

```math
q=4,\qquad n=16,\qquad n_2=6.
```

The question is whether every 16-vertex tree with exactly 6 degree-2 vertices satisfies

```math
b(T)\le4.
```

A tree with

```math
b(T)\ge5
```

would be a counterexample for this finite case.

---

# Your responsibilities

## 1. Execute the program

Actually run the complete Python program below.
Do NOT merely inspect it.
Do NOT estimate the output.
Do NOT reuse numerical results from previous messages.
Do NOT fabricate runtime or results.

---

## 2. First run the validation tests

Report the actual output for:

```math
b(P_n)=\lceil\sqrt n\rceil
```

and

```math
b(K_{1,m})=2.
```

If validation fails, STOP and report the failure.
Do not silently modify the algorithm.

---

## 3. Run the complete q=4 exhaustive search

The program should:

- generate all non-isomorphic trees on 16 vertices;
- verify that the total is 19320;
- filter to trees with exactly 6 degree-2 vertices;
- compute the exact burning number of every filtered tree;
- determine the maximum burning number;
- determine whether `b(T)=5` occurs.

Report the actual values obtained.

---

## 4. Extremal analysis

For the trees attaining the maximum burning number, report the information produced by the program, including:

- edge list;
- degree sequence;
- number of leaves;
- maximum degree;
- diameter;
- radius;
- center;
- suppressed core;
- subdivision lengths;
- `b(H)`;
- `\Delta_b=b(T)-b(H)`;
- optimal burning sequence.

Do not add structural interpretations that were not actually computed.

---

## 5. Raw output

Paste the important raw console output from the actual execution.
This is important because another AI will
