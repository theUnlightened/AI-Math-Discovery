# DeepSeek Round 1

## Date

2026-10-08

## Purpose

Generate potentially interesting mathematical research questions
without using external literature.

## Model

DeepSeek

## Configuration

- DeepThink: ON
- Web Search: OFF


## Prompt

You are an expert mathematical researcher specializing in mathematical problem discovery.

LANGUAGE REQUIREMENT:
Think and respond entirely in English.
Use standard mathematical terminology and formal academic English.
Do not switch to Chinese unless explicitly requested.

MY GOAL:

I want to discover a small, precise, potentially unexplored mathematical problem. I am NOT looking for famous open problems such as the Riemann Hypothesis, Goldbach's Conjecture, or the Twin Prime Conjecture.

I want to explore the possibility of discovering a genuinely interesting "small open problem" or an overlooked mathematical question.

IMPORTANT:
At this stage, DO NOT use web search or external literature search. I want you to explore the mathematical problem space independently first, without being constrained by search results.

RESEARCH AREAS:

Prioritize:

1. Elementary number theory
2. Combinatorics
3. Graph theory
4. Integer sequences and recurrences
5. Discrete mathematics
6. Elementary probability
7. Mathematics and algorithms
8. Discrete dynamical systems
9. Extremal problems
10. Properties of computationally generated mathematical structures

Prefer problems that can be stated precisely using elementary or undergraduate-level mathematics.

WHAT I WANT YOU TO LOOK FOR:

Do NOT simply invent random mathematical questions.

Instead, search conceptually for potential gaps arising from:

* Natural generalizations of known theorems
* Variants of known conjectures
* Boundary cases of known results
* Special parameter cases that have not obviously been settled
* Interesting patterns in integer sequences
* Properties of recursively defined objects
* Extremal questions in graphs or combinatorial structures
* Interactions between two well-known mathematical structures
* Questions suggested by computational experiments
* Statements that are obvious for small cases but unclear in general
* Questions where a known theorem seems "almost" strong enough, but leaves a small unexplored case

The ideal candidate should be:

* Mathematically precise
* Non-trivial
* Small enough to understand clearly
* Potentially computationally testable
* Potentially connected to existing mathematics
* Interesting even if the original conjecture turns out to be false

DO NOT optimize for difficulty.
I prefer a small, sharp, well-defined problem over a grand but vague problem.

IMPORTANT EPISTEMIC RULE:

You MUST NOT claim that a problem is genuinely open merely because you personally do not know a solution.

At this stage, use phrases such as:

* "potentially unexplored"
* "possibly open"
* "requires literature verification"
* "I am not currently aware of a solution"

Do NOT fabricate mathematical papers, mathematicians, theorems, conjectures, or historical facts.

If you are uncertain about something, explicitly say so.

TASK:

Generate at least 50 candidate mathematical research problems.

For each candidate, use the following structure:

### Candidate X

**Problem:**
State the mathematical question precisely.

**Mathematical origin:**
Explain what mathematical structure, theorem, sequence, conjecture, or phenomenon inspired it.

**Known intuition:**
Explain what appears to be known or strongly suggested from standard mathematical knowledge.

**Unknown aspect:**
Identify exactly what remains unclear.

**Why it is interesting:**
Explain its mathematical significance.

**Computational tractability:**
Explain whether finite computational experiments could investigate it.

**Potential counterexamples:**
Describe where a counterexample might plausibly occur.

**Possible research directions:**
Suggest possible ways the problem might be attacked.

**Novelty risk:**
Explain why this may already have been studied.

Then assign:

* Novelty Potential: 0–100
* Mathematical Significance: 0–100
* Computational Tractability: 0–100
* Potential for an Overlooked Question: 0–100

After generating all candidates, perform a SECOND INTERNAL FILTER.

Eliminate candidates that are:

* Clearly trivial
* Obviously false
* Clearly solved by elementary results
* Merely restatements of famous theorems
* Merely cosmetic reformulations of known problems
* Too vague to constitute a mathematical problem
* Too broad to investigate meaningfully
* Mathematically uninteresting

Then select the 10 strongest candidates.

For the final 10, provide a ranking from 1 to 10 and explain why each candidate deserves further investigation.

At the very end, identify the 3 candidates that you believe are the most promising for a subsequent literature-search stage.

REMEMBER:

This is a discovery stage, not a proof stage.

Do not force a proof.
Do not force novelty.
Do not pretend certainty where none exists.

The objective is to produce a high-quality pool of potentially interesting mathematical questions that can later be subjected to rigorous literature verification.


---

## Original Thought
We need answer as mathematical researcher. Need generate at least 50 candidate problems with structure, then filter to 10 strongest, ranking, final 3. Need no web search. Must be precise, not claim open. Need probably produce long answer. Need think carefully. We have lots of tokens. Need generate 50 candidates across areas. We need ensure each has all fields: Problem, origin, known intuition, unknown aspect, why interesting, computational tractability, potential counterexamples, possible research directions, novelty risk, scores. Then second filter eliminate and select 10. Then ranking and top 3. This is large. Need manage length. Desired oververbose 5, but task demands 50 candidates. We need provide sufficient detail but not enormous. We can compress each candidate but include all required. Need ensure at least 50. Maybe 55 candidates. Then final 10. Need be precise. Could use a numbered list with subsections. Need no fake citations. Use phrases "I am not currently aware..." etc.

We need think of candidate problems. Need not be famous open. Small, precise, elementary. We can generate from number theory, combinatorics, graph theory, sequences, discrete math, probability, algorithms, dynamical systems, extremal.

We need avoid obviously trivial/false. Need likely non-trivial. We can formulate as conjectures/questions. We don't need solve. Need scores.

Let's brainstorm candidate problems.

Areas:

Elementary number theory:

For n, define s(n) sum of proper divisors? Aliquot? Small open? Maybe "Is there n such that aliquot sequence reaches a perfect number after exactly k steps?" Not precise.

Generalization of Euclid: primes dividing n^2+n+1?

Egyptian fractions: For every n, can 1 be expressed as sum of n unit fractions with odd denominators? There are known.

Goldbach variants avoid famous? e.g., every odd integer >? is sum of prime and twice a square? Hardy-Littlewood? Famous.

Sequence: a(n) = smallest k such that n divides Fibonacci(k). Rank of apparition. Question: are there infinitely many n for which z(n) = z(n+1)? Small? Could be computational.

For prime p, Wilson quotient.

Number of partitions into distinct parts vs odd parts. Euler theorem. Generalization modulo m? E.g., partitions into parts congruent to certain residues.

"Niven numbers" (Harshad) consecutive? There are arbitrarily long? Known?

"Smith numbers" consecutive?

"Practical numbers" and Goldbach?

"Untouchable numbers" gaps?

"Euler totient valence": smallest n with exactly k solutions to phi(x)=n?

"Multiplicative persistence" is famous? base 10 open? Maybe base 2?

"Additive persistence" known?

"Collatz" avoid famous.

Combinatorics:

Ramsey numbers small? Known open many.

"Anti-Ramsey" numbers for paths/cycles in small graphs.

"Zero-sum problems" over groups.

"Davenport constant" for non-abelian?

"Sidon sets" in intervals: maximum size? Known bounds. Question about perfect difference sets?

"Sum-free sets" in [n]: maximum size known. But number of maximum sum-free sets?

"Cap sets" in finite vector spaces? Famous.

"Latin squares": number of transversals?

"Permutations avoiding patterns": consecutive patterns?

"Graph pebbling": pebbling number of product of paths?

"Domination number" of graph products?

"Graceful labelings" of trees? Ringel-Kotzig? Famous.

"Harmonious labelings" of specific families.

"Edge irregularity strength" of graphs.

"1-2-3 Conjecture" solved?

"Total coloring" conjecture? Famous.

"List coloring" of planar graphs?

"Cops and robbers" on graphs: cop number of product?

"Firefighter problem" on grids?

"Graph burning number" of trees?

"Boolean satisfiability threshold" small.

Integer sequences:

Recamán's sequence? Famous.

Hofstadter Q?

Somos sequences?

"Look-and-say" lengths? Conway known.

"Van Eck sequence" patterns?

"EKG sequence" primes?

"Yellowstone permutation" primes?

"Kolakoski sequence"?

"Sylow?".

Graph theory:

"Halin graphs Hamiltonian"? known.

"Cubic graphs with no bridges": perfect matching? Petersen theorem.

"Chromatic number of unit distance graphs" famous.

"Hadwiger-Nelson" famous.

"Erdos-Hajnal" property for specific classes.

"Induced Ramsey numbers" for paths.

"Treewidth of random graphs" known.

"Diameter of random Apollonian networks"?

"Algebraic connectivity of trees with given degree sequence"?

"Spectral radius of graphs with given independence number"?

Discrete dynamical systems:

Cellular automata: Rule 30? Famous.

Iteration of arithmetic functions: sum of squares of digits. Known happy numbers. Question: how many cycles in base b? For bases? Could be small. E.g., sum of squares of digits in base b. For base 10 cycles known. For general b, are there always cycles? maybe.

Sum of cubes of digits?

"Kaprekar routine" for n digits. For 4 digits known. For general n?

"Ducci sequences" over integers. Known eventually periodic? For n power of 2? For other n? Could be open.

"Collatz-like maps" avoid.

Probability:

Random Fibonacci sequences growth? Known.

"Random permutation longest increasing subsequence" known.

"Coupon collector with two collectors"?

"Random walk on graph hitting time" for specific graphs.

"Benford's law" sequences.

Algorithms:

Sorting with restricted comparisons?

"Pancake sorting" for burnt pancakes?

"Minimum number of comparisons to find median" small n?

"Graph coloring reconfiguration" connectivity?

We need 50 candidates. Could pick 50 and write compact. Need final 10. We can generate many from specific families. But ensure precise and not too vague. We can state as questions.

Maybe better to have candidates with same template but concise. Need at least 50. We can number 1-55. For each, write Problem, origin, known intuition, unknown aspect, why interesting, computational tractability, potential counterexamples, possible research directions, novelty risk, scores. That's 9 fields per candidate. 50*9 = 450 items. That's huge. Need maybe compress each into a paragraph with labels. But task explicitly says use structure. We can use a table? A table with columns might be too wide. But can use compact bullet labels. Need final answer not overly massive? It will be long. We can reduce by using short sentences. 50 candidates * maybe 150 words = 7500 words. That's okay maybe. But token limit? We have 768 juice, not actual token. We can produce ~10k words? Might be okay. But final answer desired oververbosity 5. However task demands 50. We can use a compressed format: each candidate as:

Candidate 1
Problem: ...
Origin: ...
Known intuition: ...
Unknown: ...
Interest: ...
Computation: ...
Counterexamples: ...
Directions: ...
Novelty risk: ...
Scores: NP=.. MS=.. CT=.. OQ=..

That's 10 lines. 50*10=500 lines. Could be long but acceptable. We can maybe group candidates by area and use semicolon-separated fields. Need ensure all required.

