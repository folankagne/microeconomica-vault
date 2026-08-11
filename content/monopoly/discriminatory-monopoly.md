---
title: "Discriminatory and Implicit Price Discrimination"
source: "Osborne & Rubinstein (2020), §§7.3–7.4 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - monopoly
  - price-discrimination
prerequisites:
  - monopoly/profit-maximizing-monopoly-and-deadweight-loss
---
## Explicit discrimination: different prices for different observable segments

**Definition.** A discriminatory monopolistic market lets the monopolist set a *different* price in each segment, rather than [one uniform price](monopolistic-markets-and-marginal-revenue.md). The model implicitly assumes consumers don't resent or react to the price differences themselves — only to the price they personally face.

The monopolist's problem, $\max_{y_1,\dots,y_k} \sum_i P_i(y_i)y_i - C\big(\sum_i y_i\big)$, does **not** decompose into $k$ separate problems, because total cost depends on aggregate output across all segments jointly.

**Proposition.** If optimal output $y_i^*$ in segment $i$ is positive, then $\text{MR}_i(y_i^*) = \text{MC}\big(\sum_j y_j^*\big)$ for every such segment.

The intuition has two parts: **(i)** marginal revenues must be *equal across all active segments* — if segment $A$'s marginal revenue exceeded segment $B$'s, shifting a unit of output from $B$ to $A$ would raise profit, so no such imbalance survives at an optimum; **(ii)** that common marginal revenue must equal overall marginal cost — otherwise total output itself should rise or fall. This is a direct generalization of [the uniform-price MR = MC condition](profit-maximizing-monopoly-and-deadweight-loss.md): uniform pricing is exactly the special case where the monopolist is *forced* to pick one segment-blind price rather than optimizing each segment's marginal revenue separately.

## Implicit discrimination: screening via a menu

A subtler case: the monopolist knows demand *differs* across consumers but can't observe *which* consumer is which — so she can't charge person-specific prices directly. Instead, she offers a **menu** of quantity-price pairs $(q,m)$, and lets each consumer self-select the option maximizing her own surplus $V_i(q)-m$ (or opt out entirely).

**The key result (stated without the full proof here):** for two consumers whose valuations differ systematically — one values *every* additional unit more than the other — the monopolist's optimal menu can involve **two distinct options**, and the *higher*-value consumer's option is deliberately priced to leave her indifferent between it and switching to the *lower*-value consumer's option. This isn't a rounding error — it's the binding **incentive-compatibility constraint**: the monopolist would love to charge the high-value consumer her full willingness to pay, but doing so would make the high-value consumer prefer to mimic the low-value consumer's cheaper, smaller bundle instead, so the high-value option's price is capped by exactly the gap needed to prevent that.

This is **second-degree price discrimination** in its purest form — quantity-based menus (economy vs. business class, small vs. jumbo package sizes) functioning as an indirect, self-enforcing substitute for the direct segment-based discrimination of the previous section, precisely because the monopolist cannot observe type but *can* observe which option each consumer picks.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§7.3–7.4.*
