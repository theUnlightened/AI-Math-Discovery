You are an independent mathematical literature researcher and skeptical research assistant.
I will give you a report produced by another AI (DeepSeek) that investigated potentially open mathematical problems.
Your task is NOT to trust the report. Independently verify its mathematical correctness and research status.

Main goals
For each of the three candidates below:

Verify that the mathematical statement itself is correctly formulated.
Check whether the cited results, papers, authors, dates, and claims are real.
Search for the exact problem and mathematically equivalent formulations.
Search recent literature, especially 2020–2026.
Search arXiv, Google Scholar-indexed sources, MathOverflow, Math StackExchange, OEIS, journal papers, surveys, and open-problem lists where relevant.
Determine whether the problem is:
already solved;
already explicitly studied;
a known open problem;
a special case of a known open problem;
a straightforward consequence of known results;
or potentially underexplored.
Do NOT infer novelty merely because you cannot find a paper.
If you find evidence that the problem is open, provide the strongest source supporting that claim.
If the problem is already known, identify the earliest or most authoritative source you can find.
If a candidate is too broad or already well known, try to identify a smaller, more precise research question arising naturally from it that appears less explored.
Important
Be especially alert for mathematical errors in the DeepSeek report.
Do not assume that its formulas, asymptotic estimates, conjecture statements, or citations are correct.
For every important claim, distinguish:

VERIFIED FACT
STRONG EVIDENCE
PLAUSIBLE BUT UNVERIFIED
SPECULATION
Do not call anything a "new open problem" unless there is very strong evidence.

Candidates
Candidate 10 — Burning number of trees
DeepSeek claims that the burning number of every tree T of order n satisfies a certain upper bound, and discusses known results for trees with restrictions on degree-2 vertices.
Verify the exact mathematical statement first. The formulation in the DeepSeek report may contain an error.

Candidate 3 — Yellowstone permutation
Question:
Is the Yellowstone permutation (OEIS A098550) a permutation of the positive integers?
Verify its current status and search for work from 2020–2026.

Candidate 9 — Maximum Sidon sets
Question:
Is the number of maximum-size Sidon sets in {1,...,n} unbounded as n → ∞?
Verify the formulation and all relevant asymptotic claims first. In particular, independently verify the order of magnitude of the maximum size of a Sidon set.

Required output
For each candidate, provide:

1. Mathematical correctness
Is the problem correctly formulated?

2. Literature status
What is actually known?

3. Strongest evidence
Give specific papers, authors, years, links, or database records.

4. Recent developments
What happened during 2020–2026?

5. Verdict
Choose one:
A. Solved
B. Known studied problem
C. Known open problem
D. Special case/generalization of a known open problem
E. Potentially underexplored, but novelty cannot be established
F. Problem is malformed or mathematically incorrect
6. Possible smaller research questions
If the original candidate is already known, derive 1–3 smaller and more precise questions that naturally arise from the literature.
These should not simply be superficial rewordings.

7. Confidence
Give a confidence level for your verdict and explain what remains uncertain.

Final ranking
After analyzing all three candidates:

Rank the candidates by potential for an actually useful research direction.
Identify which ones should be discarded.
Identify which smaller questions deserve further investigation.
Clearly separate "known open problem" from "potentially unexplored problem."
Here is the DeepSeek report:
Critical note before proceeding: The 10 candidates from Round 1 were not pasted into your message; the placeholder [PASTE THE 10 CANDIDATES FROM ROUND 1 HERE] remains unfilled. I cannot conduct a rigorous literature investigation without the precise problem statements. Below I proceed using the 10 candidates as they were ranked at the end of Round 1, reconstructed from that conversation. If your intended list differs, the analysis must be redone.
Candidate 1 (Round 1 Rank 1): Van Eck sequence surjectivity

Problem

Let the Van Eck sequence be defined by (a(1)=0), and for (n>1), if (a(n-1)) has appeared previously, let (a(n)) be the distance to its most recent previous occurrence; otherwise (a(n)=0). Is every nonnegative integer attained by this sequence?
Classification

E — No sufficiently close prior result found, but novelty cannot be established.
Prior Work

