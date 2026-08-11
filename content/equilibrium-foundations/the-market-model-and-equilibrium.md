---
title: "The Market Model and Equilibrium"
source: "Osborne & Rubinstein (2020), §9.1 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - market-equilibrium
  - house-allocation
prerequisites:
  - equilibrium-foundations/the-jungle-model-and-equilibrium
---
## Same society, opposite allocation mechanism

A **market** $\langle N,H,(\succeq_i)_{i\in N},e\rangle$ replaces [the jungle's power relation](the-jungle-model-and-equilibrium.md) with an **initial allocation** $e$ (who owns what house to start) and the assumption that ownership is *fully protected*: houses trade only by mutual consent, never by force. This is the polar-opposite primitive — the jungle had no property rights at all; the market has nothing *but* property rights, mediated by trade.

**Definition — equilibrium of a market.** A pair $(p,a)$, price system and allocation, is an equilibrium if: **(i)** every individual's assigned house $a(i)$ is her favorite among all houses priced at or below her own initial house's price, $\{h: p(h)\leq p(e(i))\}$; **(ii)** $a$ is a genuine allocation (feasible — each house goes to exactly one person). This is structurally the *same shape* of definition as [the consumer's problem](../consumer-theory/the-consumers-problem.md) — optimize subject to a budget constraint — except the "budget" here is inherited entirely from what you already own, priced by the equilibrium price system itself, and feasibility (market clearing) is imposed as a second, separate condition rather than following automatically.

## Two clarifying examples

**Common preferences.** If every individual shares the same ranking $\succeq$ over houses, then $(p,e)$ — the price system that mirrors $\succeq$ (higher-ranked houses cost more), paired with the *initial* allocation itself — is an equilibrium. Nobody trades: each individual's budget set is exactly "my house or something worse," so staying put is already optimal. This is a useful degenerate check: when there's no genuine scope for mutually beneficial trade, equilibrium correctly predicts none happens.

**All-different favorites.** If every individual has a *distinct* favorite house, the equilibrium sets a single uniform price for every house, and everyone simply gets her favorite — since all budget sets are then the same (the whole house set $H$), and no two people's optimal choices collide.

**A non-equilibrium example.** Not every Pareto-improving trade outcome is supportable by *some* price system. For a specific 4-person, 4-house market, one particular reallocation (reachable via a sequence of pairwise swaps) turns out to admit **no** rationalizing price system at all — while a *different* reallocation from the same starting point does. This is the market-equilibrium analogue of [rationalizable demand functions](../consumer-theory/rationalizing-demand-and-warp.md): not every outcome that *could* arise from voluntary trade is one that a coherent price system can simultaneously support.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §9.1.*
