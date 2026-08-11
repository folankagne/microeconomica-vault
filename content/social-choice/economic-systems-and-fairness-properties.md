---
title: "Economic Systems and Fairness Properties"
source: "Osborne & Rubinstein (2020), §§19.1–19.2 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - social-choice
  - fairness
  - socialism
prerequisites:
  - exchange-economies/welfare-theorems-and-the-core
---
## The model: productivity, input, and wealth

A society of $n$ individuals shares a fixed unit of **input** (e.g. land); individual $i$'s **productivity** $\lambda_i\geq0$ converts an amount $\alpha_i$ of input into wealth $\alpha_i\lambda_i$. A **distribution of input** is $(\alpha_1,\dots,\alpha_n)$ with $\sum_i\alpha_i=1$; a **feasible wealth profile** for productivity profile $(\lambda_1,\dots,\lambda_n)$ is any $(w_1,\dots,w_n)$ with $\sum_i w_i=\sum_i\alpha_i\lambda_i$ for some such distribution. An **economic system** $F$ is a rule mapping every productivity profile to a feasible wealth profile — deliberately silent about *who produces what*, only about who ends up with how much wealth.

Six examples the chapter builds toward its central result with: (1) *equality of input, no redistribution* — $F_i=\lambda_i/n$; (2) *input to most productive, no redistribution* — the most productive individuals split the input and keep what they produce, everyone else gets zero; (3) *equality of input, equality of wealth* — total wealth $\sum_j\lambda_j/n$ divided equally; (4) *input to most productive, equality of wealth* — **socialism**: $F_i=\max\{\lambda_1,\dots,\lambda_n\}/n$ for every $i$, one formalization of "from each according to her ability, to each according to her needs" (Marx 1971) when needs are identical; (5) *one worker, one beneficiary* — a "master/slave" system where a fixed individual $j_1$ works and a fixed individual $j_2$ collects everything; (6) *input to most productive, wealth relative to productivity* — output goes to the most productive, but is then split among *everyone* in proportion to $\lambda_i$.

## Five properties an economic system might satisfy

**Efficiency.** No feasible wealth profile Pareto-dominates $F$'s output — equivalently, $F$ always allocates the input to the *most* productive individuals, extracting the maximum total wealth $M=\max\{\lambda_1,\dots,\lambda_n\}$. This is the [Pareto stability](../exchange-economies/welfare-theorems-and-the-core.md) concept from exchange economies, restated for a production-only setting. Only systems (2), (4), and (6) are efficient.

**Symmetry.** Individuals with equal productivity get equal wealth. Satisfied by everything except (5).

**Relative monotonicity.** $\lambda_i\geq\lambda_j\Rightarrow F_i\geq F_j$ — a more productive individual never gets less. Also fails only for (5).

**Anonymity.** Permuting *which individual has which productivity* permutes the wealth outcomes correspondingly — the rule cannot depend on individuals' names, only on the *profile* of productivities. Anonymity **implies** symmetry but is strictly stronger (a rule can treat equal-productivity individuals equally without being invariant to relabeling productivities among unequal individuals). Fails only for (5).

**Monotonicity in own productivity.** Increasing $\lambda_i$ (holding everyone else fixed) never decreases $F_i$. Satisfied by *all six* examples, including (5).

**Monotonicity in others' productivities.** Increasing $\lambda_i$ never *decreases* anyone else's wealth $F_j$. Fails for exactly the two systems, (2) and (6), that give the input exclusively to the currently-most-productive individuals — a productivity increase there can bump a previously-tied individual entirely out of "most productive," collapsing her wealth to zero.

These properties split into two logical types: efficiency, symmetry, and relative monotonicity constrain what $F$ does *at a single productivity profile*; anonymity and the two "monotonicity" properties constrain how $F$'s output *changes* as the profile changes — exactly the same distinction between static and comparative-statics axioms that recurs in [preference aggregation](preference-aggregation-functions.md), where neutrality/anonymity are "static" symmetries and positive responsiveness is a comparative-statics condition.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§19.1–19.2.*