Direct searches for “Van Eck sequence surjective” returned no mathematical papers, only tangential results on surjectivity in unrelated contexts. The sequence is indexed in OEIS as A181391. The OEIS entry records computational observations but does not, to my knowledge, contain a proof of surjectivity. I was unable to locate a paper or preprint addressing the surjectivity question directly. This does not mean the problem is open; it may be discussed in unpublished notes, blog posts, or forums not indexed by the search tools available here.
Closest Known Results

The closest known result is the definition and basic computational exploration of the sequence itself. There is no known theorem establishing surjectivity for any infinite class of integers within the sequence.
Relevant Sources

OEIS A181391 (Van Eck’s sequence). Verified as a standard reference.
No arXiv, MathOverflow, or journal article was found that directly addresses surjectivity.
What Appears To Remain Unknown

Whether the image of the Van Eck sequence is all of (\mathbb{N}_0). I have no evidence that this has been proved, and no evidence that it has been explicitly stated as an open problem in the published literature.
Novelty Assessment

Potentially unexplored, but not independently verified. The problem is simple to state and computationally testable, but its absence from search results is weak evidence of novelty. It may be known to sequence enthusiasts.
Mathematical Significance

55
Probability That a Genuine Open Component Exists

40
Confidence in This Assessment

30 (low, due to absence of direct literature evidence)
Main Risks

The problem may be discussed in non-indexed sources (blogs, forums, OEIS comments).
Surjectivity may follow from a general theorem on greedy sequences not found by the searches.
The problem may be considered too recreational for formal literature.
Candidate 2 (Round 1 Rank 2): EKG sequence is a permutation

Problem

The EKG sequence is defined by (a(1)=1), (a(2)=2), and for (n>2), (a(n)) is the smallest unused positive integer sharing a common factor with (a(n-1)). Is ((a(n))) a permutation of the positive integers?
Classification

A — Already solved.
Prior Work

The EKG sequence was introduced and studied by Lagarias, Rains, and Sloane in a paper published in Experimental Mathematics (2002). The abstract and search results indicate that they proved the sequence is a permutation of the natural numbers and established linear bounds (c_1 n \le a(n) \le c_2 n). Subsequent work by Hofman and Pilipczuk (“A few new facts about the EKG sequence,” Journal of Integer Sequences, 2008) refined aspects of the sequence. The OEIS entry A064413 records the theorem that it is a permutation.
Closest Known Results

Lagarias, Rains, Sloane (2002): proof of permutation property.
Hofman, Pilipczuk (2008): additional structural facts.
Asymptotic conjectures remain open (e.g., (a(n) \sim n(1+1/(3\log n)))), but the permutation question is settled.
Relevant Sources

Lagarias, J. C., Rains, E. M., Sloane, N. J. A., “The EKG sequence,” Experimental Mathematics 11(3), 437–446 (2002). Verified via multiple search results.
OEIS A064413. Verified.
What Appears To Remain Unknown

The exact asymptotic formula for (a(n)). The permutation property is not unknown.
Novelty Assessment

Not novel as an open problem. The central question is solved.
Mathematical Significance

75 (for the solved theorem)
Probability That a Genuine Open Component Exists

5
Confidence in This Assessment

95 (high, based on multiple sources)
Main Risks

The asymptotic formula remains conjectural, but the permutation property does not.
Candidate 3 (Round 1 Rank 3): Yellowstone permutation is a permutation

Problem

The Yellowstone permutation is defined by (a(1)=1), (a(2)=2), (a(3)=3), and for (n>3), (a(n)) is the smallest unused positive integer such that (\gcd(a(n),a(n-1))>1) and (\gcd(a(n),a(n-2))=1). Is it a permutation of the positive integers?
Classification

B — Already explicitly proposed or studied.
Prior Work

The sequence was defined and studied by Applegate, Pol, Sloane, and others in a paper titled “The Yellowstone Permutation” (arXiv:1501.01669, 2015). The paper proves that the sequence is infinite and discusses its structural properties. Search results indicate that the surjectivity (permutation) question is explicitly open for the Yellowstone permutation. A 2024 paper on a binary analog states: “It is still an open question whether or not every eligible number appears in the Enots Wolley sequence”, and the Yellowstone permutation is closely related.
Closest Known Results