Maybe we can generate 50 but not too detailed. For final 10, provide ranking and explanation. Then top 3.

Need be careful not to claim open. Use "potentially unexplored", "I am not aware", "requires literature verification".

Let's design candidate list. I'll create 55 candidates. Need ensure each is mathematically precise.

Let's start drafting.

Candidate 1: Sum-free sets with exactly k pairs?
Problem: For each n, let f(n) be number of maximum-size sum-free subsets of {1,...,n}. Determine whether f(n) is unbounded? Actually maximum sum-free size ceil(n/2). Number of maximum sum-free sets? For odd n, maximum sum-free sets are odd numbers? Wait sum-free set no x+y=z within set. Maximum size ceil(n/2). For [n], maximum sum-free sets: if n=2m, all odds size m, also numbers > m size m? Actually {m+1,...,2m} size m sum-free. For odd 2m+1, max size m+1: odds {1,3,...,2m+1} size m+1; also {m+1,...,2m+1}? size m+1. Number of maximum sum-free sets? Known: for n odd, only odds? Let's recall. Sum-free subsets of [n] maximum. For n=5, max size 3. Sets: {1,3,5}? 1+3=4 not, 1+5=6, 3+5=8, sum-free yes. {2,3,5}? 2+3=5 no, not. {3,4,5}? 3+4=7. {1,4,5}? 1+4=5 no. So odds only? For n=6, max size 3: odds {1,3,5}; upper half {4,5,6}? 4+5=9; sum-free. Are there others? So number small. Not interesting.

Maybe "number of maximal sum-free sets" known? Could be.

Candidate 2: Practical numbers: Is every even number a sum of two practical numbers? This is Goldbach analogue. Practical numbers density? I think known: every even number is sum of two practical numbers? Maybe solved? Not sure. This might be open? Actually practical numbers: every even number is sum of two practical numbers? I recall conjecture by Margenstern? Maybe known? We can include but risk known. Use "potentially unexplored".

Candidate 3: Untouchable numbers: Are there infinitely many pairs of consecutive untouchable numbers? Untouchable numbers are not in image of sum of proper divisors. Known infinite? Consecutive? Computational.

Candidate 4: For n, define f(n)=sum of squares of divisors. Is f(n) a square infinitely often? e.g., n=1. σ_2(n). This is sum of squares of divisors. Are there infinitely many n such that σ_2(n) is a perfect square? I think this is an open problem? Might be. Small.

Candidate 5: For n, let φ(n) be Euler totient. Are there infinitely many n such that φ(n) = φ(n+1)? Known? This is a known open? I think φ(n)=φ(n+1) has solutions, infinitely many unknown? Maybe famous? It is a known problem. Avoid? It's not as famous as RH but known open. We can include but mark.

Candidate 6: Are there infinitely many n such that τ(n)=τ(n+1)? Number of divisors. Known? I think open? There are results. Could be.

Candidate 7: Aliquot sequences: Is there an n such that aliquot sequence starting at n enters a cycle other than 1, 6, 28, etc? This is Catalan-Dickson conjecture? Famous.

Candidate 8: "Euler's idoneal numbers": Are there exactly 65? Famous.

Candidate 9: "Giuga numbers": Are there infinitely many? Famous.

Candidate 10: "Primary pseudoperfect numbers": finite? Famous.

Need small overlooked. Maybe focus on specific sequences.

Candidate: "Take the sequence a(n) = n + reverse(n) in base 10. Are there infinitely many n such that a(n) is prime?" This is not too famous. Could be computational. Or "n + reverse(n) is a square". Known? Let's think. For n, n+rev(n). Are there infinitely many squares? Example 12+21=33 no. 10+01=11. This is a small problem. Could be open? Maybe easy? If n has digits, rev(n) ≡ n mod 9, so sum ≡ 2n mod 9. Square mod 9 can be 0,1,4,7. So n mod 9 restricted. Could be infinite? Not obvious. Computational tractable.

Candidate: "For base b, are there infinitely many n such that n + reverse_b(n) is a perfect square?" Could be.

Candidate: "Multiplicative persistence in base 2" is known? In base 2, product of digits is 1 if all ones else 0, so persistence at most 1. Not.

Candidate: "Additive persistence" known.

Candidate: "Kaprekar constants for n digits in base 10." For n=3, 495; n=4, 6174. For n>4? Known? Actually Kaprekar routine for n digits: for n=5, constants? There are cycles? This is studied. But maybe for base b? Could be.

Candidate: "Ducci sequences" for length n not power of 2. Over integers, Ducci sequence is map (a1,...,an) -> (|a1-a2|,...,|an-a1|). Does every integer Ducci sequence reach zero? Known for n power of 2? For n not power of 2, there are cycles? I recall open? This is a known problem. Could be.

Candidate: "Recamán's sequence: are there infinitely many positive integers missing?" Famous? Recamán is known open.

Candidate: "Van Eck sequence: does every positive integer appear?" I think open? Van Eck sequence starts 0,0,1,0,2,0,2,2,1,... Question whether every number appears. This is a known open problem? Possibly. But not famous. Could include.

Candidate: "EKG sequence: does every positive integer appear?" Known? EKG sequence (a(1)=1,a(2)=2, a(n) smallest unused sharing factor with previous). It is conjectured to be a permutation. I think open? Known? Could be.

Candidate: "Yellowstone permutation: does every positive integer appear?" Known open? Yellowstone permutation is similar. Could include.

Candidate: "Somos sequences: integrality for certain parameters." Famous.

Candidate: "Hofstadter Q: does Q(n) exist for all n?" Famous? Actually Q(n) defined recursively Q(1)=Q(2)=1, Q(n)=Q(n-Q(n-1))+Q(n-Q(n-2)). It is not known if defined for all n? I think it is known that Q(n) < n for all n? Wait Hofstadter Q sequence is known to be well-defined? There was a proof? I recall Q(n) is defined for all n? Actually it's an open problem? Let's not.

Combinatorics:

"Number of permutations avoiding a set of patterns of length 3" known.

"Consecutive pattern avoidance" e.g., permutations avoiding 123 consecutively. Known.

"Stack-sortable permutations" known.

"Permutations with no 3-term arithmetic progression" maybe.

Graph theory:

"Graceful labeling of trees" famous.

"Harmonious labeling of trees" famous.

"Magic labeling" maybe.

"Prime labeling of graphs" open for many.

"Vertex magic total labeling" for specific graphs.

"1-2-3 conjecture" solved 2023? Maybe.

"Cops and robbers on Cartesian product of trees": cop number of product? There is conjecture: cop number of Cartesian product of two trees is at most 2? Actually cop number of Cartesian product of two trees is at most 2? I recall: cop number of Cartesian product of trees is at most 2? There is a known result: cop number of product of two trees ≤ 2? Wait, cop number of a tree is 1. Product of two trees can have cop number up to? I think cop number of Cartesian product of two trees is at most 2? There is a conjecture by Nowakowski and Winkler? Might be open. Could include.

"Graph burning number of trees": known? Burning number of a tree can be computed? There is a conjecture that burning number of a tree ≤ ceil((diameter+1)/2)? Actually for paths. For trees, burning number ≤? There is a conjecture by Bonato et al. Could be open.

"Domination number of Cartesian product of paths": exact formula known? For P_m □ P_n, domination number is floor((m+2)(n+2)/5)-4? Known? Actually for grids, domination number exact for many but not all? There is a famous problem: domination number of grid graphs. Exact formula known? I think for m,n large, γ(G_{m,n}) = floor((m+2)(n+2)/5)-4 except some small? This was solved? Maybe.

"Independence number of hypercubes": known.

"Chromatic number of square of planar graph": known.

"Total coloring conjecture": famous.

"Erdos-Faber-Lovasz": solved.

Integer sequences:

"Number of partitions of n into prime parts": asymptotics known.

"Partitions into distinct parts with difference at least d": known.

"Rogers-Ramanujan" famous.

"Cranks and ranks": famous.

"Andrews-Gordon identities": known.

Maybe we can formulate small questions about specific sequences and their properties.

Need 50 candidates. We can generate from many areas. Let's systematically list 55 candidates with precise questions.

I'll number and give compact fields. Need final 10. Let's build a list:

n + reverse(n) square infinitely often in base 10.

n + reverse(n) prime infinitely often in base 10.

n - reverse(n) divides n? or is a square?

Sum of proper divisors is a perfect square infinitely often.

Number of divisors of n equals number of divisors of n+1 infinitely often.

Euler totient of n equals Euler totient of n+2 infinitely often.

Practical numbers: every even integer is sum of two practical numbers.

Untouchable numbers: infinitely many consecutive pairs.

Aliquot sequences: existence of a cycle of length >2 other than known? (famous but can include)

Iterated sum of squares of digits in base b: for which b are there non-trivial cycles? Known for b up to?

Iterated sum of cubes of digits: are there infinitely many n reaching a fixed point?

Kaprekar routine in base b for n digits: number of fixed points/cycles as function of n.

Ducci sequences over integers for length n not power of 2: do all reach zero? (known open? include)

Van Eck sequence: does every positive integer occur?

EKG sequence: is it a permutation of positive integers?

Yellowstone permutation: is it a permutation?

Recamán: are there infinitely many missing? (famous)

Look-and-say: lengths in base b other than 10? Conway's cosmological theorem for base 10; for other bases?

Hofstadter Q: is Q(n) defined for all n? (maybe known)

Somos-4 integrality over integers? known.

Number of maximum sum-free subsets of [n] is bounded?

Number of maximal sum-free subsets of [n] asymptotics?

Sidon sets in [n]: maximum size known ~sqrt(n). Number of maximum Sidon sets?

Difference sets in Z_n: existence of perfect difference sets for parameters? Famous.

Costas arrays: existence for all orders? Famous open? Yes.

Permutations avoiding consecutive pattern 123: enumeration known. Question: number of permutations avoiding two consecutive patterns?

Permutations with no 3-term arithmetic progression in values and positions?

Latin squares: number of transversals in cyclic Latin squares of odd order. Known? There is conjecture.

Latin squares: existence of complete mappings for all groups? Hall-Paige conjecture solved?

Zero-sum problems: Davenport constant of non-abelian groups.

Ramsey numbers for books: R(B_m, B_n) exact? Known for some.

Ramsey numbers for cycles: R(C_m, C_n) known? Many.

Induced Ramsey numbers for paths: known?

Graph burning number of trees: exact formula?

Cop number of Cartesian product of two trees: is it at most 2?

Cop number of Cartesian product of a tree and a cycle?

Domination number of grid graphs: exact for all m,n? (maybe solved)

Total domination number of hypercubes: exact? Known?

Graceful labeling of trees: known open? (famous)

Harmonious labeling of trees: known open?

Prime labeling of trees: open?

Edge irregularity strength of paths and cycles: exact? Known.

List chromatic number of bipartite planar graphs: known?

Chromatic number of square of planar graphs: known.

