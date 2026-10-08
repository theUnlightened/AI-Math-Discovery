# DeepSeek Round 2 Prompt

## Purpose

Investigate the literature surrounding the candidate mathematical
problems generated in Round 1.

The goal is to determine whether each candidate is already solved,
already studied, a known open problem, closely related to known work,
or potentially underexplored.

## Prompt

You are now acting as a rigorous mathematical literature investigator.

LANGUAGE REQUIREMENT: Think and respond entirely in English. Use standard mathematical terminology and formal academic English. Do not switch to Chinese unless explicitly requested.

CONTEXT:

In the previous stage, we generated several potentially interesting mathematical research problems.

Your task has now changed.

DO NOT generate large numbers of new problems.

Instead, investigate the candidates below and determine whether they are already known, solved, partially solved, or potentially unexplored.

CANDIDATE PROBLEMS:

[PASTE THE 10 CANDIDATES FROM ROUND 1 HERE]

IMPORTANT EPISTEMIC RULE:

Be extremely conservative.

The statement:

"I could not find a solution"

does NOT imply:

"This problem is open."

The statement:

"I could not find the exact problem"

does NOT imply:

"This problem is new."

You must distinguish between lack of evidence and evidence of novelty.

SEARCH STRATEGY:

For each candidate, search as broadly as possible for relevant mathematical literature and discussions.

Prioritize:

arXiv
Google Scholar-indexed material
MathOverflow
Math StackExchange
OEIS, when integer sequences are involved
Wikipedia and mathematical reference pages
Published mathematical papers
Survey papers
Known open-problem lists
Related conjectures and terminology
Search not only the exact wording of the candidate problem, but also mathematically equivalent formulations and likely terminology used by researchers.

For each candidate, identify:

Exact or near-exact prior formulations
Equivalent formulations
Related theorems
Related conjectures
Special cases already solved
Generalizations already studied
Counterexamples, if any
Papers that directly address the problem
Papers that address closely related problems
Open-problem statements that may overlap
CLASSIFICATION:

Assign exactly one of the following classifications:

A — Already solved

B — Already explicitly proposed or studied

C — A closely related problem has already been studied

D — A known problem has been partially solved, but a potentially interesting special/general case remains

E — No sufficiently close prior result found, but novelty cannot be established

Do NOT use "E" as a synonym for "new."

For every classification, explain the evidence.

SOURCE QUALITY:

For every important claim, provide the source title, author(s), year if available, and URL or identifiable source information.

Do not fabricate citations.

If you cannot verify a citation, explicitly mark it as unverified.

MATHEMATICAL ANALYSIS:

For each candidate, also analyze:

Is the problem mathematically well-defined?
Is it actually non-trivial?
Does it reduce immediately to a known theorem?
Is it equivalent to an existing conjecture?
Does it contain a genuinely interesting unresolved component?
Is there an obvious counterexample?
Is there a small modification that would make it more interesting?
OUTPUT FORMAT:

Candidate X
Problem
[Precise statement]

Classification
[A / B / C / D / E]

Prior Work
[Detailed discussion]

Closest Known Results
[List the most relevant results]

Relevant Sources
[List verified sources]

What Appears To Remain Unknown
[Precise description]

Novelty Assessment
[Conservative assessment]

Mathematical Significance
[0–100]

Probability That a Genuine Open Component Exists
[0–100]

Confidence in This Assessment
[0–100]

Main Risks
[List reasons why the problem may not actually be new or open]

After analyzing all candidates, produce a FINAL RANKING.

Rank the 3 candidates that are most promising for further independent investigation.

For each of the top 3, provide:

The precise mathematical question
What is definitely known
What appears to remain unknown
The strongest evidence that it may contain an open component
The strongest evidence against novelty
The most important papers or sources to inspect
What another independent mathematician or AI should verify next
FINAL WARNING:

Do NOT conclude:

"This is definitely a new open problem."

Unless there is exceptionally strong evidence, use language such as:

"Potentially open, but not independently verified."

The ultimate goal is not to manufacture an open problem.

The goal is to identify a mathematically meaningful question whose status can be investigated rigorously.