Applegate et al. (2015): proof that the sequence is infinite; structural analysis.
The Enots Wolley sequence (A336957) is a binary analog where surjectivity is explicitly open.
Relevant Sources

Applegate, D., Pol, O., Sloane, N. J. A., et al., “The Yellowstone Permutation,” arXiv:1501.01669 (2015). Verified via search results.
OEIS A098550. Verified.
The binary analog paper (search result 4) explicitly states the open question. Verified as a search result.
What Appears To Remain Unknown

Whether the Yellowstone permutation is surjective (i.e., whether every positive integer appears).
Novelty Assessment

Known to be open (at least for the closely related binary analog; the original Yellowstone surjectivity appears to be open as well, though I did not find a direct explicit statement for the original). This is not a novel problem; it is a studied open problem.
Mathematical Significance

65
Probability That a Genuine Open Component Exists

85 (high, given explicit statements in the literature)
Confidence in This Assessment

80 (high, based on direct search results)
Main Risks

The original Yellowstone surjectivity may have been resolved since the 2015 paper; I did not find a proof.
The binary analog is a different sequence, but closely related.
Candidate 4 (Round 1 Rank 4): Infinitely many (n) with (n+r(n)) square

Problem

Let (r(n)) denote the decimal digit reversal of (n). Are there infinitely many positive integers (n) such that (n+r(n)) is a perfect square?
Classification

C — A closely related problem has already been studied.
Prior Work

Search results show Math StackExchange discussions on related reversal problems: finding (n) such that both (n) and (r(n)) are perfect squares, and general properties of (n+r(n)) (the “Reverse Add Repdigit” theorem). I did not find a paper directly addressing the infinitude of (n) with (n+r(n)) square. However, the related problem of squares and digit reversal has been discussed in recreational and StackExchange contexts.
Closest Known Results

The fact that (n+r(n)) is always divisible by 9 for any (n) (a standard observation).
The “Reverse Add Repdigit” theorem: if every mirrored pair of digits sums to a constant (k), then (n+r(n)) is (k) repeated (n) times.
Relevant Sources

Math StackExchange discussions (URLs visible in search results). Verified as search results, but not peer-reviewed literature.
OEIS entries on Armstrong numbers and digit reversals (tangential).
What Appears To Remain Unknown

Whether there are infinitely many such (n). I found no proof or disproof.
Novelty Assessment

Potentially unexplored in formal literature, but closely related problems have been discussed. The absence of a direct paper is weak evidence.
Mathematical Significance

40
Probability That a Genuine Open Component Exists

50
Confidence in This Assessment

25 (low, due to reliance on StackExchange-level sources)
Main Risks

The problem may be solved in a paper on digit reversal not indexed by the search tools.
It may be considered trivial or recreational.
Candidate 5 (Round 1 Rank 5): Even integers as sums of two practical numbers

Problem

Is every sufficiently large even integer the sum of two practical numbers?
Classification

A — Already solved.
Prior Work

This is the Goldbach conjecture for practical numbers. Search results show that Melfi proved this conjecture: “every even positive integer is a sum of two practical numbers”. The proof is also reported in On Two Conjectures about Practical Numbers (ScienceDirect). The conjecture was raised in 1984 and proved by Melfi (2005, according to the Wikipedia result).
Closest Known Results

Melfi (2005): proof that every even positive integer is a sum of two practical numbers.
Margenstern verified the conjecture computationally for (2n < 100000).
Relevant Sources

Melfi, G., “On Two Conjectures about Practical Numbers,” Journal of Number Theory (or similar venue; the search result points to ScienceDirect). Verified via multiple search results.
Wikipedia entry on Giuseppe Melfi. Verified as a search result.
What Appears To Remain Unknown

Nothing regarding the main conjecture; it is solved.
Novelty Assessment

Not novel. The problem is solved.
Mathematical Significance

70 (for the solved theorem)
Probability That a Genuine Open Component Exists

5
Confidence in This Assessment

95
Main Risks

The proof may have gaps, but multiple sources report it as proved.
Candidate 6 (Round 1 Rank 6): Cycles of digit-square maps in base (b)

Problem

