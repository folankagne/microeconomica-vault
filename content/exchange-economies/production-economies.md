---
title: "Production Economies"
source: "Osborne & Rubinstein (2020), §12 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - production-economy
  - general-equilibrium
prerequisites:
  - exchange-economies/welfare-theorems-and-the-core
  - producer-theory/output-vs-profit-maximization
---
The textbook itself keeps this chapter brief — extending [the exchange economy](welfare-theorems-and-the-core.md) to include production, but proving only *one* result per model (Pareto stability of equilibrium), rather than the full existence/core/uniqueness treatment given to pure exchange. This entry matches that scope.

## Model 1: consumers and producers together

A **production economy** adds a set $J$ of producers to [the consumer set](../consumer-theory/the-consumers-problem.md), each with a **technology** $T(j)\subseteq\mathbb{R}^2_+$ — a closed, bounded, convex, free-disposal set of producible bundles (no cost structure needed; a producer simply *has* the ability to make certain combinations of goods). Producers maximize profit $p\cdot y$ over $T(j)$; their profits are distributed to consumers via fixed ownership shares $\alpha(i,j)$, which then fund each consumer's budget. A **competitive equilibrium** requires: every consumer optimal in her (profit-funded) budget set, every producer profit-maximizing on her technology, and the whole configuration feasible (total consumption = total production).

**Proposition.** Every competitive equilibrium's consumption-production plan is Pareto stable.

*Proof idea:* exactly [the value-summing argument from pure exchange](welfare-theorems-and-the-core.md) — sum $p\cdot x(i)$ over consumers, use producer profit-maximization to bound total production value, use consumer optimality to get a strict inequality wherever someone's strictly better off, and let feasibility (production = consumption in value) supply the contradiction. Notably, **this argument uses neither convexity of preferences nor convexity of technology** — Pareto stability of equilibrium is a remarkably robust conclusion, needing only optimization and market-clearing.

**But existence is a different story.** A worked counterexample — one consumer with perfect-complements preferences, one producer with a *non-convex* technology — has **no** competitive equilibrium at all: for every price system, the producer's profit-maximizing output sits at one of two extreme corners of her technology set, neither of which ever coincides with what the consumer wants to buy at those same prices. Pareto stability of equilibrium survives without convexity; *existence* of equilibrium generally does not.

## Model 2: capital and labor — the simplest possible production economy

A single **worker**, endowed with one unit of time to split between leisure $l$ and labor $1-l$, and a single **capitalist**, who owns an increasing, concave production function $f$ converting labor into a consumption good. Given wage $w$, the capitalist chooses labor demand $a$ to maximize $f(a)-wa$ — [ordinary profit-maximization](../producer-theory/output-vs-profit-maximization.md), with labor as the input — while the worker chooses $l$ to optimize $(l, w(1-l))$ under her own preferences over leisure-and-consumption bundles. Pareto stability here compares outcomes on *both* what the worker gets *and* how much surplus $z$ the capitalist retains — a natural two-sided notion of efficiency for a two-agent economy where one side supplies labor and the other supplies capital and technology.

This stripped-down model — one worker, one capitalist, one input, one output — is deliberately the simplest possible setting where "wages," "labor supply," and "capital's return" all appear as genuine equilibrium objects rather than assumed primitives, connecting [producer theory](../producer-theory/00-overview.md) and [consumer theory](../consumer-theory/00-overview.md) into a single closed system.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §12.*
