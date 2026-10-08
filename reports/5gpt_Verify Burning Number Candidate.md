## 1. Latest theorem verified

The claimed 2026 result **does exist**, but its publication status is weaker than the wording “2026 result” might suggest.

**Primary record:** Sandip Das, Sk Samim Islam, Ritam Manna Mitra, Sanchita Paul, *The Burning Number Conjecture is true for Trees with Few Degree-2 Vertices*, SSRN 7276482, posted **13 August 2026**, 10 pages. The SSRN record explicitly states:

$$
n_2\le 2\lceil\sqrt n\rceil-3
\quad\Longrightarrow\quad
b(T)\le \lceil\sqrt n\rceil.
$$

([SSRN][1])

I also found the same four authors listed for a **CALDAM 2026 poster** under the earlier/different title *Towards the Burning Number Conjecture*. The conference page classifies it as a poster paper, not a regular proceedings paper. ([Google Sites][2])

I did **not** locate a later journal publication or a newer arXiv version of that exact 2026 title in the indexed material available to me. ResearchGate also treats it as a preprint rather than a peer-reviewed journal article. ([ResearchGate][3])

There is an important epistemic limitation: SSRN's full-text endpoint was not fetchable from this environment, so I could verify the **primary-source theorem statement and metadata**, but I could **not independently audit the Das–Islam–Mitra–Paul proof line-by-line**. I therefore do not regard their proof as independently re-certified here.

### A newer theorem that must not be confused with it

Ning–Jin–Zhang have a **peer-reviewed 2026 paper**, published in *Graphs and Combinatorics* on **2 March 2026**. Its exact theorem is

$$
b(T)\le
\left\lceil
\sqrt{
n+n_2-
\left\lceil
\sqrt{n+n_2+0.25}-1.5
\right\rceil
}
\right\rceil .
$$

It implies

$$
n_2\le \lfloor\sqrt{n-1}\rfloor
\quad\Longrightarrow\quad
b(T)\le\lceil\sqrt n\rceil.
$$

That is **not** the \(2\lceil\sqrt n\rceil-3\) theorem. ([Springer][4])

The arXiv version is v2 dated 5 September 2025, and the proof is publicly inspectable. In particular, their Theorem 5 is exactly the formula above, and Corollary 6 gives the \(\lfloor\sqrt{n-1}\rfloor\) threshold. ([arXiv][5])

So the preliminary claim you gave is **correct about Das et al.**, but it is easy to misread it as the main 2026 published theorem; it is not.

---

# 2. Candidate solved by existing theorem? **NO**

Your candidate is

$$
n_2=2q-2,\qquad q=\lceil\sqrt n\rceil,
$$

and asks whether \(b(T)\le q\).

Das et al. establish this only for

$$
n_2\le 2q-3.
$$

Your case is **exactly one degree-2 vertex beyond their stated range**.

So the 2026 Das theorem does **not** prove the candidate.

The Ning–Jin–Zhang theorem is also insufficient in general. For example, at a perfect square \(n=q^2\),

$$
n_2=2q-2,
$$

and their formula gives an upper bound of \(q+1\), not \(q\). Thus their theorem does not close your candidate at the square endpoint.

---

# 3. But an important part of the candidate is already solved indirectly

This is the most useful algebraic finding.

Das–Islam–Mitra–Paul's earlier 2023 paper proves, for \(n\ge50\),

$$
b(T)\le \left\lceil\sqrt{n+n_2+8}\right\rceil-1.
$$

([arXiv][6])

Substitute

$$
n_2=2q-2.
$$

Then

$$
b(T)\le
\left\lceil\sqrt{n+2q+6}\right\rceil-1.
$$

For this to imply \(b(T)\le q\), it is enough that

$$
n+2q+6\le(q+1)^2.
$$

Since

$$
(q+1)^2=q^2+2q+1,
$$

this is equivalent to

$$
\boxed{q^2-n\ge5}.
$$

Therefore, for \(n\ge50\), **the old general bound already proves your candidate except when**

$$
q^2-n\in\{0,1,2,3,4\}.
$$

Equivalently, the only potentially difficult orders are

$$
\boxed{n=q^2,\ q^2-1,\ q^2-2,\ q^2-3,\ q^2-4.}
$$

