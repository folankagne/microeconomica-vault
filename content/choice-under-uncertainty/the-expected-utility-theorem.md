---
title: "The Expected Utility Theorem"
source: "Osborne & Rubinstein (2020), §3.3"
status: enriched
tags:
  - expected-utility
  - von-neumann-morgenstern
  - bernoulli-function
prerequisites:
  - choice-under-uncertainty/continuity-and-independence-axioms
---
## The expected utility form

**Definition.** $\succeq$ on $L(Z)$ is **consistent with expected utility** if there's a function $v:Z\to\mathbb{R}$ (the **Bernoulli function**, or value of a prize) such that $\succeq$ is represented by $U(p)=\sum_{z\in Z}p(z)v(z)$ — rank lotteries by their *expected* Bernoulli value.

This is a strictly narrower class than [general utility representability](../preferences-and-choice/utility-representation-theorem.md): every expected-utility preference is representable by *some* utility function ($U$ itself), but not every utility function on $L(Z)$ takes the linear-in-probabilities form $U(p)=\sum_z p(z)v(z)$.

## The characterization (von Neumann–Morgenstern)

**Proposition (necessity).** Expected utility $\Rightarrow$ continuity and independence.

*Proof:* for continuity, given $[a]\succ[b]\succ[c]$ so $v(a)>v(b)>v(c)$, set $\alpha = (v(b)-v(c))/(v(a)-v(c)) \in(0,1)$; then $\alpha v(a)+(1-\alpha)v(c)=v(b)$ exactly, giving the required indifference. For independence, the defining equivalence reduces algebraically — expand $U$ on both compound lotteries, the shared terms cancel, and what remains is precisely the comparison $v(z_k)$ vs. $\beta v(a)+(1-\beta)v(b)$, i.e. exactly the independence condition. $\blacksquare$

**Proposition (sufficiency — the main theorem).** Continuity and independence on a *finite* prize set $\Rightarrow$ consistent with expected utility.

*Proof idea:* order prizes $[z_1]\succeq\cdots\succeq[z_K]$, let $M=z_1$ (best), $m=z_K$ (worst). If $[M]\sim[m]$, everyone's indifferent to everything (by independence, every lottery is a compound of $M$'s and $m$'s, all indifferent) — take $v\equiv0$, done. Otherwise $[M]\succ[m]$: by continuity, every prize $z$ has a unique $v(z)\in[0,1]$ with $[z]\sim v(z)\cdot M\oplus(1-v(z))\cdot m$ — literally define the Bernoulli value of $z$ as the probability mixture of best-and-worst that's indifferent to $z$ for certain. Substituting this into any lottery $p$ and applying independence $K$ times collapses $p$ to a compound $M$-or-$m$ lottery with $M$-probability $\sum_k p(z_k)v(z_k)$; [the monotonicity lemma](continuity-and-independence-axioms.md) then says comparing two such lotteries reduces exactly to comparing these sums — which *is* comparing $\sum p(z_k)v(z_k)$, the expected-utility formula. $\blacksquare$

Together, the two propositions give **continuity + independence $\iff$ expected utility** — a full characterization, not just a sufficient condition, in the same spirit as [property $\alpha$'s characterization of rationalizable choice](../preferences-and-choice/property-alpha-and-the-rationalizability-theorem.md).

## Uniqueness: Bernoulli functions are cardinal, not ordinal

Unlike [ordinary utility functions](../preferences-and-choice/utility-representation-theorem.md), which are unique only up to an *arbitrary strictly increasing* transformation, a Bernoulli function representing a given expected-utility preference is unique only up to a **positive affine** transformation: if $v$ works, so does $w(z)=\alpha v(z)+\beta$ for any $\alpha>0$ — and, going the other way (stated without proof here), *any* two Bernoulli functions representing the same preference must be related this way. This is strictly more restrictive than ordinary ordinal utility: $v^2$ or $\sqrt{v}$ generally do **not** represent the same expected-utility preference as $v$, even though they'd represent the same *ordinary* preference relation over sure things. The reason the class of admissible transformations shrinks is exactly independence: it forces $U$ to stay *linear* in probabilities, and only affine transformations of $v$ preserve that linearity. This cardinality is what makes [risk aversion](risk-aversion-and-the-bernoulli-function.md) — a statement about the *curvature* (concavity) of $v$, not just its ranking — a meaningful, representation-independent property.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §3.3. Original theorem: von Neumann & Morgenstern (1947).*