Hadwiger number of random graphs?

Treewidth of random cubic graphs?

Algebraic connectivity of trees with given degree sequence: extremal?

Spectral radius of graphs with given independence number: extremal?

Number of spanning trees in grid graphs: asymptotics known. Exact formula for m x n?

Number of perfect matchings in grid graphs: exact?

Random Fibonacci sequences: growth rate known. Question: distribution of signs?

Random walk on Z: hitting time of a moving boundary?

Coupon collector with unequal probabilities: exact expected time for specific distributions?

Benford's law for sequences: does n! follow Benford? Known.

Pancake sorting: exact number for burnt pancakes? Known?

Minimum comparisons to sort with restricted comparisons?

Graph coloring reconfiguration: connectivity of k-colorings of planar graphs?

SAT threshold for random 3-SAT: famous.

Firefighter problem on grids: exact number of saved vertices?

Graph pebbling: pebbling number of product of paths?

We need 50. We can choose 50 from these. Need ensure each has all fields. That's a lot. Maybe we can produce 50 but with very concise fields. Let's aim for 50 candidates. Then final filter to 10. We can use a table-like format.

But before final, need think if some are too famous. The prompt says not famous open problems like RH, Goldbach, Twin Prime. But other known open problems might be acceptable? It says "I am NOT looking for famous open problems such as..." So we should avoid very famous ones. But we can include some less famous known open. However final 10 should be potentially unexplored. Need maybe focus on obscure.

Maybe we can create more original candidates by combining structures. But we can't verify novelty. We can state "potentially unexplored".

Let's design 50 candidates with precise problems. I'll write them compactly. Use labels: P, O, KI, U, I, CT, PC, RD, NR, Scores. That's 10 lines. For 50, maybe 500 lines. Okay.

We can group final 10 after.

Let's start composing.

Candidate 1:
Problem: For base 10, let r(n) be digit reversal. Are there infinitely many n such that n + r(n) is a square?
Origin: Palindromic and reversal sequences.
Known: For n<10^k, r(n) ≡ n mod 9, so sum ≡ 2n mod 9; squares mod 9 restrict n. Many small solutions.
Unknown: Infinitude and density.
Interest: Elementary Diophantine with digit constraints.
CT: Easy to test up to large ranges.
PC: Might be finite due to modular obstructions? e.g., n=0,1? Check: n=2 -> 2+2=4 square. n=8 -> 16 square. n=29 -> 29+92=121. So many.
RD: Construct via n = (a^2)/2? Use digit equations.
NR: Likely studied as reverse multiples.
Scores: NP 60, MS 40, CT 90, OQ 70.

Candidate 2: n + rev(n) prime infinitely often.
Similar.

Candidate 3: n - rev(n) is a square infinitely often? e.g., 10-01=9.
Candidate 4: Sum of proper divisors σ(n)-n is a perfect square infinitely often.
Candidate 5: τ(n)=τ(n+1) infinitely often.
Candidate 6: φ(n)=φ(n+2) infinitely often.
Candidate 7: Every even integer is sum of two practical numbers.
Candidate 8: Infinitely many consecutive untouchable numbers.
Candidate 9: Aliquot cycles other than known.
Candidate 10: Sum of squares of digits in base b: for which b is there a cycle of length >1?
Candidate 11: Sum of cubes of digits: are there infinitely many n reaching 1?
Candidate 12: Kaprekar routine in base b: number of cycles for n digits.
Candidate 13: Ducci sequences length n not power of 2: do all integer sequences reach zero?
Candidate 14: Van Eck sequence: does every positive integer occur?
Candidate 15: EKG sequence: is it a permutation?
Candidate 16: Yellowstone permutation: is it a permutation?
Candidate 17: Recamán: are there infinitely many missing? (maybe too famous)
Candidate 18: Look-and-say in base b: do lengths grow exponentially for all b?
Candidate 19: Hofstadter Q: is it defined for all n?
Candidate 20: Somos-4: integrality for all initial values? (known? no)
Candidate 21: Number of maximum sum-free subsets of [n] is bounded by polynomial?
Candidate 22: Number of maximal sum-free subsets of [n] asymptotics.
Candidate 23: Number of maximum Sidon subsets of [n] is unbounded?
Candidate 24: Existence of perfect difference sets for infinitely many parameters?
Candidate 25: Costas arrays exist for all orders? (famous open)
Candidate 26: Permutations avoiding two consecutive patterns: enumerate for all pairs.
Candidate 27: Permutations with no 3-term AP in positions and values.
Candidate 28: Number of transversals in cyclic Latin squares of odd order.
Candidate 29: Complete mappings for all finite groups? (Hall-Paige solved? actually solved 2009)
Candidate 30: Davenport constant for non-abelian groups of order 2p?
Candidate 31: Ramsey numbers for books: exact for B_m vs B_n?
Candidate 32: Ramsey numbers for cycles: exact for C_m vs C_n?
Candidate 33: Induced Ramsey numbers for paths: exact?
Candidate 34: Burning number of trees: is it ≤ ceil((diam+1)/2)?
Candidate 35: Cop number of Cartesian product of two trees ≤ 2?
Candidate 36: Cop number of Cartesian product of tree and cycle?
Candidate 37: Domination number of grid graphs: exact formula?
Candidate 38: Total domination number of hypercubes: exact?
Candidate 39: Graceful labeling of trees: all trees graceful?
Candidate 40: Harmonious labeling of trees: all trees harmonious?
Candidate 41: Prime labeling of trees: all trees prime?
Candidate 42: Edge irregularity strength of paths and cycles: exact?
Candidate 43: List chromatic number of bipartite planar graphs: is it 3?
Candidate 44: Chromatic number of square of planar graphs: max 8? (known)
Candidate 45: Hadwiger number of random graphs: threshold?
Candidate 46: Treewidth of random cubic graphs: linear?
Candidate 47: Algebraic connectivity of trees with given degree sequence: extremal?
Candidate 48: Spectral radius of graphs with given independence number: extremal?
Candidate 49: Number of spanning trees in grid graphs: exact formula?
Candidate 50: Number of perfect matchings in grid graphs: exact formula?
Candidate 51: Random Fibonacci sequences: growth rate? (known)
Candidate 52: Random walk hitting time of moving boundary.
Candidate 53: Coupon collector with two coupons at a time.
Candidate 54: Benford's law for n! (known)
Candidate 55: Pancake sorting: exact for burnt pancakes.
Candidate 56: Minimum comparisons to find median for n=7?
Candidate 57: Reconfiguration of k-colorings of planar graphs.
Candidate 58: Firefighter on grids: exact saved vertices.
Candidate 59: Graph pebbling number of product of paths.
Candidate 60: Zero-sum constants for symmetric groups.

We need 50. I can pick 50 from these. But need each with fields. Maybe we can reduce fields by grouping? The task says "For each candidate, use following structure". So must include. We can make fields very short.

Maybe we can produce 50 candidates but with bullet labels. This will be lengthy. Let's write efficiently.

I need ensure final 10 selection. The final 10 should be the strongest. I can choose candidates that are small, precise, computationally testable, potentially overlooked. E.g., n+rev(n) square, sum of proper divisors square, τ(n)=τ(n+1), φ(n)=φ(n+2), consecutive untouchable, sum of squares of digits in base b, Ducci length not power of 2, Van Eck every integer, EKG permutation, burning number of trees, cop number product of trees, edge irregularity strength of paths/cycles, etc.

But some are known open. Need final top 3 most promising for literature search. Maybe:

Van Eck sequence: does every positive integer occur? (computational, sequence)

Ducci sequences for lengths not power of 2 over integers: do all reach zero? (dynamical)

Cop number of Cartesian product of two trees is at most 2? (graph theory)

n+rev(n) square infinitely often? (number theory)

Sum of proper divisors is square infinitely often? (number theory)

Need pick 3. Maybe Van Eck, Ducci, cop number product of trees. But Ducci is known open? Actually Ducci sequences: for n not power of 2, there are cycles? I recall: For integer Ducci sequences, if n is a power of 2, every sequence reaches (0,...,0). For other n, there are periodic sequences not all zero? I think it's known that for n not a power of 2, there exist cycles? Wait, Ducci sequences over integers: map T(x)i = |x_i - x{i+1}|. It is known that if n is a power of 2, every integer sequence reaches zero. If n is not a power of 2, there exist sequences that do not reach zero (e.g., (0,1,0,1) for n=4? n=4 power of 2, reaches zero? (0,1,0,1)->(1,1,1,1)->(0,0,0,0). For n=3, (0,1,1)->(1,0,1)->(1,1,0)->(0,1,1) cycle length 3. So known. So not open. Remove.

Cop number of Cartesian product of two trees: I think it's known that cop number ≤ 2? Actually there is a theorem: The cop number of the Cartesian product of two trees is at most 2. I recall a paper "The cop number of the Cartesian product of two trees" maybe solved. So not.

Van Eck sequence: I think it's open whether every number appears. That's a known open problem? It might be. But not famous. Could be.

Maybe "EKG sequence is a permutation" is open? I think it's conjectured but not proven. Known? There are results. Could be.

"Yellowstone permutation is a permutation" is open? Yes.

"Recamán's sequence" famous open.

Maybe "n + rev(n) is a square infinitely often" is likely open? Could be. Let's check: n + rev(n) = 2 * something? For n with digits a_k...a_0, sum = Σ (a_i + a_{k-i}) 10^i. Not symmetric. There are infinitely many? We can construct n=2*10^m? 20+02=22 not square. n=8, 8+8=16. n=29, 29+92=121. n=38, 38+83=121. n=47, 47+74=121. n=56, 56+65=121. n=65, 65+56=121. n=74, 74+47=121. n=83, 83+38=121. n=92, 92+29=121. So for two digits, n+rev(n)=11(a+b). Square if a+b=11? 11*11=121. So all two-digit with sum 11. For three digits, n=100a+10b+c, rev=100c+10b+a, sum=101(a+c)+20b. Can be square. Are there infinitely many? We can set b=0, need 101(a+c) square. 101 is prime, so a+c=101k^2? But a+c≤18, so only k=0. So no b=0. With b, 101(a+c)+20b. Since a+c≤18, sum ≤ 10118+180=1998. So for 3 digits, finite. For larger digits, possible. Infinitude not obvious. Could be open. Good.

Another: "Are there infinitely many n such that n + reverse(n) is a palindrome?" Known?

Maybe "number of divisors of n equals number of divisors of n+1" is known open? I think it's open whether infinitely many. Yes, it's a known problem. But not super famous.

"Euler totient of n equals Euler totient of n+2" is open? I think infinitely many n with φ(n)=φ(n+1) is open. φ(n)=φ(n+2) maybe.

"Sum of proper divisors is a perfect square" is likely open.

"Consecutive untouchable numbers" is open? Untouchable numbers: I think it's known there are infinitely many, but consecutive? Not sure.

