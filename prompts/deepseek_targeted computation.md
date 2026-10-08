You are now conducting a targeted computational investigation of ONE specific mathematical conjecture.

Do NOT generate new research problems.
Do NOT give a broad survey.
Do NOT try to prove the conjecture yet.
Do NOT rely on intuition alone.

Your only goal is to search computationally for a counterexample or, if none is found, identify the most dangerous/extremal trees.

---

# Conjecture

Let T be a tree on n vertices, and let n_2 be the number of degree-2 vertices of T.

The candidate is:

```
n_2 = 2 ceil(sqrt(n)) - 2
```

Does this imply

```
b(T) <= ceil(sqrt(n))?
```

We want to investigate the most important boundary case:

```
n = q^2
```

so that

```
ceil(sqrt(n)) = q
```

and therefore

```
n_2 = 2q - 2.
```

Thus the computational target is:

```
n = q^2,
n_2 = 2q - 2,
```

and we want to determine whether there exists a tree T satisfying these conditions with

```
b(T) >= q + 1.
```

A tree with b(T)=q+1 would be an explicit counterexample.

---

# IMPORTANT: Standard Burning Number Definition

Use the standard graph burning definition.

A burning sequence is a sequence of vertices

```
(v_1, v_2, ..., v_k)
```

such that at time i, vertex v_i must not already be burning.

After k rounds, every vertex must be burned.

Equivalently, the chosen centers must satisfy both:

1. the required distance/coverage condition, and
2. the "new source cannot already be burning" condition.

Do NOT compute burning number using coverage alone.

Before running large experiments, validate your implementation on small trees whose burning numbers are known exactly, including paths and stars.

---

# PART I — Feasibility

First determine for which q the conditions

```
n = q^2
n_2 = 2q - 2
```

are actually realizable by a tree.

Do not assume every q is feasible.

Explain the feasibility constraints using the standard tree degree identities.

---

# PART II — Exact Search for Small q

For the smallest feasible q values, perform an exact exhaustive search if computationally possible.

Prioritize:

```
q = 3, 4, 5, 6
```

and go higher if feasible.

For each

```
n = q^2,
```

consider all non-isomorphic trees satisfying

```
n_2 = 2q - 2.
```

For every such tree compute the exact burning number.

Record:

* q
* n
* number of candidate trees
* maximum b(T)
* whether b(T)=q+1 occurs
* number of trees with b(T)=q
* number of trees with b(T)=q+1, if any

If exhaustive enumeration is computationally impossible, explicitly say so and switch to a structured search. Do NOT pretend that an incomplete search is exhaustive.

---

# PART III — Structured Search Using the Degree-2 Suppressed Core

Because n_2 is only O(q), do not blindly enumerate all trees on q^2 vertices if a more efficient representation is available.

Suppress all degree-2 vertices.

Let H be the resulting tree/core.

Represent T as a subdivision of H:

```
T = (H, {s_e : e in E(H)}),
```

where s_e is the number of inserted degree-2 vertices on edge e.

Then

```
sum_e s_e = 2q - 2.
```

Use this representation to search intelligently.

For each candidate, record:

* the core H
* |V(H)|
* |E(H)|
* degree sequence of H
* maximum degree of H
* number of leaves
* subdivision vector (s_e)
* number of subdivided edges
* maximum subdivision length
* whether subdivisions are concentrated or distributed
* diameter
* radius
* b(H), if computable
* b(T)
* Delta = b(T) - b(H)

Pay particular attention to trees where subdivisions are:

1. concentrated on one/few edges;
2. evenly distributed;
3. located near leaves;
4. located near high-degree branching vertices;
5. located along diameter paths;
6. located between major branching vertices.

---

# PART IV — Search Specifically for Counterexamples

The primary objective is NOT merely to find large burning numbers.

Search specifically for

```
b(T) >= q+1.
```

If one is found, STOP and provide the explicit counterexample.

Give:

1. q
2. n=q^2
3. n_2=2q-2
4. degree sequence
5. adjacency list OR Prüfer code
6. core H
7. subdivision lengths
8. exact burning number
9. a rigorous certificate that b(T)=q+1

In particular, provide:

* a burning sequence showing b(T) <= q+1;
* and an argument/computational certificate showing that no burning sequence of length q exists.

Do NOT merely report "the program says b(T)=q+1."

---

# PART V — If No Counterexample Is Found

If no tree with b(T)=q+1 is found, do NOT conclude that the conjecture is true.

Instead identify the most dangerous examples.

For each q, report the trees achieving

```
max b(T).
```

Extract their structural features.

In particular determine whether high-burning examples tend to have:

* large diameter;
* large radius;
* path-like structure;
* few branching vertices;
* one dominant branching core;
* concentrated degree-2 subdivisions;
* distributed subdivisions;
* subdivisions near leaves;
* subdivisions near the center;
* multiple long arms;
* double-star-like structure;
* caterpillar-like structure.

Try to determine whether there is a recurring extremal pattern.

---

# PART VI — Compare T with Its Suppressed Core

For each important example calculate

```
Delta_b = b(T) - b(H).
```

This is especially important.

We want to understand how much the 2q-2 degree-2 vertices can increase the burning number.

Look for examples maximizing

```
b(T) - b(H).
```

Determine whether the worst examples have a common subdivision pattern.

Do NOT assume any monotonicity theorem unless you actually prove or verify it.

---

# PART VII — Exact Data Table

Produce a table like:

| q |  n | # candidate trees | max b(T) | q+1 found? | max Delta_b |
| - | -: | ----------------: | -------: | ---------- | ----------: |

Then provide a second table for the extremal examples:

| q | b(T) | degree sequence | diameter | radius | b(H) | Delta_b | subdivision pattern |
| - | ---: | --------------- | -------: | -----: | ---: | ------: | ------------------- |

For any potential counterexample, give the complete tree representation.

---

# PART VIII — Computational Reliability

This part is mandatory.

Explain exactly how the computation was performed.

State:

* programming language;
* graph-generation method;
* whether enumeration is exhaustive;
* how non-isomorphic trees are handled;
* algorithm for exact burning number;
* how the "new source must be unburned" condition is enforced;
* validation tests;
* runtime;
* which q values were actually completed.

If using external software/library, name it.

If you did NOT actually execute the computation, say:

```
"I did not execute the computation."
```

Do NOT fabricate numerical results.

Do not present hypothetical output as experimental evidence.

---

# PART IX — Final Assessment

At the end give exactly one of these classifications:

A. COUNTEREXAMPLE FOUND

B. NO COUNTEREXAMPLE FOUND IN AN EXHAUSTIVE SEARCH

C. NO COUNTEREXAMPLE FOUND, BUT SEARCH WAS PARTIAL

Then summarize:

1. strongest computational evidence;
2. most dangerous structural family;
3. maximum observed b(T);
4. maximum observed Delta_b;
5. whether the next step should be proof or larger computation.

Remember:

Finding no counterexample is NOT a proof.

The purpose of this experiment is to identify the actual extremal structures before attempting a mathematical proof.

Do not call the conjecture "proved", "true", "false", or "open" based solely on this computation.