For a base (b \ge 2), consider the map (f_b(n) =) sum of squares of the base-(b) digits of (n). Classify all cycles of (f_b) for each (b), and determine for which (b) the map has a cycle of length greater than 1.
Classification

C — A closely related problem has already been studied.
Prior Work

OEIS A193585 records the “Number of cycles under iteration of sum of squares of digits in base (b)”. A 2023 arXiv paper by Walter A. Kehowski, “Fibonacci Cycles and Fixed Points,” studies (S_b(n)), the sum of squares of digits in base (b), and notes that the sequence terminates in a fixed point or enters a cycle. Stewart’s “Sums of Functions of Digits” (Canadian Journal of Mathematics, 2018) is a related classical reference.
Closest Known Results

OEIS A193585 provides cycle counts for various bases.
Kehowski (2023) discusses the general termination property.
Stewart (2018) studies general digit-sum functions.
Relevant Sources

OEIS A193585. Verified.
Kehowski, W. A., “Fibonacci Cycles and Fixed Points,” arXiv (2023). Verified via search result.
Stewart, B. M., “Sums of Functions of Digits,” Canadian Journal of Mathematics (2018). Verified via search result.
What Appears To Remain Unknown

A complete classification of cycles for all bases (b) may not be fully settled. The OEIS entry provides data for many bases, but a general theorem classifying cycle structure as a function of (b) may be absent.
Novelty Assessment

A closely related problem is studied; a complete general classification may remain partially open. The computational component is highly tractable.
Mathematical Significance

45
Probability That a Genuine Open Component Exists

40
Confidence in This Assessment

50
Main Risks

A general classification theorem may exist in the literature on digit functions.
The problem may be too computational and lack structural depth.
Candidate 7 (Round 1 Rank 7): Sum of proper divisors is a square

Problem

Let (s(n) = \sigma(n) - n) be the sum of proper divisors of (n). Are there infinitely many (n) such that (s(n)) is a perfect square?
Classification

C — A closely related problem has already been studied.
Prior Work

Search results show discussions of whether the sum of divisors (including (n)) can be a perfect square, in the context of Putnam problems and AoPS threads. I did not find a paper directly addressing the infinitude of (s(n)) being a square. The related question for (\sigma(n)) (including (n)) has been studied; the variant with proper divisors may be less explored.
Closest Known Results

Classical results on perfect numbers ((s(n)=n)) and abundant/deficient numbers.
Putnam 1974 A3: “Do there exist infinitely many positive integers such that the sum of the positive divisors … is a perfect square?” (search result 3). This is the (\sigma(n)) version, not (s(n)).
Relevant Sources

AoPS threads and Putnam problem references. Verified as search results, not formal literature.
Pollack’s notes on (s(n)) (search result 7). Verified as a search result.
What Appears To Remain Unknown

Whether infinitely many (n) have (s(n)) a perfect square. The (\sigma(n)) version is also studied but may not be fully resolved either.
Novelty Assessment

Potentially unexplored for the proper-divisor variant, but closely related to known divisor-sum problems.
Mathematical Significance

50
Probability That a Genuine Open Component Exists

45
Confidence in This Assessment

35
Main Risks

The problem may be solvable by elementary congruence arguments.
It may be a known exercise or competition problem.
Candidate 8 (Round 1 Rank 8): (\tau(n) = \tau(n+1)) infinitely often

Problem

Are there infinitely many (n) such that (\tau(n) = \tau(n+1)), where (\tau) is the number of positive divisors?
Classification

B — Already explicitly proposed or studied.
Prior Work

Search results for this exact question were poor; the search engine returned unrelated material on Ramanujan’s tau function and dynamical systems. However, the equality of divisor counts for consecutive integers is a known type of problem in number theory. I recall (without verified citation) that it is known to have infinitely many solutions, perhaps via elementary construction. I cannot verify this from the search results obtained.
Closest Known Results

The divisor function (\tau(n)) is multiplicative; local divisor counts can be manipulated via CRT.
It is known that (\tau(n)) takes the same value for infinitely many (n) (trivially), but consecutive equality is more subtle.
Relevant Sources

No directly relevant source found in the search results. This is a gap.
What Appears To Remain Unknown

