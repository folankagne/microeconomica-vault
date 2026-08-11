---
title: "Welfare Theorems for the Housing Market"
source: "Osborne & Rubinstein (2020), §§9.3–9.4 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - welfare-theorems
  - pareto-stability
  - uniqueness
prerequisites:
  - equilibrium-foundations/top-trading-cycles-and-existence
---
## "First welfare theorem": every equilibrium is Pareto stable

**Proposition.** Every market equilibrium allocation is Pareto stable.

*Proof:* suppose $(p,a)$ is an equilibrium but $b$ Pareto-dominates $a$. For every $i$ strictly better off under $b$, optimality of $a(i)$ in $i$'s budget set forces $p(b(i))>p(a(i))$ (otherwise $i$ could already have afforded $b(i)$ and would have chosen it). Everyone else has $b(i)=a(i)$ exactly, since preferences are strict. Summing prices over all individuals: $\sum_i p(b(i)) > \sum_i p(a(i))$ — but both sides equal $\sum_i p(e(i))$, the total value of *all* houses, since $a$ and $b$ are both complete allocations of the same house set. Contradiction. $\blacksquare$

## "Second welfare theorem": Pareto-stable endowments generate no trade

**Proposition.** If the initial allocation $e$ is itself Pareto stable, every equilibrium allocation equals $e$ — no trade occurs.

*Proof:* $e(i)$ is always affordable in $i$'s own budget set, so equilibrium optimality gives $a(i)\succeq_i e(i)$ for everyone; if $a\neq e$ for even one person, that's a strict improvement for someone with nobody worse off — exactly a Pareto improvement over $e$, contradicting $e$'s Pareto stability. $\blacksquare$

This mirrors [the jungle's social-planner result](pareto-stability-in-the-jungle.md) exactly, with ownership standing in for power: an authority who can assign initial property rights (but not directly dictate outcomes, nor prevent voluntary trade) can induce *any* Pareto stable allocation, simply by making it the starting endowment — the same "achieve any Pareto-stable outcome by controlling the right primitive" structure recurs, once with power as the lever, once with ownership.

## A pointed methodological refusal

The textbook explicitly declines to call these results the "first and second fundamental theorems of welfare economics" — the conventional names — because the model has **no notion of welfare** in it at all, only ordinal preferences. A Pareto stable allocation can leave nearly everyone thrilled and one person merely non-worse-off; "no one can be made better off without someone being made worse off" is a genuine, useful stability property, but the authors argue it should not be dressed up in language ("welfare") that implies something stronger or more normatively loaded than what's actually been proven. This is the same brand of methodological candor as [the discussion of why profit maximization is assumed in producer theory](../producer-theory/why-profit-maximization.md) — a repeated willingness to flag exactly where a standard piece of terminology outruns what the underlying mathematics actually establishes.

## Uniqueness

**Proposition.** Every market has a **unique equilibrium allocation** (though *not* necessarily a unique equilibrium *price system* — different price rankings can support the same allocation).

*Proof idea (induction on the number of individuals):* take the trading cycle containing whoever holds the highest-priced house under one candidate equilibrium; every member of that cycle must be getting her overall favorite house (since, by [the same-price-within-a-cycle result](top-trading-cycles-and-existence.md), everyone in the cycle can afford everything). The same must be true of that cycle's members under *any other* equilibrium too — so the two equilibria agree on that cycle, which can then be peeled off, leaving a smaller market to which the same argument applies inductively. This depends essentially on the no-indifference assumption; with ties in preferences, both Pareto stability of equilibria and uniqueness of the equilibrium allocation can fail.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§9.3–9.4. Model due to Shapley & Scarf (1974).*