"Practical numbers: every even integer is sum of two practical numbers" is a conjecture by Margenstern? I think it's open. But maybe known? I recall "Every even number is the sum of two practical numbers" is a conjecture. Good.

"Sum of squares of digits in base b": For base b, the map is finite because sum of squares of digits ≤ (b-1)^2 * number of digits. For large n, it decreases. So every orbit eventually enters a cycle. The question is to classify cycles for each b. For b=10, known cycles: 1, 4, 16, 37, 58, 89, 145, 42, 20, 4? Actually happy numbers. For general b, classification is computational but maybe not fully known for large b. Could be small open. But not deep.

"Kaprekar routine in base b for n digits": For base 10, n=3 constant 495, n=4 constant 6174, n=5 has cycles? I think for n=5, there are several cycles. For general n, number of cycles? Could be open. Computational.

"Ducci sequences" known.

"Van Eck sequence": open.

"EKG sequence": open.

"Yellowstone permutation": open.

"Look-and-say in base b": Conway's theorem for base 10. For other bases, the cosmological theorem? I think it's known for base 10 only? Actually Conway's cosmological theorem applies to base 10. For other bases, the behavior may be different. Could be open. But maybe studied.

"Somos-4 integrality": known for Somos-4 with integer initial values? Actually Somos-4 sequence defined by a_n a_{n-4} = a_{n-1} a_{n-3} + a_{n-2}^2. It is known to be integral for integer initial values? Yes, it's a classical result. Not open.

"Hofstadter Q": I think it's known that Q(n) is defined for all n? Let me recall: Hofstadter Q sequence: Q(1)=Q(2)=1; Q(n)=Q(n-Q(n-1))+Q(n-Q(n-2)). It is not known if Q(n) is defined for all n? Actually I remember there is a problem: it is not known whether Q(n) < n for all n, which would ensure definition. But I think it has been verified up to large n. It is a known open problem? Maybe. But too famous? Not as famous.

"Number of maximum sum-free subsets of [n]": I think known: for n even, exactly 2? For n odd, exactly 1? Let's check n=5 max size 3. Sets: {1,3,5}? {2,3,5}? 2+3=5 so not. {1,4,5}? 1+4=5 not. {3,4,5}? 3+4=7. {1,2,5}? 1+2=3 no. So maybe only odds. For n=6, max size 3. Sets: {1,3,5}, {2,3,5}? 2+3=5 no. {4,5,6}? 4+5=9. {1,4,5}? 1+4=5 no. So maybe few. Not interesting.

"Number of maximal sum-free subsets": known asymptotics.

"Sidon sets": maximum size known. Number of maximum Sidon sets? Not sure. Could be interesting.

"Costas arrays": famous open.

"Permutations avoiding two consecutive patterns": There are many pairs, some enumerated. Could be small.

"Permutations with no 3-term AP in positions and values": This is related to non-attacking queens? Actually permutations with no 3-term AP in positions and values are "3-free permutations". Known? There is a conjecture that for n large, no such permutations? Wait, permutations of [n] with no 3-term arithmetic progression in the sequence of values? That's exactly "permutations avoiding arithmetic progressions". For n=4, 1,3,2,4? 1,2,3? Not. There is a known problem: maximum size of subset of [n] with no 3-AP is r_3(n). But permutation with no 3-AP in positions and values? It's a "3-free permutation". It is known that for n ≥ 20? Actually there is a theorem: there are no 3-free permutations of length n for n sufficiently large? I recall a problem: "Does there exist a permutation of {1,...,n} with no 3-term arithmetic progression in the sequence?" This is equivalent to a complete mapping of Z_n avoiding 3-AP. It is known that for n≥? there are none? Let's not.

"Latin squares transversals": Number of transversals in cyclic Latin squares of odd order. It is conjectured that the number of transversals in the cyclic Latin square of order n is odd if and only if n is odd? Actually there is a known conjecture: the number of transversals in the cyclic Latin square of order n is odd for n odd? I think it's open? Could be.

"Zero-sum problems: Davenport constant of non-abelian groups": known for some.

"Ramsey numbers for books": R(B_m, B_n) exact? I think R(B_m, B_n) = 2m + n + 1? Not sure. Known for books? There is a result. Maybe not.

"Ramsey numbers for cycles": known for many.

"Induced Ramsey numbers for paths": exact? I think induced Ramsey number of paths is known? Not sure.

"Burning number of trees": There is a conjecture: burning number of a tree ≤ ceil((diameter+1)/2)? Actually for any connected graph, burning number ≤ ceil(sqrt(2n))? For trees, there is a conjecture that burning number ≤ ceil((diameter+1)/2)? I think it's known that burning number of a path is ceil(sqrt(n))? Wait, burning number of a path P_n is ceil(sqrt(n))? Actually burning number of path: b(P_n) = ceil(sqrt(n))? Let's recall: Burning number of a path of length n is ceil(sqrt(n))? No, for path, you can burn one vertex per step, it spreads. The burning number of a path P_n is ceil(sqrt(n))? I think it's floor(sqrt(n-1))+1? Something like that. For trees, there is a conjecture by Bonato et al. that b(T) ≤ ceil((diam(T)+1)/2)? Not sure.

"Cop number of Cartesian product of two trees": I think it's known that it's at most 2. Actually I recall a result: The cop number of the Cartesian product of two trees is at most 2. So not open.

"Domination number of grid graphs": exact formula known? For m,n ≥ 16, γ(G_{m,n}) = floor((m+2)(n+2)/5)-4. This was proved by Gonçalves et al. 2011? So solved.

"Total domination number of hypercubes": exact? I think known.

"Graceful labeling of trees": famous open.

"Harmonious labeling of trees": famous open.

"Prime labeling of trees": open.

"Edge irregularity strength of paths and cycles": exact known? I think known.

"List chromatic number of bipartite planar graphs": is it 3? Actually list chromatic number of planar bipartite graphs can be 3? There is a theorem: every planar bipartite graph is 3-choosable? I think it's known that every planar bipartite graph is 3-choosable? Actually there are planar bipartite graphs not 2-choosable. 3-choosable is known? I think it's a theorem. Not open.

"Chromatic number of square of planar graphs": known max 8? Actually Wegner's conjecture: square of planar graph with Δ=3 has χ≤7? Known? Not.

"Hadwiger number of random graphs": known.

"Treewidth of random cubic graphs": known linear.

"Algebraic connectivity of trees with given degree sequence": extremal? Could be.

"Spectral radius of graphs with given independence number": extremal? Known? There is a conjecture.

"Number of spanning trees in grid graphs": exact formula known via eigenvalues.

"Number of perfect matchings in grid graphs": exact formula known for m x n? For grid graphs, number of perfect matchings is known (Kasteleyn). For general grid with holes? Open.

"Random Fibonacci sequences": growth rate known.

"Random walk hitting time of moving boundary": could be.

"Coupon collector with two coupons at a time": expected time? Known.

"Benford's law for n!": known.

"Pancake sorting": exact for burnt pancakes? Known? The burnt pancake problem is open? I think the exact number for burnt pancakes is known? Actually the pancake sorting problem (sorting by prefix reversals) has a known formula for unburnt? It was solved in 2011? The burnt pancake problem is still open? I recall: The pancake problem for burnt pancakes is still open? Actually the burnt pancake problem was solved for some? Let's check: The minimum number of prefix reversals to sort a stack of n burnt pancakes is known? I think it's open for n≥? The unburnt pancake problem was solved by Gates and Papadimitriou? Actually the exact number for unburnt pancakes is known: n+1? No. The pancake number P(n) is known? I think it's not fully known for all n? Wait, the pancake problem: sorting by prefix reversals. The exact value is known for n up to 19? It's an open problem in general. The burnt pancake problem is also open. But it's famous? Maybe not as famous. Could include.

"Minimum comparisons to find median": known for small n.

"Reconfiguration of k-colorings of planar graphs": connectivity? Could be.

"Firefighter on grids": exact saved vertices? Open.

"Graph pebbling number of product of paths": known? There is a conjecture.

This is a lot. I need produce final answer. To save time, I'll write a structured response with 50 candidates. I can make them concise. Then final 10. I'll ensure no claim of open. Use "potentially open", "requires literature verification".

Let's draft final answer. I'll write in English. I'll use a compact format:

Candidate 1
Problem: ...
Origin: ...
Known intuition: ...
Unknown aspect: ...
Why interesting: ...
Computational tractability: ...
Potential counterexamples: ...
Possible research directions: ...
Novelty risk: ...
Scores: NP=..., MS=..., CT=..., OQ=...

I'll do 50. This will be long but manageable. I'll try to keep each field to one sentence. Then final 10.

Let's start. I'll pick 50 from my list. I'll number 1-50. Need final 10. I'll choose final 10 as: 1, 4, 5, 7, 10, 14, 15, 16, 34, 35? But some might be known. Let's select final 10 based on potential:
1 n+rev square
4 sum proper divisors square
5 τ(n)=τ(n+1)
7 practical Goldbach
10 sum of squares digits cycles in base b
14 Van Eck every integer
15 EKG permutation
16 Yellowstone permutation
34 burning number of trees
35 cop number product of trees? (if not known)
Maybe also 23 maximum Sidon sets unbounded.

But final 10 should be strongest. I'll rank them. Top 3: Van Eck, EKG/Yellowstone, n+rev square. Or practical Goldbach. Need explain.

Let's write.

I need be careful: Candidate 34 burning number of trees: I think there is a conjecture that b(T) ≤ ceil((diam+1)/2)? Actually I'm not sure. If it's false, counterexample. I can state as question.

Candidate 35: cop number of Cartesian product of two trees. I think it's known to be ≤2? Actually I recall a theorem: The cop number of the Cartesian product of two trees is at most 2. So not open. Maybe remove from final. Use another.

Maybe final 10: 1,4,5,7,10,14,15,16,23,34. That's 10.

Let's now write final answer. I'll be concise. Need at least 50 candidates. I'll produce 50. I'll use "Candidate X" headings. This will be long. Let's go.

I'll ensure each has scores. At end, second filter: eliminate trivial etc. Then final 10 ranking. Then top 3.

Let's write.

---
##Original Output

# Discovery-Stage Pool of Mathematical Questions

Below I list 50 candidate problems. I am not claiming that any of these are genuinely open. The correct epistemic status is usually “potentially unexplored,” “possibly open,” or “requires literature verification.” Where I am uncertain, I say so explicitly. The goal is to generate a high-quality pool for later literature search, not to assert novelty.

---

## Candidate 1

**Problem:** Let \(r(n)\) denote the decimal digit reversal of \(n\). Are there infinitely many \(n\) such that \(n+r(n)\) is a perfect square?

**Mathematical origin:** Digit-reversal sequences and elementary Diophantine equations.

**Known intuition:** For two-digit \(n\), \(n+r(n)=11(a+b)\), so solutions occur when \(a+b=11\). Many small solutions exist. Modular restrictions modulo 9 are immediate.

