---
title: "The Gale-Shapley Algorithm"
source: "Osborne & Rubinstein (2020), §18.2 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - matching
  - gale-shapley
  - deferred-acceptance
prerequisites:
  - mechanism-design-and-matching/the-matching-problem-and-matching-methods
---
## Deferred acceptance: proposals and tentative holds

The **Gale-Shapley algorithm** comes in two versions — one where the $X$'s initiate matches (denoted $\mathrm{GS}^X$) and one where the $Y$'s do ($\mathrm{GS}^Y$). We describe $\mathrm{GS}^X$; $\mathrm{GS}^Y$ is the mirror image with the roles of $X$ and $Y$ swapped.

**Stage 1.** Each $X$ chooses (proposes to) her favorite $Y$. If every $Y$ is chosen by exactly one $X$, the algorithm ends with that matching. Otherwise, every $Y$ chosen by more than one $X$ picks her favorite among those who chose her, becomes *tentatively* matched to that $X$, and rejects the rest. $X$'s chosen by nobody remain unmatched.

**Stage $t+1$ (for $t\geq1$).** Each unmatched $X$ proposes to her favorite $Y$ among those who have not yet rejected her. Each $Y$ then picks her favorite from the set consisting of (i) whoever she was tentatively matched with at the end of stage $t$ and (ii) the newly unmatched $X$'s who just proposed to her — forming new tentative matches (and possibly rejecting an $X$ she was previously holding, if a more preferred one has just proposed).

**Stopping rule.** The process ends once every $X$ is tentatively matched with a $Y$; those tentative matches become final. A rejected $Y$ is never proposed to again by the same $X$ — rejections are permanent, which is exactly what drives the algorithm toward termination.

The formal version of the procedure tracks, at the end of stage $t$, a tentative-match function $g_t:X\to Y\cup\{\text{unmatched}\}$ (injective on its matched values) and a rejection record $R_t(x)\subseteq Y$ for each $x$ — the set of $Y$'s who have rejected $x$ so far. Starting from $g_0(x)=\text{unmatched}$ and $R_0(x)=\varnothing$ for all $x$, stage $t+1$ has each $y$ receive proposals from $A_{t+1}(y)=\{x\in X: y \text{ is best in } Y\setminus R_t(x) \text{ according to } x\}$, sets $g_{t+1}(x)=y$ for whichever $x$ is $y$'s favorite in $A_{t+1}(y)$ (unmatched otherwise), and updates $R_{t+1}(x)$ by adding any $y$ that just rejected $x$. The algorithm ends at the first stage $T$ with $g_T(x)\in Y$ for all $x$.

As with [serial dictatorship](../equilibrium-foundations/the-jungle-model-and-equilibrium.md), the language of individuals "choosing" is a vivid description of a purely mechanical function from preference profiles to matchings, not a claim about deliberate strategic behavior at each stage.

## Worked example

**Example 18.4.** Take four $X$'s and four $Y$'s with preferences (most-preferred first): $X_1: Y_1Y_4Y_2Y_3$, $X_2: Y_2Y_3Y_1Y_4$, $X_3: Y_4Y_2Y_3Y_1$, $X_4: Y_4Y_3Y_1Y_2$; and $Y_1: X_3X_1X_2X_4$, $Y_2: X_3X_2X_4X_1$, $Y_3: X_4X_3X_2X_1$, $Y_4: X_1X_4X_3X_2$.

Running $\mathrm{GS}^X$: **Stage 1** — $X_1$ chooses $Y_1$, $X_2$ chooses $Y_2$, and both $X_3$ and $X_4$ choose $Y_4$; $Y_4$ prefers $X_4$ to $X_3$ and rejects $X_3$, so after stage 1 $X_1$–$Y_1$, $X_2$–$Y_2$, and $X_4$–$Y_4$ are tentative, while $X_3$ is unmatched (rejected once, by $Y_4$). **Stage 2** — $X_3$'s next favorite is $Y_2$; she proposes, and $Y_2$ prefers $X_3$ to her current tentative match $X_2$, so $Y_2$ rejects $X_2$ and holds $X_3$. **Stage 3** — $X_2$'s next favorite is $Y_3$, who is unmatched and accepts. Every $Y$ is now held by exactly one $X$, so the algorithm ends with $\mu(X_1)=Y_1$, $\mu(X_2)=Y_3$, $\mu(X_3)=Y_2$, $\mu(X_4)=Y_4$.

Running $\mathrm{GS}^Y$ (the $Y$'s propose instead) on the very same profile — the mirror-image procedure, worked out stage-by-stage in the source — happens to terminate at this **identical** matching. This is not a general fact: for many preference profiles $\mathrm{GS}^X$ and $\mathrm{GS}^Y$ produce genuinely different matchings, a point sharpened in [the entry on optimality for the proposing side](optimality-of-gale-shapley-for-proposers.md).

## The algorithm always produces a matching

**Proposition 18.1.** For any society and any preference profile, the Gale-Shapley algorithm is well defined and generates a matching.

*Proof.* *Well-defined:* suppose, for contradiction, that at some stage $t$ some $x\in X$ has been rejected by *every* $Y$ (i.e. $R_t(x)=Y$). Whenever a $Y$ rejects an $X$, she remains tentatively matched with some other $X$ — rejection never leaves a $Y$ unmatched. So if every $Y$ has, at some point, rejected $x$, every $Y$ must currently be tentatively matched to someone. Since $|X|=|Y|$, this forces $x$ herself to be tentatively matched to some $Y$ — but then that $Y$ has not rejected $x$, contradicting $R_t(x)=Y$.

*Terminates:* at every stage the algorithm continues, at least one $X$ is newly rejected (otherwise it would have stopped). Since there are finitely many $(x,y)$ pairs and each rejection is permanent, if the algorithm never stopped some $x$ would eventually be rejected by every $Y$ — which the previous paragraph rules out. So it must terminate in finitely many stages.

*Terminates in a matching:* the stopping rule fires exactly when every $X$ is tentatively matched, i.e. $g_T$ is already a one-to-one function from $X$ onto $Y$ — a matching by [Definition 18.2](the-matching-problem-and-matching-methods.md). $\blacksquare$

This is structurally the same style of argument as [existence via top trading cycles](../equilibrium-foundations/top-trading-cycles-and-existence.md): a simple, always-terminating finite procedure whose termination *is* the existence proof, no fixed-point argument required.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §18.2. The chapter is based on Gale and Shapley (1962).*