This substantially changes the character of the candidate.

It is **not** a completely unresolved statement over all \(n\). The genuinely interesting residue is concentrated in five orders immediately below each perfect square.

---

# 4. Candidate already explicitly studied? **NO**

I searched the exact formulation and close equivalent descriptions:

* \(2\lceil\sqrt n\rceil-2\) with burning number
* degree-2 threshold formulations
* subdivision/homeomorphic-tree formulations
* trees with one/two/multiple degree-2 vertices
* citations surrounding Murakami 2024
* Ning–Jin–Zhang 2026
* the Das–Islam–Mitra–Paul work
* the relevant author/citation records

I found the following related results:

Murakami proves the conjecture for trees with **zero** degree-2 vertices. ([Springer][7])

van der Tol's 2024 thesis proves it for trees with **one** degree-2 vertex and studies the corresponding cat-construct structure. ([TU Delft Repository][8])

Ning–Jin–Zhang give the stronger-looking **functional upper bound** above and consequently the \(\lfloor\sqrt{n-1}\rfloor\) degree-2 threshold. ([arXiv][5])

Das et al.'s 2026 SSRN preprint gives the \(2\lceil\sqrt n\rceil-3\) threshold. ([SSRN][1])

I found **no directly matching statement** of

$$
n_2=2\lceil\sqrt n\rceil-2
\Longrightarrow
b(T)\le\lceil\sqrt n\rceil.
$$

I would therefore answer **NO**, with the important qualification that absence from searchable literature is not a proof of novelty.

---

# 5. Counterexample found? **NO**

I also looked at the structural directions most likely to generate extremal examples.

### Subdivided stars / spiders

These are not promising counterexamples. Spiders are already a well-studied class for which the Burning Number Conjecture is known to hold. ([ScienceDirect][9])

So merely putting \(2q-2\) degree-2 vertices along the arms of a star does not threaten the conjecture.

### Subdivided paths

These are simply paths, and

$$
b(P_n)=\lceil\sqrt n\rceil.
$$

Thus they attain the conjectured bound but never exceed it. ([Springer][7])

### Caterpillar / double-star-type families

These are also poor candidates for a counterexample because substantial subclasses of caterpillars and related trees are already known to satisfy the conjecture. ([ScienceDirect][9])

### General homeomorphic expansions

This is where a genuine counterexample, if one exists, would have to live: a branching core with carefully distributed degree-2 chains, rather than a single long path-like arm.

No counterexample emerged from the exhaustive computation described below.

---

# 6. Small computational verification

I performed an **exact exhaustive enumeration of non-isomorphic trees through \(n=19\)** using NetworkX's generator for unlabeled trees.

For each tree I:

1. computed \(n_2\);
2. retained exactly those with

   $$
   n_2=2\lceil\sqrt n\rceil-2;
   $$
3. computed the exact burning number by an exact source-search using distance-ball coverage and source-separation constraints;
4. independently cross-checked the solver against direct simulation on all non-isomorphic trees up to \(n=8\).

The direct-simulation cross-check agreed in every case.

### Results

| \(n\) | \(\lceil\sqrt n\rceil\) | target \(n_2\) | candidate trees | burning numbers observed |
| ----: | ----------------------: | -------------: | --------------: | ------------------------ |
|     4 |                       2 |              2 |               1 | 2                        |
|     6 |                       3 |              4 |               1 | 3                        |
|     8 |                       3 |              4 |               4 | 3                        |
|     9 |                       3 |              4 |               5 | 3                        |
|    10 |                       4 |              6 |               7 | 3,4                      |
|    11 |                       4 |              6 |               9 | 3,4                      |
|    12 |                       4 |              6 |              53 | 3,4                      |
|    13 |                       4 |              6 |             108 | 3,4                      |
|    14 |                       4 |              6 |             383 | 3,4                      |
|    15 |                       4 |              6 |             959 | 3,4                      |
|    16 |                       4 |              6 |            2821 | 3,4                      |
|    17 |                       5 |              8 |            2938 | 3,4                      |
|    18 |                       5 |              8 |            9740 | 3,4                      |
|    19 |                       5 |              8 |           28235 | 3,4                      |

