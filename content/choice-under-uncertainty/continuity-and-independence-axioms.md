---
title: "Continuity and Independence"
source: "Osborne & Rubinstein (2020), §3.2.1"
status: enriched
tags:
  - independence-axiom
  - continuity
  - compound-lottery
prerequisites:
  - choice-under-uncertainty/lotteries-and-preferences-over-lotteries
---
## Continuity: no prize is infinitely better than another

**Definition.** $\succeq$ on $L(Z)$ is continuous if for any prizes $[a]\succ[b]\succ[c]$, some mixture $\alpha\cdot a\oplus(1-\alpha)\cdot c$ is exactly indifferent to $[b]$, for some $\alpha\in(0,1)$.

Sliding continuously from the lottery $[a]$ ($\alpha=1$) to $[c]$ ($\alpha=0$), preference must cross $[b]$'s value at some point along the way — an intermediate-value requirement, structurally the same idea as [continuity of preferences over bundles](../consumer-theory/monotonicity-continuity-and-convexity.md). **Pessimistic preferences fail this** whenever $Z$ has 3+ prizes: since the pessimist only ever looks at the *worst* prize in the support, $\alpha\cdot a\oplus(1-\alpha)\cdot c$ is ranked by $c$ (the worse of $a,c$) for *every* $\alpha<1$ — the lottery never crosses $[b]$'s value continuously, it just jumps from "as good as $[a]$" (at $\alpha=1$ exactly) straight to "as bad as $[c]$" everywhere else. Good-and-bad and minimizing-options preferences satisfy continuity only **vacuously** — there's no triple $[a]\succ[b]\succ[c]$ to test against in the first place (good-and-bad only ever produces two indifference classes; minimizing-options ranks purely by support size, giving no strict three-way ranking of degenerate lotteries either).

## Independence: irrelevant common consequences shouldn't affect ranking

**Definition — compound lottery.** Given lotteries $p_1,\dots,p_K$ and weights $\alpha_1,\dots,\alpha_K$ summing to 1, $\alpha_1\cdot p_1\oplus\cdots\oplus\alpha_K\cdot p_K$ is the two-stage lottery: draw $p_k$ with probability $\alpha_k$, then draw a prize from $p_k$. Its reduced form assigns each prize $z$ probability $\sum_k \alpha_k p_k(z)$.

**Definition — independence.** $[z_k]\succeq \beta\cdot a\oplus(1-\beta)\cdot b$ if and only if replacing the $k$-th slot of *any* compound lottery with $z_k$ versus with $\beta\cdot a\oplus(1-\beta)\cdot b$ preserves the same ranking, holding every other slot fixed.

The logic: two lotteries that agree everywhere except in one slot should be compared exactly the way that one differing slot is compared — a component-wise, "cancel the common parts" principle. **Pessimistic preferences violate this**: with $[a]\succ[b]$, the lotteries $p=0.6\cdot a\oplus0.4\cdot b$ and $q=0.6\cdot b\oplus0.4\cdot b=[b]$ differ only in the first slot ($a$ vs. $b$), so independence demands $p\succ q$ — but a pessimist, who only ever looks at the worst prize, finds both lotteries indifferent (worst prize is $b$ either way). **Minimizing-options preferences also fail**: $[a]\sim[b]$ (both single-prize), yet $0.5\cdot a\oplus0.5\cdot b \prec 0.5\cdot b\oplus0.5\cdot b=[b]$ (two possible outcomes is worse than one) — violating what independence would require if $[a]\sim[b]$ held. **Good-and-bad preferences do satisfy independence**: since $G(\cdot)$ is linear in the underlying probabilities, $G(p)-G(q)$ for two compound lotteries differing only in slot $k$ has the same sign as $G([z_k])-G(\beta\cdot a\oplus(1-\beta)\cdot b)$ — the comparison reduces exactly to the comparison of the differing slot, by construction of linearity.

## Independence implies monotonicity

**Lemma.** If $\succeq$ satisfies independence and $[a]\succ[b]$, then for probabilities $\alpha,\beta$: $\alpha>\beta \iff \alpha\cdot a\oplus(1-\alpha)\cdot b \succ \beta\cdot a\oplus(1-\beta)\cdot b$ — lotteries over just two prizes, one strictly better than the other, are ranked *exactly* by the probability of getting the better prize, with no other consideration entering.

This closes the gap between the abstract independence property and the everyday intuition "more chance of the better outcome is better" — it isn't an extra assumption, it's a theorem that independence alone already delivers.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §3.2.1.*
