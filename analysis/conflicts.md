# DeepSeek vs Gemini — Conflict Analysis

## Purpose

Compare the independent reports produced by DeepSeek and Gemini.

The goal is to identify disagreements, mathematical errors,
uncertain claims, and questions requiring further verification.

---

## Candidate 10 — Burning Number of Trees

### DeepSeek

DeepSeek identified the burning number of trees as a potentially
important open problem.

However, its formulation contained a suspicious upper bound.

### Gemini

Gemini corrected the standard conjectural bound to:

b(T) <= ceil(sqrt(n))

and confirmed that the Burning Number Conjecture is a known open problem.

### Conflict

The original DeepSeek formulation was mathematically malformed.

Gemini appears to have corrected the statement.

### Current Status

Known open problem.

Not a new problem.

### Further Verification Needed

- Verify the exact original conjecture.
- Verify Murakami's 2024 result.
- Verify the most recent 2024–2026 results.
- Determine whether the proposed degree-2-density questions are already known.

---

## Candidate 3 — Yellowstone Permutation

### DeepSeek

DeepSeek identified surjectivity of the Yellowstone permutation
as an open problem.

### Gemini

Gemini independently confirmed that the surjectivity question
is a known open problem.

### Conflict

No major disagreement was identified.

### Current Status

Known open problem.

Not a new problem.

### Further Verification Needed

- Search for results published after the original 2015 paper.
- Check whether any partial surjectivity result has been proved.
- Verify whether the proposed "odd prime surjectivity" question
  is genuinely unresolved.

---

## Candidate 9 — Maximum Sidon Sets

### DeepSeek

DeepSeek suggested that the number of maximum-size Sidon sets
may be an interesting unresolved question.

However, its report contained questionable asymptotic claims
and appeared to confuse maximum and maximal Sidon sets.

### Gemini

Gemini independently identified major errors in DeepSeek's
counting claims.

Gemini classified the exact question as potentially underexplored,
but explicitly stated that novelty cannot be established.

### Conflict

The main issue is not whether the question is interesting,
but whether it has already been studied or follows easily
from existing results.

### Current Status

Potentially underexplored.

Novelty NOT established.

### Further Verification Needed

- Search the exact quantity M(n).
- Search equivalent formulations.
- Determine whether known constructions imply unbounded M(n).
- Check whether the proposed Singer-length question is already known.
- Search recent literature from 2020–2026.

---

# Overall Assessment

## Strongly Supported

- Burning Number Conjecture is a known open problem.
- Yellowstone permutation surjectivity is a known open problem.
- DeepSeek contained mathematical errors that Gemini identified.

## Uncertain

- Whether the maximum-Sidon-set question is genuinely unexplored.
- Whether any of the proposed smaller questions are already known.
- Whether some proposed refinements follow easily from existing results.

## Important Rule

No candidate will be described as a "new open problem"
until independent literature verification provides strong evidence.

---

# Next Stage

Submit both the DeepSeek and Gemini reports to an independent
adversarial mathematical reviewer.

The reviewer should attempt to disprove the conclusions,
find hidden errors, and identify prior work that was missed.


## Final Audit — GPT

Date: 2026-10-08

The GPT final audit identified several important errors shared by
the DeepSeek and Gemini reports.

### Major corrections

1. Yellowstone permutation
   - DeepSeek and Gemini incorrectly treated surjectivity as open.
   - The 2015 Applegate et al. paper proves that every positive integer
     occurs.
   - Therefore the permutation/surjectivity question is solved.

2. Proper divisor sum square
   - For every prime p, sigma(p)-p = 1 = 1^2.
   - Hence infinitely many solutions exist trivially.

3. Practical numbers
   - Melfi's relevant paper was published in 1996, not 2005.
   - The stated Goldbach-type result is already proved.

4. tau(n) = tau(n+1)
   - Heath-Brown proved infinitely many solutions in 1984.
   - Later quantitative improvements exist.

5. Maximum Sidon sets
   - Maximum and maximal Sidon sets must be distinguished.
   - OEIS A382395 directly studies the number M(n) of maximum-sized
     Sidon subsets of [n].
   - Therefore the claim that M(n) is essentially unstudied is outdated.

6. Burning Number
   - The BNC remains open.
   - However, several recent results substantially shrink the unresolved
     region.
   - In particular, a 2026 preprint claims the conjecture for trees with
     n_2 <= 2 ceil(sqrt(n)) - 3 degree-2 vertices.

### Current candidate directions

1. Burning Number:
   n_2 = 2 ceil(sqrt(n)) - 2

2. Burning Number:
   threshold function kappa(n)

3. Burning Number:
   fixed-diameter extremal function B(d)

4. Sidon:
   M(q^2 + q + 1) along Singer lengths

5. Van Eck:
   first-occurrence function t(m)

### Epistemic status

No candidate is currently classified as a "new open problem".

The strongest candidates are classified as:

- potentially underexplored
- apparently unresolved
- novelty requires expert verification

Primary-source verification is required before making any novelty claim.
