You are now writing the actual executable program for the first exact computational experiment for our mathematical conjecture.

Do NOT propose another experiment.
Do NOT give a literature survey.
Do NOT attempt to prove the conjecture.
Do NOT report numerical results unless you actually execute the code.

Your task is to produce a correct, reproducible program that performs an EXACT exhaustive search for the case

$$
q=4,\qquad n=q^2=16,\qquad n_2=2q-2=6.
$$

The goal is to determine whether there exists a 16-vertex tree \(T\) with exactly 6 degree-2 vertices and

$$
b(T)\ge q+1=5.
$$

A tree with \(b(T)=5\) would be a counterexample to the candidate in this case.

---

# 1. Mathematical definition

Use the standard graph burning number.

At each round, one new vertex is chosen as a source, and fire spreads one edge per round from every existing source.

A burning sequence

$$
(v_1,\dots,v_k)
$$

must satisfy the standard condition that \(v_i\) is not already burning when it is ignited.

After \(k\) rounds, every vertex must be burned.

IMPORTANT:

Do NOT replace the burning-number problem by a coverage-only problem.

The implementation must enforce both:

1. complete coverage;
2. the condition that each newly selected source is unburned at the time it is selected.

---

# 2. Exact enumeration of all trees

For \(n=16\), enumerate ALL non-isomorphic trees on 16 vertices.

Use a mathematically reliable method such as:

* nauty / gengentree / gentreeg, OR
* another exact unlabeled-tree generator.

If using NetworkX, explain precisely how non-isomorphic trees are generated and verify that the generator really produces every unlabeled tree exactly once.

The known total number of non-isomorphic trees on 16 vertices is

$$
7741.
$$

Use this as an independent sanity check.

Your program should verify that it generated exactly 7741 non-isomorphic 16-vertex trees before filtering.

Do NOT hard-code this number as the result of the experiment; use it only as a validation check.

---

# 3. Filter condition

For every generated tree \(T\), compute the number of degree-2 vertices.

Keep exactly those satisfying

$$
n_2=6.
$$

Record:

* total number of non-isomorphic 16-vertex trees;
* number surviving the \(n_2=6\) filter.

---

# 4. Exact burning-number algorithm

Implement an EXACT algorithm for \(b(T)\).

You may use:

* exhaustive search over burning sequences;
* branch-and-bound;
* dynamic programming;
* BFS/state-space search;
* mathematically justified pruning.

But the answer must be exact.

For each tree, determine the smallest \(k\) for which a valid burning sequence exists.

The program must explicitly enforce the temporal condition that the new source is unburned when selected.

Do NOT use an incorrect formulation based only on balls of radii

$$
k-1,k-2,\dots,0
$$

unless you separately prove that your formulation is exactly equivalent to the standard burning definition.

---

# 5. Validation of the burning-number implementation

Before using the algorithm on the 16-vertex exhaustive search, validate it on small standard trees.

At minimum test:

* \(P_1,P_2,\dots\) for which the burning number is known;
* stars \(K_{1,m}\);
* several small randomly generated trees.

For paths verify

$$
b(P_n)=\lceil\sqrt n\rceil.
$$

If your implementation disagrees with known values, STOP and fix it before doing the 16-vertex search.

Explain these validation results.

---

# 6. Main experiment

For every tree satisfying

$$
n=16,\qquad n_2=6,
$$

compute \(b(T)\).

Produce:

$$
\max b(T)
$$

among all filtered trees.

Also determine:

* whether any tree satisfies \(b(T)=5\);
* how many have \(b(T)=4\);
* how many have \(b(T)=5\), if any;
* minimum and maximum burning number among filtered trees.

The most important question is:

$$
\boxed{\exists T:\ |V(T)|=16,\ n_2=6,\ b(T)\ge5\ ?}
$$

---

# 7. Store extremal examples

For every tree attaining the maximum burning number, record a complete machine-readable description.

At minimum include:

* adjacency list;
* degree sequence;
* diameter;
* radius;
* number of leaves;
* maximum degree;
* number of degree-3, degree-4, etc. vertices.

If several extremal trees exist, report them all if their number is small; otherwise give the number of extremal isomorphism classes and representative examples.

---

# 8. Suppressed core analysis

For every extremal tree, suppress all degree-2 vertices to obtain its core \(H\).

Record:

* \(H\)'s adjacency list;
* degree sequence of \(H\);
* \(b(H)\);
* subdivision lengths \(s_e\);
* number of subdivided edges;
* maximum subdivision length.

Then calculate

$$
\Delta_b=b(T)-b(H).
$$

Do NOT assume any monotonicity theorem about subdivision unless it is proved.

The purpose here is only empirical structural analysis.

---

# 9. Counterexample certificate

If a tree with

$$
b(T)=5
$$

is found, give a complete certificate.

Provide:

1. exact adjacency list;
2. degree sequence;
3. exact value \(n_2=6\);
4. a valid burning sequence of length 5;
5. a rigorous computational certificate that no valid burning sequence of length 4 exists.

Do NOT merely write:

> “The program says the burning number is 5.”

Show how the program establishes minimality.

---

# 10. Reproducibility requirements

Provide the COMPLETE executable source code.

Do not provide pseudocode only.

State:

* programming language and version;
* required packages;
* installation commands;
* exact command used to run the experiment;
* expected runtime;
* whether all 7741 trees were actually generated;
* whether all filtered trees were actually tested.

If you do not have the ability to execute the program in your environment, say clearly:

> “I wrote the program, but I did not execute it.”

Do not invent numerical output.

---

# 11. Output format

Your response should contain exactly these sections:

## A. Mathematical correctness of the implementation

Explain why the burning-number algorithm matches the standard definition.

## B. Complete executable code

Provide the full code in one block.

## C. Validation tests

Give the tests used to validate the algorithm.

## D. Experimental output

ONLY include this section with numerical results if you actually executed the program.

Otherwise write:

> “The program was not executed, so no experimental results are reported.”

## E. Reproducibility instructions

Explain exactly how I can run it.

## F. What the experiment will establish

Explain precisely what a successful exhaustive computation of the \(q=4\) case would and would not prove.

---

# Final restrictions

Do not call the conjecture true or false.

Do not call the candidate a new theorem.

Do not claim a counterexample unless the program actually finds one.

Do not fabricate runtime, counts, burning numbers, or structural patterns.

The only objective of this round is:

$$
\boxed{\text{produce a mathematically correct executable exact }q=4\text{ search}.}
$$