**Unknown aspect:** Whether the set of solutions is infinite, and whether it has positive density among suitable congruence classes.

**Why it is interesting:** It is a small, explicit digit problem combining base-10 arithmetic with square recognition.

**Computational tractability:** Very high. One can test up to \(10^9\) or more with simple code.

**Potential counterexamples:** A proof of finiteness might come from modular obstructions at higher digit lengths.

**Possible research directions:** Parametrize by digit sums; study blocks of digits; use automata theory for digit constraints.

**Novelty risk:** Reversal problems are common; this exact square condition may already have been studied.

**Scores:** Novelty Potential 60; Mathematical Significance 40; Computational Tractability 95; Potential for Overlooked Question 70.

---

## Candidate 2

**Problem:** With \(r(n)\) as above, are there infinitely many \(n\) such that \(n+r(n)\) is prime?

**Mathematical origin:** Digit reversal and prime values of linear-like digit forms.

**Known intuition:** Heuristically, many such \(n\) should exist. Parity forces \(n\) and \(r(n)\) to have opposite parity or one to be 2.

**Unknown aspect:** Infinitude and density.

**Why it is interesting:** It is a concrete intersection of digit reversal and primality.

**Computational tractability:** High for ranges up to \(10^8\) or \(10^9\).

**Potential counterexamples:** No obvious finite obstruction, but proving infinitude is likely hard.

**Possible research directions:** Sieve methods for digit-reversal forms; study primes of the form \(n+r(n)\).

**Novelty risk:** Similar to palindromic prime problems; likely some literature exists.

**Scores:** Novelty Potential 50; Mathematical Significance 35; Computational Tractability 95; Potential for Overlooked Question 55.

---

## Candidate 3

**Problem:** Are there infinitely many \(n\) such that \(n-r(n)\) is a nonzero perfect square?

**Mathematical origin:** Difference of a number and its digit reversal.

**Known intuition:** \(n-r(n)\) is always divisible by 9. For two digits, \(n-r(n)=9(a-c)\), so squares occur when \(a-c\) is a square. Small solutions exist.

**Unknown aspect:** Infinitude and characterization.

**Why it is interesting:** It is an elementary digit problem with a built-in divisibility by 9.

**Computational tractability:** Very high.

**Potential counterexamples:** Modular restrictions may limit solutions.

**Possible research directions:** Analyze \(n-r(n)\) modulo powers of 10 and 9.

**Novelty risk:** Likely studied in recreational number theory.

**Scores:** Novelty Potential 45; Mathematical Significance 30; Computational Tractability 95; Potential for Overlooked Question 50.

---

## Candidate 4

**Problem:** Let \(s(n)=\sigma(n)-n\) be the sum of proper divisors. Are there infinitely many \(n\) such that \(s(n)\) is a perfect square?

**Mathematical origin:** Aliquot sums and divisor functions.

**Known intuition:** Many small examples exist, e.g., \(n=6\), \(s(6)=6\), not square; \(n=12\), \(s(12)=16\). Heuristically, squares should occur infinitely often.

**Unknown aspect:** Infinitude and density.

**Why it is interesting:** It is a natural arithmetic function value problem.

**Computational tractability:** High for \(n\) up to \(10^7\) or more.

**Potential counterexamples:** A theorem could show only finitely many by congruence obstructions.

**Possible research directions:** Use multiplicative structure of \(\sigma(n)\); sieve for square values.

**Novelty risk:** Square values of arithmetic functions are a common theme; may be known.

**Scores:** Novelty Potential 55; Mathematical Significance 50; Computational Tractability 90; Potential for Overlooked Question 60.

---

## Candidate 5

**Problem:** Are there infinitely many \(n\) such that \(\tau(n)=\tau(n+1)\), where \(\tau\) is the number of positive divisors?

**Mathematical origin:** Divisor function and consecutive integers.

**Known intuition:** Many small examples: \(\tau(2)=2\), \(\tau(3)=2\); \(\tau(14)=4\), \(\tau(15)=4\). Heuristically, infinitely many should exist.

**Unknown aspect:** Infinitude and asymptotic density.

**Why it is interesting:** It is a simple, testable question about consecutive integers.

**Computational tractability:** Very high.

**Potential counterexamples:** None obvious.

**Possible research directions:** Sieve methods; compare local divisor counts.

**Novelty risk:** This is a known type of problem; literature may exist.

**Scores:** Novelty Potential 50; Mathematical Significance 55; Computational Tractability 95; Potential for Overlooked Question 60.

---

## Candidate 6

**Problem:** Are there infinitely many \(n\) such that \(\varphi(n)=\varphi(n+2)\), where \(\varphi\) is Euler’s totient?

**Mathematical origin:** Euler totient and shifted arguments.

**Known intuition:** Solutions exist. The case \(\varphi(n)=\varphi(n+1)\) is already subtle. The shift by 2 adds parity constraints.

**Unknown aspect:** Infinitude.

**Why it is interesting:** Totients of nearby integers are a classical source of problems.

**Computational tractability:** High.

**Potential counterexamples:** Parity and divisibility may restrict solutions.

**Possible research directions:** Study totients of even and odd integers; use Chinese remainder constructions.

**Novelty risk:** Totient equality problems are well studied.

**Scores:** Novelty Potential 45; Mathematical Significance 55; Computational Tractability 90; Potential for Overlooked Question 50.

---

## Candidate 7

**Problem:** Is every sufficiently large even integer the sum of two practical numbers?

**Mathematical origin:** Practical numbers and additive number theory.

**Known intuition:** Practical numbers are dense enough that a Goldbach-type statement is plausible. This is a known conjecture in spirit, but I am not certain of its exact status.

**Unknown aspect:** Existence of a proof for all sufficiently large even integers.

**Why it is interesting:** It is a Goldbach analogue with a denser set.

**Computational tractability:** High for moderate ranges.

**Potential counterexamples:** Small even integers might fail; large counterexamples would be surprising.

**Possible research directions:** Use density of practical numbers; circle method; sieve.

**Novelty risk:** This may be a known conjecture; literature search is essential.

**Scores:** Novelty Potential 50; Mathematical Significance 70; Computational Tractability 85; Potential for Overlooked Question 60.

---

## Candidate 8

**Problem:** Are there infinitely many pairs of consecutive untouchable numbers?

**Mathematical origin:** Untouchable numbers are those not in the image of \(\sigma(n)-n\).

**Known intuition:** Untouchable numbers are relatively common. Consecutive pairs occur but may be sparse.

**Unknown aspect:** Infinitude of consecutive pairs.

**Why it is interesting:** It concerns gaps in the image of a classical arithmetic function.

**Computational tractability:** Moderate to high with sieving.

**Potential counterexamples:** Parity might force gaps.

**Possible research directions:** Sieve for untouchable numbers; study modular obstructions.

**Novelty risk:** Untouchable numbers have been studied; consecutive pairs may be known.

**Scores:** Novelty Potential 60; Mathematical Significance 55; Computational Tractability 80; Potential for Overlooked Question 65.

---

## Candidate 9

**Problem:** Does there exist an aliquot sequence starting from some positive integer that enters a cycle other than the known cycles of length 1 or 2?

**Mathematical origin:** Aliquot sequences and the Catalan–Dickson conjecture.

**Known intuition:** Many cycles are known, including perfect numbers and amicable pairs. Longer cycles are known for some starting values.

**Unknown aspect:** Existence of new cycles, especially long ones, and whether all sequences eventually terminate or cycle.

**Why it is interesting:** It is a classical dynamical system on integers.

**Computational tractability:** High for small starting values, but long-term behavior is hard.

**Potential counterexamples:** New cycles may be found computationally.

**Possible research directions:** Large-scale computation; probabilistic models.

**Novelty risk:** This is a famous area; likely not overlooked.

**Scores:** Novelty Potential 30; Mathematical Significance 75; Computational Tractability 70; Potential for Overlooked Question 30.

---

## Candidate 10

**Problem:** For a base \(b\), consider the map \(f_b(n)\) = sum of squares of the base-\(b\) digits of \(n\). Classify all cycles of \(f_b\) for each \(b\ge 2\). In particular, for which \(b\) does \(f_b\) have a cycle of length greater than 1?

**Mathematical origin:** Happy numbers and digit-square dynamics.

**Known intuition:** For \(b=10\), the cycles are known. For general \(b\), the map is eventually periodic because it decreases for large \(n\).

**Unknown aspect:** Complete classification of cycles for all bases, and asymptotic growth of the number of cycles as \(b\to\infty\).

**Why it is interesting:** It is a finite dynamical system problem with a clean computational component.

**Computational tractability:** Very high for individual bases; classification for all \(b\) may be hard.

**Potential counterexamples:** Some bases may have only fixed points.

**Possible research directions:** Automate cycle search; study cycle lengths modulo \(b\).

**Novelty risk:** Generalized happy numbers have been studied; full classification may exist for small bases.

**Scores:** Novelty Potential 55; Mathematical Significance 45; Computational Tractability 90; Potential for Overlooked Question 65.

---

## Candidate 11

**Problem:** Consider the map \(g(n)\) = sum of cubes of decimal digits. Are there infinitely many \(n\) whose orbit under \(g\) reaches 1?

**Mathematical origin:** Armstrong numbers and digit-power maps.

**Known intuition:** For large \(n\), \(g(n)\) is much smaller, so orbits are eventually periodic. The basin of 1 may be infinite.

**Unknown aspect:** Infinitude of the basin of 1.

**Why it is interesting:** It is an elementary dynamical system with a number-theoretic flavor.

**Computational tractability:** High.

**Potential counterexamples:** The basin may be finite.

**Possible research directions:** Automata; modular analysis; computational enumeration.

**Novelty risk:** Digit-power maps are well studied.

**Scores:** Novelty Potential 45; Mathematical Significance 35; Computational Tractability 90; Potential for Overlooked Question 50.

---

## Candidate 12

**Problem:** For the Kaprekar routine in base \(b\) on \(n\)-digit numbers, determine the number of fixed points and cycles as a function of \(n\) and \(b\).

**Mathematical origin:** Kaprekar constants and digit rearrangement.

**Known intuition:** For base 10, \(n=3\) gives 495, \(n=4\) gives 6174. For larger \(n\), multiple cycles exist.

**Unknown aspect:** General classification for all \(n,b\).

**Why it is interesting:** It is a concrete discrete dynamical system with combinatorial structure.

**Computational tractability:** High for small \(n,b\); grows rapidly.

**Potential counterexamples:** Some \((n,b)\) may have no nontrivial cycles.

**Possible research directions:** Symmetry analysis; transfer operators; computational enumeration.

**Novelty risk:** Kaprekar routines are widely studied.

**Scores:** Novelty Potential 40; Mathematical Significance 40; Computational Tractability 80; Potential for Overlooked Question 50.

---

## Candidate 13

**Problem:** For integer Ducci sequences of length \(n\), i.e., iterating \((a_1,\dots,a_n)\mapsto(|a_1-a_2|,\dots,|a_n-a_1|)\), characterize those \(n\) for which every integer sequence reaches the zero vector.