Thus:

$$
\boxed{\text{No counterexample exists for }n\le19.}
$$

In particular, **every one of the 44,000+ candidate trees at \(n=17,18,19\)** satisfies

$$
b(T)\le\lceil\sqrt n\rceil.
$$

I am deliberately not claiming a larger exhaustive range: \(n=20\) already has 823,065 unlabeled trees, and the straightforward exact search becomes substantially more expensive. The \(n=20\) computation did not finish, so it is **not** being counted as verified.

---

# 7. Boundary analysis

Let

$$
q=\lceil\sqrt n\rceil.
$$

### Boundary 1

$$
\boxed{n_2\le2q-3}
$$

This is exactly the range claimed by the Das–Islam–Mitra–Paul 2026 preprint. ([SSRN][1])

So this side is currently covered.

### Boundary 2

$$
\boxed{n_2=2q-2}
$$

This is your candidate.

No directly matching theorem was found, and the main known \(n,n_2\) upper bounds do not imply it uniformly.

### Boundary 3

$$
\boxed{n_2=2q-1}
$$

The same generic results do not uniformly establish the BNC here either.

Therefore the sequence

$$
2q-3,\quad 2q-2,\quad 2q-1
$$

should **not** presently be interpreted as three proved mathematical phases.

What is genuinely meaningful is:

$$
2q-3
$$

is a threshold appearing in the **current Das theorem**, while

$$
2q-2
$$

is the immediate next case.

There is currently no evidence that nature itself has chosen \(2q-3\) as a sharp transition.

So the boundary is **theorem-induced**, not yet known to be an intrinsic extremal boundary.

---

# 8. Exact logical status

$$
\boxed{\textbf{D = apparently unresolved and potentially underexplored}}
$$

I would **not** assign A, because no existing theorem I found proves it.

I would **not** assign B, because no counterexample was found.

I would **not** assign C, because I found no directly matching formulation explicitly posed or studied.

I would **not** assign E, because there is enough positive evidence to say it is more than merely “interesting but poorly characterized”: it sits at a very precise boundary immediately beyond an actual 2026 theorem, and the old general bound reduces the genuinely difficult part to a narrow near-square regime.

So D is the best classification.

---

# 9. Confidence

$$
\boxed{\textbf{82\%}}
$$

The main uncertainty is **not** the algebra or computation. It is literature completeness and, especially, the inability to independently inspect the full Das–Islam–Mitra–Paul SSRN manuscript line-by-line because its full-text endpoint was inaccessible here.

---

# 10. Why it remains interesting

This candidate survives scrutiny for a much more precise reason than “AI couldn't find a proof.”

The picture is:

$$
\boxed{
\begin{array}{c}
n_2\le2q-3
\\[2mm]
\text{proved by Das et al.}
\\
\downarrow
\\[-1mm]
n_2=2q-2
\\
\text{your candidate}
\\
\downarrow
\\[-1mm]
n_2=2q-1
\\
\text{also not covered uniformly}
\end{array}}
$$

At the same time, the 2023 upper bound shows that your statement is already settled for all sufficiently large \(n\) except the five values

$$
n=q^2-r,\qquad r=0,1,2,3,4.
$$

Thus the real mathematical core is approximately:

$$
\boxed{
n=q^2-r,\quad
r\in\{0,1,2,3,4\},\quad
n_2=2q-2
}
$$

rather than the entire infinite family in its raw form.

That makes the candidate much sharper than it initially appears.

### Research-value assessment

**Naturalness:** high. It is directly tied to the BNC and to the degree-2 interpolation between path-like and branching trees.

**Difficulty:** high enough to be nontrivial, but structurally constrained. It is not obviously an undergraduate one-week proof.

**Computation:** very good. Exact enumeration is practical at small \(n\), and the candidate has a particularly clear near-square test regime.

**Special cases:** promising. Spiders, paths, caterpillar-like trees, and small cores are natural first restrictions.

**Counterexample search:** meaningful. The difficult examples would likely require branching cores plus a highly nontrivial distribution of the \(2q-2\) subdivisions.

**Publishability:** a complete proof would be potentially interesting because it would extend an active 2026 threshold by exactly one; even a sharp structural reduction for the five near-square orders could be worthwhile.

