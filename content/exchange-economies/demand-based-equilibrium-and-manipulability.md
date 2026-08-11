---
title: "Demand-Based Equilibrium and Manipulability"
source: "Osborne & Rubinstein (2020), §§10.7–10.8 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - demand-functions
  - manipulability
prerequisites:
  - exchange-economies/welfare-theorems-and-the-core
---
## Equilibrium without assuming preference-maximization

Everything so far assumed each individual optimizes a genuine preference relation. The same equilibrium *concept* — a price system plus an allocation where everyone gets exactly what their demand function specifies, and markets clear — works equally well if individuals are instead characterized directly by **demand functions**, including ones [not rationalizable by any preference relation at all](../consumer-theory/rationalizing-demand-and-warp.md). A worked example (one individual who demands only the *more expensive* good, per [the non-rationalizable demand function from consumer theory](../consumer-theory/rationalizing-demand-and-warp.md)) confirms the machinery goes through unchanged — competitive equilibrium is really a statement about *mutual consistency of behavior*, not a statement that presupposes rational optimization underneath.

## Can you profit from lying about your preferences?

**In the housing market, no** — [misrepresenting preferences never helps](../equilibrium-foundations/welfare-theorems-for-the-housing-market.md), a fact left as an exercise there. **In an exchange economy, the answer flips to yes.** A two-person economy (perfect-substitutes agent 1, perfect-complements agent 2, endowments $(1,0)$ and $(0,1)$) has a unique honest equilibrium at $p=(1,1)$, splitting evenly, $(\tfrac12,\tfrac12)$ each. If individual 1 instead **acts as though** her utility were $3x_1+x_2$ (pretending to value good 1 more than she truly does), the equilibrium price shifts to $(3,1)$ and her allocation improves to $(\tfrac34,\tfrac34)$ — a bundle she genuinely prefers under her *true* preferences.

This is a striking asymmetry between the two market models developed in this vault, and worth sitting with: the housing market's strategy-proofness (via top trading cycles) is a special, structurally fragile property of that particular combinatorial setting — it is **not** a general feature of competitive markets. Once goods become divisible and prices become continuous rather than discrete, a large enough trader can move the equilibrium price system in her own favor by misrepresenting demand, exactly the same *kind* of concern (though a different mechanism) as [a monopolist facing a price-setting incentive](../monopoly/00-overview.md) rather than a pure price-taking one.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§10.7–10.8.*