**Mathematical origin:** Ducci sequences and finite difference dynamics.

**Known intuition:** For \(n\) a power of 2, every integer sequence reaches zero. For other \(n\), nonzero cycles exist.

**Unknown aspect:** Complete characterization and classification of cycles for non-powers of 2.

**Why it is interesting:** It is a clean dynamical system on integer vectors.

**Computational tractability:** High for small \(n\).

**Potential counterexamples:** Known for \(n=3\).

**Possible research directions:** Linear algebra over \(\mathbb{Z}\); modular analysis.

**Novelty risk:** This is a known solved/partially solved area.

**Scores:** Novelty Potential 30; Mathematical Significance 60; Computational Tractability 85; Potential for Overlooked Question 30.

---

## Candidate 14

**Problem:** Does every positive integer eventually appear in the Van Eck sequence?

**Mathematical origin:** Van Eck sequence: start with 0; if the previous term has appeared before, next term is the distance to its previous occurrence; otherwise next term is 0.

**Known intuition:** The sequence is conjectured to be a permutation of the nonnegative integers. Many small integers appear.

**Unknown aspect:** Whether the sequence is surjective.

**Why it is interesting:** It is a simple recursive sequence with surprising complexity.

**Computational tractability:** Very high for large initial segments.

**Potential counterexamples:** Some integer might never appear.

**Possible research directions:** Computational search; probabilistic heuristics; automata.

**Novelty risk:** This is a known open problem in the sequence community; requires literature verification.

**Scores:** Novelty Potential 70; Mathematical Significance 65; Computational Tractability 95; Potential for Overlooked Question 80.

---

## Candidate 15

**Problem:** Is the EKG sequence a permutation of the positive integers? The EKG sequence starts \(a_1=1\), \(a_2=2\), and \(a_n\) is the smallest unused positive integer sharing a common factor with \(a_{n-1}\).

**Mathematical origin:** Recursively defined permutations of integers.

**Known intuition:** It is conjectured to be a permutation. Computations show all small integers appear.

**Unknown aspect:** Proof of surjectivity.

**Why it is interesting:** It combines gcd constraints with a greedy algorithm.

**Computational tractability:** Very high.

**Potential counterexamples:** Some integer might be skipped forever.

**Possible research directions:** Analyze prime gaps; use graph-theoretic models.

**Novelty risk:** This is a known open problem; literature exists.

**Scores:** Novelty Potential 60; Mathematical Significance 65; Computational Tractability 95; Potential for Overlooked Question 70.

---

## Candidate 16

**Problem:** Is the Yellowstone permutation a permutation of the positive integers? The Yellowstone permutation starts \(a_1=1\), \(a_2=2\), \(a_3=3\), and then \(a_n\) is the smallest unused positive integer such that \(\gcd(a_n,a_{n-1})>1\) and \(\gcd(a_n,a_{n-2})=1\).

**Mathematical origin:** Greedy permutations with gcd constraints.

**Known intuition:** Conjectured to be a permutation. Many small integers appear.

**Unknown aspect:** Surjectivity.

**Why it is interesting:** It is a more constrained greedy permutation than EKG.

**Computational tractability:** Very high.

**Potential counterexamples:** Some integer might be permanently blocked.

**Possible research directions:** Computational search; analyze prime powers.

**Novelty risk:** Known open problem in sequence community.

**Scores:** Novelty Potential 60; Mathematical Significance 65; Computational Tractability 95; Potential for Overlooked Question 70.

---

## Candidate 17

**Problem:** Are there infinitely many positive integers that never appear in Recamán’s sequence?

**Mathematical origin:** Recamán sequence: \(a_0=0\), \(a_n=a_{n-1}-n\) if positive and unused, else \(a_n=a_{n-1}+n\).

**Known intuition:** Many integers appear; some are conjectured missing. Infinitude of missing values is open.

**Unknown aspect:** Existence of infinitely many missing values.

**Why it is interesting:** It is a classic recursive sequence.

**Computational tractability:** High for initial segments.

**Potential counterexamples:** Missing values may be finite.

**Possible research directions:** Computational search; modular patterns.

**Novelty risk:** Famous in recreational mathematics.

**Scores:** Novelty Potential 30; Mathematical Significance 60; Computational Tractability 90; Potential for Overlooked Question 30.

---

## Candidate 18

**Problem:** In the look-and-say sequence over a base \(b\), do the lengths of terms grow exponentially for every base \(b\ge 2\)?

**Mathematical origin:** Conway’s cosmological theorem for base 10.

**Known intuition:** For base 10, lengths grow by a constant factor. For other bases, behavior may differ.

**Unknown aspect:** General base classification.

**Why it is interesting:** It is a string-rewriting dynamical system.

**Computational tractability:** High for small bases and many iterations.

**Potential counterexamples:** Some bases may have decaying or periodic lengths.

**Possible research directions:** Automata; matrix products; computational exploration.

**Novelty risk:** Look-and-say is well studied, but general bases may be partially open.

**Scores:** Novelty Potential 50; Mathematical Significance 50; Computational Tractability 85; Potential for Overlooked Question 60.

---

## Candidate 19

**Problem:** Is the Hofstadter Q-sequence defined for all positive integers? That is, does \(Q(n)=Q(n-Q(n-1))+Q(n-Q(n-2))\) with \(Q(1)=Q(2)=1\) always have \(Q(n-1)<n\) and \(Q(n-2)<n\)?

**Mathematical origin:** Hofstadter’s meta-Fibonacci sequences.

**Known intuition:** Verified for large \(n\). It is conjectured to be well-defined.

**Unknown aspect:** Proof of well-definedness.

**Why it is interesting:** It is a famous example of a recursively defined sequence with chaotic behavior.

**Computational tractability:** High.

**Potential counterexamples:** A failure might occur at very large \(n\).

**Possible research directions:** Computational verification; asymptotic analysis.

**Novelty risk:** Known open problem.

**Scores:** Novelty Potential 40; Mathematical Significance 65; Computational Tractability 90; Potential for Overlooked Question 40.

---

## Candidate 20

**Problem:** For the Somos-4 recurrence \(a_n a_{n-4}=a_{n-1}a_{n-3}+a_{n-2}^2\), are there initial values in a number field that produce a sequence with infinitely many nonintegral terms?

**Mathematical origin:** Somos sequences and Laurent phenomenon.

**Known intuition:** For integer initial values, Somos-4 is integral. Over other rings, behavior can differ.

**Unknown aspect:** General algebraic characterization of integrality.

**Why it is interesting:** It connects recurrence, algebraic geometry, and cluster algebras.

**Computational tractability:** Moderate.

**Potential counterexamples:** Nonintegral examples may exist.

**Possible research directions:** Algebraic geometry; Laurent phenomenon.

**Novelty risk:** Somos sequences are well studied.

**Scores:** Novelty Potential 35; Mathematical Significance 70; Computational Tractability 60; Potential for Overlooked Question 30.

---

## Candidate 21

**Problem:** Let \(F(n)\) be the number of maximum-size sum-free subsets of \(\{1,\dots,n\}\). Is \(F(n)\) bounded by a polynomial in \(n\)?

**Mathematical origin:** Sum-free sets in intervals.

**Known intuition:** Maximum size is \(\lceil n/2\rceil\). For small \(n\), \(F(n)\) is small.

**Unknown aspect:** Growth rate of \(F(n)\).

**Why it is interesting:** It is an extremal combinatorics counting problem.

**Computational tractability:** Moderate for small \(n\).

**Potential counterexamples:** \(F(n)\) might grow exponentially.

**Possible research directions:** Structural classification of maximum sum-free sets.

**Novelty risk:** Sum-free sets are well studied.

**Scores:** Novelty Potential 45; Mathematical Significance 50; Computational Tractability 70; Potential for Overlooked Question 55.

---

## Candidate 22

**Problem:** Determine the asymptotic number of maximal (by inclusion) sum-free subsets of \(\{1,\dots,n\}\).

**Mathematical origin:** Maximal sum-free sets.

**Known intuition:** There are known bounds and some exact asymptotics. I am not certain if the exact asymptotic is known.

**Unknown aspect:** Precise asymptotic constant.

**Why it is interesting:** It is a fundamental counting problem in additive combinatorics.

**Computational tractability:** Moderate.

**Potential counterexamples:** Not applicable.

**Possible research directions:** Container methods; structure of maximal sum-free sets.

**Novelty risk:** Likely studied.

**Scores:** Novelty Potential 35; Mathematical Significance 60; Computational Tractability 65; Potential for Overlooked Question 40.

---

## Candidate 23

**Problem:** Let \(S(n)\) be the maximum size of a Sidon set in \(\{1,\dots,n\}\). Is the number of maximum-size Sidon sets in \(\{1,\dots,n\}\) unbounded as \(n\to\infty\)?

**Mathematical origin:** Sidon sets and difference sets.

**Known intuition:** \(S(n)\sim\sqrt{n}\). Many maximum Sidon sets exist for small \(n\).

**Unknown aspect:** Unboundedness of the count.

**Why it is interesting:** It is a counting problem for extremal additive structures.

**Computational tractability:** Moderate for small \(n\).

**Potential counterexamples:** The number might be bounded.

**Possible research directions:** Construct many maximum Sidon sets; use probabilistic methods.

**Novelty risk:** Sidon sets are well studied; this exact count may be overlooked.

**Scores:** Novelty Potential 60; Mathematical Significance 55; Computational Tractability 70; Potential for Overlooked Question 65.

---

## Candidate 24

**Problem:** For which pairs \((v,k,\lambda)\) do perfect difference sets exist? In particular, are there infinitely many cyclic perfect difference sets with \(k>3\)?

**Mathematical origin:** Difference sets in finite groups.

**Known intuition:** Perfect difference sets correspond to projective planes. Existence is a major open area.

**Unknown aspect:** General existence.

**Why it is interesting:** It connects combinatorics and finite geometry.

**Computational tractability:** Low for large parameters.

**Potential counterexamples:** Nonexistence for many parameters is known.

**Possible research directions:** Algebraic number theory; finite geometry.

**Novelty risk:** This is a famous open problem area.

**Scores:** Novelty Potential 20; Mathematical Significance 90; Computational Tractability 30; Potential for Overlooked Question 20.

---

## Candidate 25

**Problem:** Do Costas arrays exist for every order \(n\)?

**Mathematical origin:** Costas arrays are permutations with distinct difference vectors.

**Known intuition:** Existence is known for infinitely many \(n\), but not all.

**Unknown aspect:** Existence for all \(n\).

**Why it is interesting:** It is a combinatorial design problem with applications in radar.

**Computational tractability:** Moderate for small \(n\).

**Potential counterexamples:** Some order may have no Costas array.

**Possible research directions:** Algebraic constructions; exhaustive search.

**Novelty risk:** Famous open problem in combinatorial design.

