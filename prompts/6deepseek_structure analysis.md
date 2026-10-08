You are now working on the **structural-analysis stage** of a mathematical research investigation.

Do NOT try to prove or disprove the main conjecture yet.

Do NOT generate new research problems.

Your task is to determine what trees could possibly be extremal or counterexample candidates.

---

# Research Candidate

Let \(T\) be a tree on \(n\) vertices, and let \(n_2\) denote the number of vertices of degree \(2\) in \(T\).

We are investigating:

$$
n_2 = 2\lceil\sqrt n\rceil-2
\quad\Longrightarrow\quad
b(T)\le \lceil\sqrt n\rceil?
$$

Let

$$
q=\lceil\sqrt n\rceil.
$$

A 2026 preprint by Das, Islam, Mitra and Paul claims that

$$
n_2\le 2\lceil\sqrt n\rceil-3
\quad\Longrightarrow\quad
b(T)\le \lceil\sqrt n\rceil.
$$

Thus our candidate is exactly one degree-2 vertex beyond that claimed threshold.

Furthermore, an earlier bound implies that for \(n\ge 50\), the candidate is automatically true unless

$$
n=q^2-r,\qquad r\in\{0,1,2,3,4\}.
$$

Therefore the genuinely interesting cases are

$$
n=q^2-r,\qquad r=0,1,2,3,4,
$$

together with

$$
n_2=2q-2.
$$

---

# Your Task

## 1. Analyze the exact structural constraints

For trees satisfying

$$
n=q^2-r,\qquad r\in\{0,1,2,3,4\},
$$

and

$$
n_2=2q-2,
$$

derive all exact structural identities that follow from the definition of a tree.

In particular analyze:

* the number of leaves;
* the number of vertices of degree at least \(3\);
* the maximum possible degree;
* the relationship between leaves and branching vertices;
* constraints on the degree sequence;
* constraints imposed by \(n_2=2q-2\).

Do not merely give qualitative observations. Derive exact formulas or rigorous inequalities whenever possible.

---

# 2. Suppress all degree-2 vertices

Let \(H\) be the tree obtained from \(T\) by suppressing every degree-2 vertex.

Equivalently, each edge \(e\) of \(H\) is subdivided by some number \(s_e\ge0\) of degree-2 vertices to obtain \(T\).

Then

$$
n=|V(H)|+\sum_e s_e
$$

and

$$
n_2=\sum_e s_e.
$$

Use

$$
n=q^2-r
$$

and

$$
n_2=2q-2
$$

to determine exactly

$$
|V(H)|.
$$

Work out the five cases \(r=0,1,2,3,4\).

Explain carefully what these identities imply about the possible structure of \(H\).

Do NOT assume that \(H\) is small or simple merely because it is a degree-2-free tree.

---

# 3. Analyze the subdivision structure

Represent \(T\) as

$$
(H,(s_e)_{e\in E(H)}).
$$

Study the integer vector

$$
(s_e)_{e\in E(H)}
$$

under the constraint

$$
\sum_e s_e=2q-2.
$$

Determine what can and cannot happen.

In particular investigate:

* all \(2q-2\) degree-2 vertices concentrated on a few edges;
* degree-2 vertices distributed nearly uniformly;
* long subdivided paths;
* many short subdivisions;
* mixtures of long and short subdivisions.

Determine whether any of these patterns are naturally associated with large burning number.

---

# 4. Search for potentially extremal tree families

Do NOT study all trees equally.

Try to identify the structures that could plausibly maximize \(b(T)\) under

$$
n_2=2q-2.
$$

At minimum investigate:

1. paths;
2. spiders;
3. subdivided stars;
4. brooms;
5. double-stars;
6. subdivided double-stars;
7. caterpillars;
8. trees with several high-degree branching vertices;
9. trees where degree-2 vertices are concentrated on a few edges;
10. trees where degree-2 vertices are distributed across many edges.

For each family determine, as far as possible:

* \(n\);
* \(n_2\);
* \(b(T)\);
* relevant degree information;
* whether it can satisfy the near-square condition;
* whether it could possibly have

$$
b(T)\ge q+1.
$$

Do not force a family to be extremal if the evidence does not support it.

---

# 5. Analyze the five near-square cases separately

Study:

### Case A

$$
n=q^2.
$$

### Case B

$$
n=q^2-1.
$$

### Case C

$$
n=q^2-2.
$$

### Case D

$$
n=q^2-3.
$$

### Case E

$$
n=q^2-4.
$$

In every case,

$$
n_2=2q-2.
$$

Compare the structural constraints between these five cases.

Determine whether one of the five cases is substantially more likely to contain a counterexample.

If so, identify the most promising case and explain why.

---

# 6. Investigate the existing literature

Perform a serious literature search.

Search for results involving:

