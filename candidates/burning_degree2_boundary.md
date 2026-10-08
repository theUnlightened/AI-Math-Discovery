# Burning Number — Degree-2 Boundary Candidate

## Candidate

Let T be a tree on n vertices, and let n_2 be the number of
degree-2 vertices of T.

Question:

If

    n_2 = 2 ceil(sqrt(n)) - 2,

must

    b(T) <= ceil(sqrt(n))?

## Current Status

Classification: D — apparently unresolved and potentially underexplored.

Confidence: 82%.

No directly matching theorem or counterexample was located.

## Known Boundary

A 2026 preprint by Das, Islam, Mitra and Paul claims:

    n_2 <= 2 ceil(sqrt(n)) - 3
    => b(T) <= ceil(sqrt(n)).

Therefore the candidate is exactly one degree-2 vertex beyond
the currently claimed threshold.

## Important Reduction

An earlier bound gives, for n >= 50,

    b(T) <= ceil(sqrt(n+n_2+8)) - 1.

Substituting

    n_2 = 2q - 2,
    q = ceil(sqrt(n)),

shows that the candidate is automatically true whenever

    q^2 - n >= 5.

Thus the genuinely difficult orders are

    n = q^2,
        q^2 - 1,
        q^2 - 2,
        q^2 - 3,
        q^2 - 4.

## Computational Evidence

All non-isomorphic trees through n = 19 were exhaustively checked
for the candidate condition.

No counterexample was found.

The largest completed case was n = 19, with 28,235 candidate trees.

## Epistemic Rule

This candidate is NOT called a "new open problem".

It is currently described as:

"apparently unresolved and potentially underexplored."

Novelty requires expert verification.
