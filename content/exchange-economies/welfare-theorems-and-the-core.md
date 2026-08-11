---
title: "Welfare Theorems and the Core"
source: "Osborne & Rubinstein (2020), §§10.5–10.6 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - welfare-theorems
  - core
  - pareto-stability
prerequisites:
  - exchange-economies/existence-and-reopening-trade
---
## Pareto stability, again

**Proposition.** Every competitive equilibrium allocation is Pareto stable.

*Proof:* if $y$ Pareto-dominated equilibrium allocation $a$, optimality at $a$ forces $p\cdot y(i)\geq p\cdot e(i)$ for everyone weakly better off, and $p\cdot y(j) > p\cdot e(j)$ *strictly* for whoever is strictly better off under $y$. Summing over all individuals gives $p\cdot\sum_i y(i) > p\cdot \sum_i e(i)$ — but $y$ being a feasible allocation requires these sums to be *equal*. Contradiction. $\blacksquare$

This is the *exact same proof structure* as [the housing-market version](../equilibrium-foundations/welfare-theorems-for-the-housing-market.md) — sum values across all agents, use feasibility to force equality, derive a contradiction from someone's strict improvement — carried over verbatim from indivisible to divisible goods. And true to form, the textbook again **declines to call this the "first fundamental theorem of welfare economics,"** for the identical reason given [in the housing-market chapter](../equilibrium-foundations/welfare-theorems-for-the-housing-market.md): the model has no cardinal welfare in it, only ordinal Pareto comparisons, so the conventional name claims more than what's proven. The parallel "second welfare theorem" claim — redistribute endowments to any Pareto-stable target, then let trade reopen, and nothing moves — follows from combining this result with [reopening-trade](existence-and-reopening-trade.md), and is declined on the same grounds.

**A genuine caveat, unique to divisible goods.** The equivalence between "Pareto stable" and "nothing strictly-Pareto-*improving* exists" (a weaker-looking but sometimes easier condition to check) requires *either* convex preferences with every bundle strictly positive, *or* strongly monotone preferences — neither is automatic, and the textbook flags this rather than letting the reader assume the two notions always coincide.

## A sharper stability concept: the core

Pareto stability only rules out changes *everyone* would agree to. The **core** rules out something stronger: any *subgroup* unilaterally walking away with just their own endowments and reallocating among themselves.

**Definition — core.** Allocation $a$ is in the core if no nonempty subset $S\subseteq N$ can find bundles $(b(i))_{i\in S}$, using only $S$'s own endowments ($\sum_{i\in S}b(i)=\sum_{i\in S}e(i)$), that make *every* member of $S$ strictly better off.

**The core is a genuinely finer test than Pareto stability.** A worked example (two "perfect complements" agents endowed with good 1, two "perfect substitutes" agents endowed with good 2) exhibits an allocation that is Pareto stable — and preferred by every individual to her own endowment — yet **not** in the core: a specific 3-person coalition (two complements-agents, one substitutes-agent) can secede and do strictly better among themselves, even though no *unanimous* improvement over the full allocation exists. Being immune to *everyone* agreeing to change is a weaker requirement than being immune to *any* subgroup defecting.

**Proposition.** Every competitive equilibrium allocation is in the core.

*Proof:* essentially the same value-summing argument as Pareto stability, restricted to the coalition $S$: if $S$ could improve upon $a$, optimality within $S$'s own budget sets forces $p\cdot\sum_{i\in S}b(i) > p\cdot\sum_{i\in S}e(i)$, directly contradicting $S$'s own feasibility constraint $\sum_{i\in S}b(i)=\sum_{i\in S}e(i)$. $\blacksquare$

Since core membership is strictly harder to achieve than Pareto stability, this is a **strictly stronger** equilibrium property than [the first welfare-theorem analogue](#pareto-stability-again) — competitive equilibrium isn't just immune to unanimous defection, it's immune to *any* coalition defecting, a much more demanding and economically meaningful robustness property.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§10.5–10.6.*