**Undergraduate project:** a full proof is probably ambitious; an exact-computation + structural-special-cases project is much more realistic.

---

# Final verdict

**1. Latest theorem verified:**
Yes at the statement/metadata level. Das–Islam–Mitra–Paul have a 13 August 2026 SSRN preprint whose stated theorem is exactly

$$
n_2\le2\lceil\sqrt n\rceil-3
\Longrightarrow b(T)\le\lceil\sqrt n\rceil.
$$

It is a preprint/working paper, not a journal version I could locate. ([SSRN][1])

A separate peer-reviewed 2026 theorem by Ning–Jin–Zhang gives a different functional bound and only the threshold \(\lfloor\sqrt{n-1}\rfloor\). ([Springer][4])

**2. Candidate solved by existing theorem?** **NO**

**3. Candidate already explicitly studied?** **NO**

**4. Counterexample found?** **NO**

**5. Small computational evidence:** exhaustive exact verification of all candidate trees through \(n=19\); no counterexample. The largest completed exhaustive case is \(n=19\), with **28,235** candidate trees, all having \(b(T)\le5\).

**6. Exact logical status:** **D — apparently unresolved and potentially underexplored**

**7. Confidence:** **82%**

**8. Precise reason it remains interesting:** it is exactly one degree-2 vertex beyond the Das et al. threshold, while the older general bound already reduces the genuinely unresolved part to the five near-square orders \(n=q^2,q^2-1,\ldots,q^2-4\).

**9. Single best next experiment/proof attempt:**
Focus exclusively on

$$
\boxed{n=q^2-r,\quad r=0,1,2,3,4,\qquad n_2=2q-2}
$$

and try to extend the **leaf-augmentation/smoothing argument underlying the 2026 degree-2 results by one extra degree-2 vertex**. In parallel, exact-compute this near-square residue for increasing \(q\). The perfect-square case \(n=q^2,\ n_2=2q-2\) is the cleanest first target, because neither the existing 2023 bound nor the Ning–Jin–Zhang bound reaches \(q\) there.

This candidate therefore **survives the adversarial audit**, but the correct description is **“apparently unresolved and potentially underexplored,” not “a new open problem.”**

[1]: https://papers.ssrn.com/sol3/papers.cfm?abstract_id=7276482&utm_source=chatgpt.com "The Burning Number Conjecture is true for Trees with Few Degree-2 Vertices by Sandip Das, Sk Samim Islam, Ritam Manna Mitra, Sanchita Paul :: SSRN"
[2]: https://sites.google.com/iitdh.ac.in/caldam-2026/accepted-papers?utm_source=chatgpt.com "Accepted Papers"
[3]: https://www.researchgate.net/publication/412226238_The_Burning_Number_Conjecture_is_true_for_Trees_with_Few_Degree-2_Vertices?utm_source=chatgpt.com "The Burning Number Conjecture is true for Trees with Few Degree-2 Vertices | Request PDF"
[4]: https://link.springer.com/article/10.1007/s00373-026-03024-w "The burning number conjecture holds for trees of order n with at most $$\left\lfloor \sqrt{n-1}\right\rfloor $$ degree-2 vertices | Graphs and Combinatorics | Springer Nature Link"
[5]: https://arxiv.org/html/2509.03144 "The burning number conjecture holds for trees of order 𝑛 with at most ⌊√{𝑛-1}⌋ degree-2 vertices"
[6]: https://arxiv.org/abs/2308.02825?utm_source=chatgpt.com "Burning a binary tree and its generalization"
[7]: https://link.springer.com/article/10.1007/s00373-024-02812-6?utm_source=chatgpt.com "The Burning Number Conjecture is True for Trees without Degree-2 Vertices | Graphs and Combinatorics | Springer Nature Link"
[8]: https://repository.tudelft.nl/record/uuid%3A3cbca1c6-a687-4bd4-870d-ad48ba18c9f6?utm_source=chatgpt.com "The burning number conjecture | TU Delft Repository"
[9]: https://www.sciencedirect.com/science/article/abs/pii/S0096300322006488?utm_source=chatgpt.com "Burnability of double spiders and path forests - ScienceDirect"