Whether the set of (n) with (\tau(n)=\tau(n+1)) is infinite. I suspect this is known, but I lack verification.
Novelty Assessment

Likely already studied; novelty very uncertain.
Mathematical Significance

55
Probability That a Genuine Open Component Exists

20
Confidence in This Assessment

20 (very low)
Main Risks

The problem is likely solved by elementary CRT construction.
The search failed to find the relevant literature.
Candidate 9 (Round 1 Rank 9): Number of maximum Sidon sets is unbounded

Problem

Let (S(n)) be the maximum size of a Sidon set in ({1,\dots,n}). Is the number of maximum-size Sidon sets in ({1,\dots,n}) unbounded as (n\to\infty)?
Classification

C — A closely related problem has already been studied.
Prior Work

The number of Sidon sets (not necessarily maximum) is studied: it is known to be between (2^{(1.16+o(1))\sqrt{n}}) and (2^{(6.442+o(1))\sqrt{n}}). The maximum size of a Sidon set is ((1+o(1))\sqrt{n}). However, I did not find a result specifically on the number of maximum-size Sidon sets. The problem of classifying large Sidon sets is explicitly mentioned as an open direction in lecture notes: “Classify large (i.e., maximal or close to maximal) Sidon sets”.
Closest Known Results

Erdős–Turán, Singer, Chowla: maximum Sidon set size (\sim \sqrt{n}).
Counting all Sidon sets: exponential bounds.
Classification of large Sidon sets is stated as an open problem.
Relevant Sources

Lecture notes from UIUC (search result 0) and Oxford (search result 1). Verified as search results.
arXiv paper on generalized Sidon sets (search result 3). Verified.
What Appears To Remain Unknown

The number of maximum-size Sidon sets as a function of (n). The counting of all Sidon sets is studied, but the extremal counting may be less explored.
Novelty Assessment

Potentially unexplored sub-question within a studied area. The classification of large Sidon sets is explicitly open; counting maximum-size ones is a refinement.
Mathematical Significance

55
Probability That a Genuine Open Component Exists

60
Confidence in This Assessment

45
Main Risks

The answer may follow from known constructions of maximum Sidon sets.
The problem may be subsumed by the general classification of large Sidon sets.
Candidate 10 (Round 1 Rank 10): Burning number of trees

Problem

Is the burning number of every tree (T) of order (n) at most (\lceil\sqrt{n}\rceil)?
Classification

D — A known problem has been partially solved, but a potentially interesting special/general case remains.
Prior Work

The burning number conjecture states that for every connected graph (G) of order (n), (b(G) \le \lceil\sqrt{n}\rceil). It is known that it suffices to prove this for trees. The conjecture remains open for trees in general. Recent work has proved it for special classes: trees without degree-2 vertices (Murakami, 2024), and trees with at most (\lfloor\sqrt{n-1}\rfloor) degree-2 vertices. A 2026 paper claims to prove it for trees with at most (n-1) degree-2 vertices, but that bound appears weaker than the full conjecture.
Closest Known Results

The conjecture is reduced to trees.
Proved for trees without degree-2 vertices.
Proved for trees with few degree-2 vertices.
Still open for general trees.
Relevant Sources

arXiv papers on the burning number conjecture for trees (search results 0–6). Verified via search results.
The original conjecture is attributed to Bonato et al. (2016 or earlier).
What Appears To Remain Unknown

The conjecture for trees with many degree-2 vertices (e.g., paths, caterpillars, general trees).
Novelty Assessment

Known open problem; not novel, but a genuine open component remains.
Mathematical Significance

65
Probability That a Genuine Open Component Exists

90
Confidence in This Assessment

85
Main Risks

The 2026 paper may have resolved more cases than the search snippet indicates.
The problem is already well known; novelty is zero.
FINAL RANKING: Top 3 Candidates for Further Investigation

Rank 1: Candidate 10 — Burning number of trees (D)

1. Precise mathematical question

Is the burning number of every tree (T) of order (n) at most (\lceil\sqrt{n}\rceil)?
2. What is definitely known

The conjecture holds for all connected graphs if it holds for trees. It is proved for trees without degree-2 vertices (Murakami 2024) and for trees with few degree-2 vertices. It remains open for general trees.
3. What appears to remain unknown

