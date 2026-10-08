You are now conducting an adversarial mathematical verification of ONE specific research candidate.

Do NOT generate new research problems yet.

Your only task is to determine whether the following candidate survives serious mathematical and literature scrutiny.

Candidate:

Let T be a tree on n vertices, and let n_2 denote the number of degree-2 vertices of T.

Question:

If

n_2 = 2 ceil(sqrt(n)) - 2,

must

b(T) <= ceil(sqrt(n))?

where b(T) is the burning number of T.

The latest preliminary research suggests that a 2026 preprint proves the Burning Number Conjecture for trees satisfying

n_2 <= 2 ceil(sqrt(n)) - 3.

Therefore this candidate lies exactly one step beyond the claimed current threshold.

IMPORTANT EPISTEMIC RULE:

Do NOT assume that this candidate is open merely because previous AI systems did not find a solution.

The candidate must survive all of the following tests.

## Part 1 — Verify the exact latest theorem

Locate and inspect the primary source for the claimed 2026 result:

"Burning Number Conjecture is true for Trees with Few Degree-2 Vertices"

by Sandip Das, Sk Samim Islam, Ritam Manna Mitra, Sanchita Paul.

Determine:

1. Exact publication/preprint status.
2. Exact theorem statement.
3. Exact hypotheses.
4. Exact bound on n_2.
5. Whether the result really gives

   n_2 <= 2 ceil(sqrt(n)) - 3

   or something subtly different.
6. Whether there is a newer version, published version, correction, or later paper extending the bound.

Do not rely on abstracts alone. Inspect the actual theorem/proof whenever possible.

## Part 2 — Search specifically for the candidate

Search the exact mathematical formulation and equivalent formulations.

Search combinations such as:

"2 ceil(sqrt(n)) - 2" burning number

"degree-2 vertices" burning number tree

"few degree-2 vertices" burning number

burning number subdivision trees

burning number homeomorphic trees

burning number degree two threshold

Burning Number Conjecture degree-2 vertices

Also search mathematical databases and citation chains.

Check:

- arXiv
- Google Scholar-indexed papers
- Springer
- ScienceDirect
- MathSciNet / zbMATH if accessible
- MathOverflow
- ResearchGate only as a secondary source
- OEIS if relevant
- citation chains of Murakami 2024
- citation chains of Ning–Jin–Zhang
- citation chains of the 2026 preprint

The goal is to determine whether the exact candidate has already appeared.

## Part 3 — Try to derive the candidate from known theorems

This is critical.

Collect all known upper bounds of the form

b(T) <= f(n,n_2)

and determine whether substituting

n_2 = 2 ceil(sqrt(n)) - 2

already implies

b(T) <= ceil(sqrt(n)).

Do the algebra explicitly.

Also check whether stronger results for subdivisions, diameter, radius, leaves, maximum degree, path structure, or homeomorphically irreducible cores imply the candidate.

If it follows from an existing theorem, classify it as SOLVED.

## Part 4 — Attempt to construct counterexamples

Do not merely search literature.

Actively investigate whether trees satisfying

n_2 = 2 ceil(sqrt(n)) - 2

can violate

b(T) <= ceil(sqrt(n)).

Analyze possible extremal constructions.

Pay particular attention to:

- subdivided stars
- subdivided paths
- double-stars
- caterpillars
- spiders
- trees with many long degree-2 chains
- trees obtained by subdividing edges of homeomorphically irreducible trees
- combinations of high-degree branching cores and degree-2 chains

Determine whether any natural family could produce

b(T) > ceil(sqrt(n)).

If a counterexample exists, give the smallest known example and verify it rigorously.

## Part 5 — Small computational verification

If feasible, compute or reason about small n.

For each sufficiently small n:

1. enumerate non-isomorphic trees;
2. compute n_2;
3. identify trees satisfying

   n_2 = 2 ceil(sqrt(n)) - 2;
4. compute their exact burning number;
5. determine whether any counterexample exists.

You may use known graph algorithms, mathematical software, or write a small program if useful.

Do NOT fabricate computational results.

If exhaustive enumeration is infeasible, clearly state the largest n that can actually be verified.

## Part 6 — Boundary analysis

Investigate the three consecutive thresholds:

n_2 <= 2 ceil(sqrt(n)) - 3

n_2 = 2 ceil(sqrt(n)) - 2

n_2 = 2 ceil(sqrt(n)) - 1

Determine exactly what is known at each boundary.

The goal is to understand whether

2 ceil(sqrt(n)) - 2

is a genuinely meaningful mathematical boundary or merely an arbitrary number produced by the current theorem.

## Part 7 — Logical status

Assign exactly one of:

A = proved true

B = proved false / counterexample

C = already explicitly posed in the literature

D = apparently unresolved and potentially underexplored

E = formulation is mathematically interesting but novelty evidence is insufficient

Explain the classification.

Do NOT call it a "new open problem".

If unresolved, use language such as:

"apparently unresolved"

"potentially underexplored"

"no directly matching result was located"

"novelty requires expert verification"

## Part 8 — Research value

If the candidate survives:

Evaluate:

- mathematical naturalness
- relation to the Burning Number Conjecture
- difficulty
- computational tractability
- possibility of proving special cases
- possibility of constructing counterexamples
- potential for a short undergraduate research project
- likelihood that a publishable result could emerge

Then identify the most promising next mathematical subproblem.

Do NOT generate unrelated problems.

## Final verdict

Return exactly:

1. Latest theorem verified
2. Candidate solved by existing theorem? YES/NO
3. Candidate already explicitly studied? YES/NO
4. Counterexample found? YES/NO
5. Small computational evidence
6. Exact logical status A/B/C/D/E
7. Confidence percentage
8. If D/E: the precise reason it remains interesting
9. The single best next mathematical experiment or proof attempt

Use primary sources wherever possible and provide direct citations.
Never fabricate references.
