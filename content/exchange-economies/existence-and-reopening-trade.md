---
title: "Existence and Reopening Trade"
source: "Osborne & Rubinstein (2020), §§10.3–10.4 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - existence
  - excess-demand
prerequisites:
  - exchange-economies/the-exchange-economy-model
---
## Existence via excess demand and the intermediate value theorem

Define **excess demand** for good 1: $z(p_1) = \sum_i [d_i(p_1) - e_1(i)]$, total desired consumption minus total endowment, as a function of good 1's price (normalizing good 2's price to 1).

**Proposition.** If every individual's demand function $d_i$ is continuous, some low price makes *everyone* want more of good 1 than they own ($z$ positive), and some high price makes everyone want to sell ($z$ negative), then a competitive equilibrium exists.

*Proof:* $z$ is continuous (sum of continuous functions), positive somewhere, negative somewhere — the Intermediate Value Theorem gives some $p_1^*$ with $z(p_1^*)=0$. Market-clearing for good 1 at $p_1^*$, plus [the shortcut proposition](the-exchange-economy-model.md), automatically gives market-clearing for good 2 too — so $((p_1^*,1), (x_i(p_1^*,1))_i)$ is a competitive equilibrium. $\blacksquare$

This is deliberately a **weaker, more elementary existence result** than the general theory would give — no fixed-point theorem, just IVT applied to a single scalar excess-demand function — traded off against genuinely restrictive assumptions (continuity of demand, and the two boundary conditions). The chapter is explicit that a fully general existence theorem needs mathematics beyond the book's scope; this is a taste of the *idea*, not the state of the art. Note also what can go wrong: **non-convex preferences can break existence entirely** (no equilibrium price may clear the market), and [the perfect-complements example](the-exchange-economy-model.md) already showed that *multiple* equilibria, differing in both prices and allocation, are entirely possible even when one exists.

## Equilibrium is self-perpetuating

**Proposition.** If $(p,a)$ is a competitive equilibrium of an economy with initial endowment $e$, then $(p,a)$ is *also* a competitive equilibrium of the economy with initial endowment reset to $a$ — reopen the market after trade, and nothing further happens.

*Proof:* $a$ is trivially feasible as its own allocation; and since $p\cdot a(i)=p\cdot e(i)$, the budget sets $B(p,e(i))$ and $B(p,a(i))$ are *identical* sets — so whatever was optimal in the first is optimal in the second. $\blacksquare$

This is the exchange-economy analogue of [the housing market's "no trade from a Pareto-stable endowment" result](../equilibrium-foundations/welfare-theorems-for-the-housing-market.md), specialized to the case where the new endowment is itself already an equilibrium outcome — a clean formal statement of the everyday intuition that a market, once it clears, has no further pressure to move.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§10.3–10.4.*