**Scores:** Novelty Potential 20; Mathematical Significance 80; Computational Tractability 60; Potential for Overlooked Question 20.

---

## Candidate 26

**Problem:** For each pair of consecutive patterns of length 3, determine the generating function for permutations avoiding both patterns.

**Mathematical origin:** Consecutive pattern avoidance.

**Known intuition:** Many single consecutive patterns have known enumerations. Pairs are less systematically classified.

**Unknown aspect:** Complete classification of all pairs.

**Why it is interesting:** It is a finite but nontrivial enumerative combinatorics problem.

**Computational tractability:** High for small lengths.

**Potential counterexamples:** Not applicable.

**Possible research directions:** Transfer matrix; generating functions.

**Novelty risk:** Consecutive pattern avoidance is well studied; some pairs may be known.

**Scores:** Novelty Potential 45; Mathematical Significance 45; Computational Tractability 85; Potential for Overlooked Question 55.

---

## Candidate 27

**Problem:** For which \(n\) does there exist a permutation \(\pi\) of \(\{1,\dots,n\}\) such that both \(\pi\) and \(\pi^{-1}\) avoid 3-term arithmetic progressions?

**Mathematical origin:** Permutations avoiding arithmetic progressions.

**Known intuition:** For small \(n\), examples exist. For large \(n\), existence is unclear.

**Unknown aspect:** Existence for all \(n\) or only finitely many.

**Why it is interesting:** It combines permutation patterns and additive combinatorics.

**Computational tractability:** High for small \(n\).

**Potential counterexamples:** Nonexistence for some \(n\).

**Possible research directions:** SAT solving; probabilistic constructions.

**Novelty risk:** Related to “3-free permutations”; may be known.

**Scores:** Novelty Potential 55; Mathematical Significance 55; Computational Tractability 80; Potential for Overlooked Question 65.

---

## Candidate 28

**Problem:** For the cyclic Latin square of odd order \(n\), is the number of transversals odd?

**Mathematical origin:** Latin squares and transversals.

**Known intuition:** There is a conjecture that the number of transversals in the cyclic Latin square of odd order is odd. I am not certain of its status.

**Unknown aspect:** Parity of the number of transversals.

**Why it is interesting:** It is a clean algebraic-combinatorial parity problem.

**Computational tractability:** Moderate for small odd \(n\).

**Potential counterexamples:** Even counts for some odd \(n\).

**Possible research directions:** Algebraic topology; sign-reversing involutions.

**Novelty risk:** Likely a known conjecture.

**Scores:** Novelty Potential 40; Mathematical Significance 60; Computational Tractability 70; Potential for Overlooked Question 45.

---

## Candidate 29

**Problem:** Does every finite group admit a complete mapping? (A complete mapping is a permutation \(\pi\) such that \(g\pi(g)\) is also a permutation.)

**Mathematical origin:** Hall–Paige conjecture.

**Known intuition:** The Hall–Paige conjecture was proved for many groups; I believe it is now solved. This candidate is included for completeness but likely not open.

**Unknown aspect:** None if solved.

**Why it is interesting:** It is a classical problem.

**Computational tractability:** High for small groups.

**Potential counterexamples:** None if theorem holds.

**Possible research directions:** Literature verification.

**Novelty risk:** Very high; likely solved.

**Scores:** Novelty Potential 5; Mathematical Significance 60; Computational Tractability 80; Potential for Overlooked Question 5.

---

## Candidate 30

**Problem:** Determine the Davenport constant for all non-abelian groups of order \(2p\), where \(p\) is an odd prime.

**Mathematical origin:** Zero-sum problems in finite groups.

**Known intuition:** Davenport constants are known for many groups but not all.

**Unknown aspect:** Exact values for these groups.

**Why it is interesting:** It is a fundamental invariant in additive combinatorics.

**Computational tractability:** Low for large \(p\).

**Potential counterexamples:** Not applicable.

**Possible research directions:** Group algebra; character theory.

**Novelty risk:** Likely studied.

**Scores:** Novelty Potential 35; Mathematical Significance 70; Computational Tractability 40; Potential for Overlooked Question 40.

---

## Candidate 31

**Problem:** Determine the Ramsey number \(R(B_m,B_n)\) for books \(B_m=K_2+K_m\) for all \(m,n\).

**Mathematical origin:** Ramsey theory for books.

**Known intuition:** Many cases are known. Exact formula may be known for some families.

**Unknown aspect:** Complete determination.

**Why it is interesting:** Books are a natural graph family.

**Computational tractability:** Low for large \(m,n\).

**Potential counterexamples:** Not applicable.

**Possible research directions:** Structural Ramsey arguments.

**Novelty risk:** Likely studied.

**Scores:** Novelty Potential 25; Mathematical Significance 60; Computational Tractability 40; Potential for Overlooked Question 30.

---

## Candidate 32

**Problem:** Determine the Ramsey number \(R(C_m,C_n)\) for all \(m,n\).

**Mathematical origin:** Ramsey numbers for cycles.

**Known intuition:** Many cases are known. The general problem is not fully solved.

**Unknown aspect:** Remaining cases.

**Why it is interesting:** It is a central problem in Ramsey theory.

**Computational tractability:** Low.

**Potential counterexamples:** Not applicable.

**Possible research directions:** Structural methods.

**Novelty risk:** Well studied.

**Scores:** Novelty Potential 20; Mathematical Significance 75; Computational Tractability 30; Potential for Overlooked Question 20.

---

## Candidate 33

**Problem:** Determine the induced Ramsey number for paths \(P_m\) and \(P_n\).

**Mathematical origin:** Induced Ramsey theory.

**Known intuition:** Some exact values are known.

**Unknown aspect:** Complete formula.

**Why it is interesting:** Induced Ramsey numbers are less understood than classical ones.

**Computational tractability:** Low.

**Potential counterexamples:** Not applicable.

**Possible research directions:** Structural graph theory.

**Novelty risk:** Likely studied.

**Scores:** Novelty Potential 35; Mathematical Significance 65; Computational Tractability 35; Potential for Overlooked Question 40.

---

## Candidate 34

**Problem:** Is the burning number of every tree \(T\) at most \(\lceil(\operatorname{diam}(T)+1)/2\rceil\)?

**Mathematical origin:** Graph burning number and trees.

**Known intuition:** The burning number of a path is roughly \(\lceil\sqrt{n}\rceil\). The proposed bound may be too weak or too strong; I am not certain.

**Unknown aspect:** Exact upper bound for trees.

**Why it is interesting:** It is a modern graph parameter with many open questions.

**Computational tractability:** Moderate for small trees.

**Potential counterexamples:** A tree with large diameter but small burning number, or vice versa.

**Possible research directions:** Computational search; structural decomposition.

**Novelty risk:** Graph burning is a growing area; some conjectures are known.

**Scores:** Novelty Potential 60; Mathematical Significance 55; Computational Tractability 75; Potential for Overlooked Question 65.

---

## Candidate 35

**Problem:** Is the cop number of the Cartesian product of two trees always at most 2?

**Mathematical origin:** Cops and robbers on graph products.

**Known intuition:** I believe this is known to be at most 2. If so, not open. If not, it is a natural small question.

**Unknown aspect:** Exact maximum cop number.

**Why it is interesting:** It concerns the interaction of graph products and pursuit-evasion.

**Computational tractability:** Moderate for small trees.

**Potential counterexamples:** A product of two trees requiring 3 cops.

**Possible research directions:** Game theory; structural graph theory.

**Novelty risk:** Likely studied; may be solved.

**Scores:** Novelty Potential 30; Mathematical Significance 55; Computational Tractability 70; Potential for Overlooked Question 35.

---

## Candidate 36

**Problem:** Determine the cop number of the Cartesian product of a tree and a cycle.

**Mathematical origin:** Cops and robbers on products.

**Known intuition:** Some bounds exist. Exact values are not fully known.

**Unknown aspect:** Exact formula.

**Why it is interesting:** It is a natural intermediate case.

**Computational tractability:** Moderate.

**Potential counterexamples:** Not applicable.

**Possible research directions:** Product graph decomposition.

**Novelty risk:** Likely studied.

**Scores:** Novelty Potential 45; Mathematical Significance 55; Computational Tractability 70; Potential for Overlooked Question 50.

---

## Candidate 37

**Problem:** Is there a closed-form formula for the domination number of the \(m\times n\) grid graph for all \(m,n\)?

**Mathematical origin:** Domination in grid graphs.

**Known intuition:** Exact formulas are known for large \(m,n\). Small cases may remain.

**Unknown aspect:** Complete unification.

**Why it is interesting:** Grid domination is a benchmark problem.

**Computational tractability:** High for small grids.

**Potential counterexamples:** Not applicable.

**Possible research directions:** Dynamic programming; structural decomposition.

**Novelty risk:** Likely solved for large grids.

**Scores:** Novelty Potential 25; Mathematical Significance 50; Computational Tractability 80; Potential for Overlooked Question 30.

---

## Candidate 38

**Problem:** Determine the total domination number of the hypercube \(Q_n\) exactly for all \(n\).

**Mathematical origin:** Domination in hypercubes.

**Known intuition:** Some exact values and bounds are known.

**Unknown aspect:** Complete formula.

**Why it is interesting:** Hypercubes are fundamental graphs.

**Computational tractability:** Low for large \(n\).

**Potential counterexamples:** Not applicable.

**Possible research directions:** Coding theory; integer programming.

**Novelty risk:** Likely studied.

**Scores:** Novelty Potential 30; Mathematical Significance 60; Computational Tractability 50; Potential for Overlooked Question 35.

---

## Candidate 39

**Problem:** Is every tree graceful? (A graceful labeling assigns distinct labels \(0,\dots,|E|\) to vertices so that edge differences are \(1,\dots,|E|\).)

**Mathematical origin:** Graceful labelings.

**Known intuition:** This is the Ringel–Kotzig conjecture, widely believed but open.

**Unknown aspect:** General proof.

**Why it is interesting:** It is a central open problem in graph labeling.

**Computational tractability:** Moderate for small trees.

**Potential counterexamples:** None known.

**Possible research directions:** Constructive labelings; algebraic methods.

**Novelty risk:** Famous open problem.

**Scores:** Novelty Potential 10; Mathematical Significance 80; Computational Tractability 60; Potential for Overlooked Question 10.

---

## Candidate 40

**Problem:** Is every tree harmonious? (A harmonious labeling assigns distinct labels modulo \(|E|\) to vertices so that edge sums are distinct.)

**Mathematical origin:** Harmonious labelings.

**Known intuition:** Conjectured for trees. Open in general.

**Unknown aspect:** General proof.

**Why it is interesting:** It is a variant of graceful labeling.

**Computational tractability:** Moderate.

**Potential counterexamples:** None known.

**Possible research directions:** Modular constructions.

**Novelty risk:** Known open problem.

**Scores:** Novelty Potential 20; Mathematical Significance 65; Computational Tractability 60; Potential for Overlooked Question 20.

---

## Candidate 41