The conjecture for trees with many degree-2 vertices, including paths and caterpillars with many degree-2 vertices.
4. Strongest evidence that it may contain an open component

Multiple recent papers explicitly state that the conjecture remains open for trees in general. New partial results continue to appear (2024, 2026).
5. Strongest evidence against novelty

This is a known open problem, not a novel one. The novelty lies only in potentially finding a new proof technique or a new special case.
6. Most important papers to inspect

Murakami (2024): proof for trees without degree-2 vertices.
The 2026 Graphs and Combinatorics paper on trees with few degree-2 vertices.
The original conjecture paper (Bonato et al.).
7. What another independent mathematician/AI should verify next

Check whether the 2026 paper actually proves the full conjecture or only a restricted case. Search for any 2025–2026 arXiv preprints claiming a full proof.
Rank 2: Candidate 3 — Yellowstone permutation surjectivity (B)

1. Precise mathematical question

Is the Yellowstone permutation (OEIS A098550) a permutation of the positive integers?
2. What is definitely known

The sequence is infinite. It is closely related to the Enots Wolley sequence (A336957), for which surjectivity is explicitly stated as open.
3. What appears to remain unknown

Whether every positive integer appears in the Yellowstone permutation.
4. Strongest evidence that it may contain an open component

The 2015 paper defines the sequence and proves infinitude but does not, according to search results, prove surjectivity. The binary analog paper explicitly states surjectivity is open for the closely related Enots Wolley sequence.
5. Strongest evidence against novelty

The problem is already known and studied. It is not novel; it is an existing open problem.
6. Most important papers to inspect

Applegate, Pol, Sloane, et al., “The Yellowstone Permutation,” arXiv:1501.01669 (2015).
The binary analog paper on the Enots Wolley sequence.
OEIS A098550 and A336957.
7. What another independent mathematician/AI should verify next

Search arXiv and Google Scholar for any 2020–2026 paper proving surjectivity of the Yellowstone permutation. Check whether the 2015 paper’s “Theorem” list includes a surjectivity proof that the search snippets missed.
Rank 3: Candidate 9 — Number of maximum Sidon sets is unbounded (C)

1. Precise mathematical question

Is the number of maximum-size Sidon sets in ({1,\dots,n}) unbounded as (n\to\infty)?
2. What is definitely known

The maximum size of a Sidon set in ([n]) is ((1+o(1))\sqrt{n}). The total number of Sidon sets is between (2^{(1.16+o(1))\sqrt{n}}) and (2^{(6.442+o(1))\sqrt{n}}). Classification of large Sidon sets is an open direction.
3. What appears to remain unknown

The number of maximum-size Sidon sets specifically, and whether it is unbounded.
4. Strongest evidence that it may contain an open component

Lecture notes explicitly list “Classify large (i.e., maximal or close to maximal) Sidon sets” as an open problem. Counting maximum-size sets is a refinement of this classification.
5. Strongest evidence against novelty

The problem is a sub-question of a studied area. A construction of infinitely many maximum Sidon sets may already exist implicitly in the literature on Singer difference sets.
6. Most important papers to inspect

Erdős–Turán (1941) on Sidon sets.
Singer (1938) on perfect difference sets.
The arXiv paper on the number of generalized Sidon sets.
Lecture notes stating the classification problem.
7. What another independent mathematician/AI should verify next

Search for “number of maximum Sidon sets” and “counting maximal Sidon sets” in arXiv and Google Scholar. Check whether constructions of maximum Sidon sets (e.g., via finite fields) yield infinitely many distinct sets as (n) varies.
FINAL WARNING

None of the above candidates can be declared “definitely a new open problem.” The strongest genuine open component is the burning number conjecture for trees (Candidate 10), which is a known open problem, not a novel one. The Yellowstone permutation surjectivity (Candidate 3) is also a known open problem in a specialized area. The Van Eck sequence surjectivity (Candidate 1) is potentially open, but not independently verified; its absence from search results is weak evidence. All other candidates are either solved (EKG, practical numbers), closely related to studied problems, or too uncertain to classify confidently. A rigorous literature search with direct access to arXiv, MathSciNet, and OEIS is essential before any novelty claim can be made.