* Burning Number Conjecture;
* trees with degree-2 vertices;
* burning number and subdivisions;
* burning number and leaves;
* burning number and maximum degree;
* subdivision trees;
* subdivided trees;
* homeomorphic trees;
* homeomorphically irreducible trees;
* suppressing degree-2 vertices;
* smoothing degree-2 vertices.

Pay particular attention to:

1. Murakami (2024);
2. Ning–Jin–Zhang (2026);
3. Das–Islam–Mitra–Paul (2026);
4. Das et al. (2023).

Do not merely inspect titles or abstracts if the full text is available.

Determine whether any existing theorem already gives structural information directly relevant to our boundary case.

If you cannot access the full proof of a claimed result, explicitly say so.

Do not treat search failure as evidence that something is unexplored.

---

# 7. Investigate the proof mechanism behind the \(2q-3\) threshold

This is particularly important.

The 2026 result claims

$$
n_2\le2q-3
\quad\Longrightarrow\quad
b(T)\le q.
$$

Study the proof carefully if accessible.

Identify exactly where the inequality

$$
n_2\le2q-3
$$

is used.

Then ask:

> What changes if one additional degree-2 vertex is allowed?

Specifically determine:

* which step of the argument becomes tight;
* whether the obstruction is genuinely structural;
* whether the extra degree-2 vertex merely breaks a technical estimate;
* whether the existing proof strategy might plausibly extend to \(2q-2\);
* whether a new local argument could handle the additional vertex.

Do NOT assume that the threshold \(2q-3\) is a true mathematical phase transition.

---

# 8. Develop rigorous structural lemmas

Try to formulate intermediate lemmas that could eventually be useful for proving or disproving the candidate.

Examples include statements of the form:

> Every potential counterexample must satisfy ...

or

> If \(T\) belongs to a certain structural class, then \(b(T)\le q\).

or

> A potential counterexample cannot have ...

Every statement must be classified as exactly one of:

### [PROVED]

A rigorous consequence of definitions or established theorems.

### [STRONG EVIDENCE]

Supported by computation or substantial experimental evidence but not proved.

### [CONJECTURAL]

A plausible structural hypothesis that still requires proof.

Never present a conjectural pattern as a theorem.

---

# 9. Design a computational experiment

Do not merely say “run computations.”

Design a concrete experiment.

For increasing \(q\), generate trees satisfying

$$
n=q^2-r,\qquad r\in\{0,1,2,3,4\},
$$

and

$$
n_2=2q-2.
$$

For each tree:

1. compute the exact burning number;
2. find the maximum \(b(T)\);
3. record all trees attaining the maximum, when feasible;
4. record:

   * degree sequence;
   * number of leaves;
   * maximum degree;
   * number of vertices of degree at least \(3\);
   * suppressed core \(H\);
   * subdivision-length distribution \((s_e)\).

The main goal is to identify:

> What do the most dangerous trees actually look like?

If exhaustive enumeration becomes infeasible, propose:

* structured enumeration;
* random generation;
* targeted search;
* optimization over tree families;
* SAT/ILP formulations;
* dynamic programming;
* other mathematically justified approaches.

Clearly distinguish exact computation from heuristic search.

---

# 10. Identify the most promising next step

At the end, provide a clear research recommendation.

If we are allowed to do only ONE thing next, choose exactly one:

**A. Search aggressively for a counterexample**

**B. Perform larger-scale exact computation**

**C. Prove a structural lemma**

**D. Attempt to prove the original conjecture**

**E. Focus on one special extremal tree family**

Choose exactly one and explain why it is the best next step.

---

# Required Final Output

Organize your answer exactly as follows:

1. **Structural Summary**
2. **Exact Structural Identities**
3. **Five Near-Square Cases**
4. **Candidate Extremal Families**
5. **Existing Literature Connections**
6. **Analysis of the \(2q-3\) Threshold**
7. **Proven Structural Lemmas**
8. **Strong Computational Evidence**
9. **Conjectural Structural Patterns**
10. **Best Computational Experiment**
11. **Best Next Mathematical Step**

---

# Strict Research Standards

1. Do NOT claim that this is a new open problem.
2. Do NOT claim novelty merely because you cannot find a paper.
3. Do NOT confuse “maximum” with “maximal”.
4. Do NOT turn computational evidence into a proof.
5. Do NOT turn a plausible pattern into a theorem.
6. Do NOT silently assume a structural classification that has not been proved.
7. Cite primary sources whenever possible.
8. Give exact bibliographic information for important results.
9. If a source is a preprint rather than a peer-reviewed publication, say so explicitly.
10. If you cannot verify a claim, mark it as unverified.
11. Do not attempt a final proof of the main conjecture in this round.
12. The sole purpose of this round is:

**Determine what a potential extremal or counterexample tree could actually look like.**