**Problem:** Is every tree prime? (A prime labeling assigns distinct labels \(1,\dots,|V|\) so that adjacent vertices have coprime labels.)

**Mathematical origin:** Prime labelings.

**Known intuition:** Conjectured for trees. Open in general.

**Unknown aspect:** General proof.

**Why it is interesting:** It connects number theory and graph labeling.

**Computational tractability:** Moderate.

**Potential counterexamples:** None known.

**Possible research directions:** Number-theoretic constructions.

**Novelty risk:** Known open problem.

**Scores:** Novelty Potential 25; Mathematical Significance 60; Computational Tractability 60; Potential for Overlooked Question 25.

---

## Candidate 42

**Problem:** Determine the edge irregularity strength of paths and cycles exactly.

**Mathematical origin:** Irregularity strength of graphs.

**Known intuition:** Exact values may be known. I am not certain.

**Unknown aspect:** Complete formula.

**Why it is interesting:** It is a small extremal labeling problem.

**Computational tractability:** High for small graphs.

**Potential counterexamples:** Not applicable.

**Possible research directions:** Combinatorial constructions.

**Novelty risk:** Likely studied.

**Scores:** Novelty Potential 35; Mathematical Significance 40; Computational Tractability 85; Potential for Overlooked Question 40.

---

## Candidate 43

**Problem:** Is every bipartite planar graph 3-choosable?

**Mathematical origin:** List coloring of planar bipartite graphs.

**Known intuition:** I believe this is known to be true. If so, not open.

**Unknown aspect:** None if theorem holds.

**Why it is interesting:** It is a fundamental list-coloring question.

**Computational tractability:** Low.

**Potential counterexamples:** None if theorem holds.

**Possible research directions:** Literature verification.

**Novelty risk:** Likely solved.

**Scores:** Novelty Potential 5; Mathematical Significance 60; Computational Tractability 40; Potential for Overlooked Question 5.

---

## Candidate 44

**Problem:** Determine the maximum chromatic number of the square of a planar graph with maximum degree \(\Delta\).

**Mathematical origin:** Wegner’s conjecture.

**Known intuition:** Conjectured bounds exist. Some cases are known.

**Unknown aspect:** Complete determination.

**Why it is interesting:** It is a central problem in graph coloring.

**Computational tractability:** Low.

**Potential counterexamples:** Not applicable.

**Possible research directions:** Discharging; structural methods.

**Novelty risk:** Famous conjecture.

**Scores:** Novelty Potential 10; Mathematical Significance 80; Computational Tractability 30; Potential for Overlooked Question 10.

---

## Candidate 45

**Problem:** Determine the threshold for the Hadwiger number of \(G(n,p)\) to become linear in \(n\).

**Mathematical origin:** Random graphs and graph minors.

**Known intuition:** Known thresholds exist.

**Unknown aspect:** Exact threshold.

**Why it is interesting:** It connects random graph theory and minors.

**Computational tractability:** Low.

**Potential counterexamples:** Not applicable.

**Possible research directions:** Probabilistic combinatorics.

**Novelty risk:** Likely studied.

**Scores:** Novelty Potential 20; Mathematical Significance 70; Computational Tractability 30; Potential for Overlooked Question 20.

---

## Candidate 46

**Problem:** Is the treewidth of a random cubic graph linear in the number of vertices with high probability?

**Mathematical origin:** Treewidth of random regular graphs.

**Known intuition:** I believe this is known to be linear.

**Unknown aspect:** Exact constant.

**Why it is interesting:** It is a structural parameter of random graphs.

**Computational tractability:** Low.

**Potential counterexamples:** Not applicable.

**Possible research directions:** Probabilistic methods.

**Novelty risk:** Likely studied.

**Scores:** Novelty Potential 15; Mathematical Significance 65; Computational Tractability 30; Potential for Overlooked Question 15.

---

## Candidate 47

**Problem:** Among trees with a given degree sequence, which tree maximizes the algebraic connectivity?

**Mathematical origin:** Spectral graph theory.

**Known intuition:** Extremal trees for spectral parameters are often “path-like” or “star-like.”

**Unknown aspect:** Exact extremal characterization.

**Why it is interesting:** It connects degree sequences and spectral properties.

**Computational tractability:** Moderate for small trees.

**Potential counterexamples:** Different extremal trees for different sequences.

**Possible research directions:** Tree rotations; spectral perturbation.

**Novelty risk:** Likely studied.

**Scores:** Novelty Potential 40; Mathematical Significance 55; Computational Tractability 75; Potential for Overlooked Question 50.

---

## Candidate 48

**Problem:** Among graphs with a given independence number, which graph maximizes the spectral radius?

**Mathematical origin:** Extremal spectral graph theory.

**Known intuition:** There are known bounds and conjectures.

**Unknown aspect:** Complete extremal characterization.

**Why it is interesting:** It is a natural extremal spectral problem.

**Computational tractability:** Moderate.

**Potential counterexamples:** Different extremal graphs for different parameters.

**Possible research directions:** Graph transformations.

**Novelty risk:** Likely studied.

**Scores:** Novelty Potential 35; Mathematical Significance 60; Computational Tractability 70; Potential for Overlooked Question 45.

---

## Candidate 49

**Problem:** Is there a simple exact formula for the number of spanning trees of the \(m\times n\) grid graph for all \(m,n\)?

**Mathematical origin:** Spanning trees in grid graphs.

**Known intuition:** Exact formulas via eigenvalues are known.

**Unknown aspect:** Simplification for all \(m,n\).

**Why it is interesting:** It is a classical enumeration problem.

**Computational tractability:** High.

**Potential counterexamples:** Not applicable.

**Possible research directions:** Matrix-tree theorem; Chebyshev polynomials.

**Novelty risk:** Likely solved.

**Scores:** Novelty Potential 10; Mathematical Significance 50; Computational Tractability 90; Potential for Overlooked Question 10.

---

## Candidate 50

**Problem:** Is there a simple exact formula for the number of perfect matchings of the \(m\times n\) grid graph with a fixed set of holes?

**Mathematical origin:** Dimer coverings and Kasteleyn theory.

**Known intuition:** For full grids, exact formulas exist. With holes, the problem is harder.

**Unknown aspect:** General formula for arbitrary holes.

**Why it is interesting:** It connects combinatorics and statistical mechanics.

**Computational tractability:** Moderate for small grids.

**Potential counterexamples:** Not applicable.

**Possible research directions:** Pfaffian methods; computational enumeration.

**Novelty risk:** Likely studied in special cases.

**Scores:** Novelty Potential 45; Mathematical Significance 65; Computational Tractability 70; Potential for Overlooked Question 55.

---

# Second Internal Filter

I now eliminate candidates that are clearly trivial, obviously false, elementary, famous, too vague, or cosmetic. The following are eliminated from strongest consideration:

- Candidate 29: likely solved Hall–Paige.
- Candidate 39: famous Ringel–Kotzig conjecture.
- Candidate 43: likely known theorem.
- Candidate 44: famous Wegner conjecture.
- Candidate 49: classical known formula.
- Candidate 9: aliquot cycles is a famous area.
- Candidate 17: Recamán is famous.
- Candidate 24, 25: very famous open problems.

The remaining strongest candidates for further investigation are the following 10.

---

# Final 10 Candidates, Ranked

## Rank 1: Candidate 14 — Van Eck sequence surjectivity

**Why it deserves investigation:** The Van Eck sequence is simple to define, computationally easy to explore, and its surjectivity appears to be a sharp, concrete open question. It is not as famous as the Riemann Hypothesis or Goldbach, but it has enough structure to attract sequence enthusiasts. A literature search is essential, but the question is precise and testable.

## Rank 2: Candidate 15 — EKG sequence is a permutation

**Why it deserves investigation:** The EKG sequence is a greedy gcd-constrained permutation. Computational evidence strongly suggests it is a permutation. The problem is small, clear, and connects to prime gaps and greedy algorithms. It may be known, but it is an excellent candidate for a focused literature check.

## Rank 3: Candidate 16 — Yellowstone permutation is a permutation

**Why it deserves investigation:** Similar to EKG but with two-step gcd constraints. It is slightly less famous and may have overlooked aspects. Computational tractability is high, and counterexamples would be surprising and informative.

## Rank 4: Candidate 1 — Infinitely many \(n\) with \(n+r(n)\) square

**Why it deserves investigation:** This is an elementary digit problem. It is easy to compute and may have a clean modular or automata-theoretic structure. The infinitude question is sharp and likely not fully settled.

## Rank 5: Candidate 7 — Even integers as sums of two practical numbers

**Why it deserves investigation:** It is a Goldbach analogue for a denser set. Practical numbers have rich multiplicative structure. The problem is precise and computationally testable. Literature verification is necessary, as it may be a known conjecture.

## Rank 6: Candidate 10 — Cycles of digit-square maps in base \(b\)

**Why it deserves investigation:** This is a family of finite dynamical systems. Classifying cycles for all bases is a concrete, computationally driven problem. It may be partially studied, but a complete classification could be overlooked.

## Rank 7: Candidate 4 — Sum of proper divisors is a square

**Why it deserves investigation:** It is a natural arithmetic function value problem. It is simple to state and test. Infinitude is plausible but not obvious. It may connect to aliquot sequences and divisor sums.

## Rank 8: Candidate 5 — \(\tau(n)=\tau(n+1)\) infinitely often

**Why it deserves investigation:** This is a crisp consecutive-integer divisor problem. It is highly tractable computationally and has a natural sieve-theoretic flavor. It may be known, but it is a good benchmark question.

## Rank 9: Candidate 23 — Number of maximum Sidon sets is unbounded

**Why it deserves investigation:** It is a counting problem for extremal additive structures. It is less standard than just finding the maximum size. Computational exploration for small \(n\) could reveal patterns and suggest constructions.

## Rank 10: Candidate 34 — Burning number of trees

**Why it deserves investigation:** Graph burning is a modern parameter with many open questions. The tree case is natural and computationally accessible. A precise conjecture or counterexample could be found by experimentation.

---

# Top 3 Most Promising for Literature Search

1. **Candidate 14 — Van Eck sequence surjectivity.**  
   It is simple, computationally testable, and appears to be a known open problem in the sequence community. A literature search should first determine whether surjectivity has been proved or whether only computational evidence exists.

2. **Candidate 15 — EKG sequence is a permutation.**  
   This is a well-defined greedy permutation problem. It is likely discussed in the literature, but the exact status of the proof should be verified. It is an excellent candidate for a small, sharp problem.

3. **Candidate 1 — Infinitely many \(n\) with \(n+r(n)\) square.**  
   This is an elementary digit problem that may have been overlooked or only partially studied. It is easy to compute and could yield a publishable small result if a construction or obstruction is found.

These three are the best starting points for a rigorous literature-search stage.



---

## My Notes

- No conclusions about novelty were accepted at this stage.
- Literature verification was intentionally postponed.
- The candidates will be independently checked in later stages.
