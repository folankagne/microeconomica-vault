---
title: "Asymmetric Information and Signaling"
source: "Osborne & Rubinstein (2020), §14 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - signaling
  - spence-model
  - separating-equilibrium
prerequisites:
  - exchange-economies/prices-expectations-and-adverse-selection
---
## A different kind of equilibrium: contracts, not prices

Here the equilibrium object isn't a price system but a **set of contracts** — and the concept doesn't fix *who* offers what, only which contracts can survive: **(I)** every offered contract is chosen by someone, **(II)** no offered contract loses money for whoever posts it, **(III)** no *unoffered* contract could be added that would attract a worker *and* turn a profit. Condition III is the free-entry discipline doing all the work — any profitable gap gets filled by a new entrant, so equilibrium requires there be no such gap left.

## Warm-up: a labor market with no asymmetry at all

Identical workers, productivity $v$; employers post wages. **Proposition.** The unique equilibrium is the single wage offer $\{v\}$ — competition among employers drives wages up to exactly match productivity (any higher and the employer loses money; any lower and a rival can profitably poach with a marginally higher offer). This is just [zero-profit competitive pricing](../monopoly/00-overview.md) restated in contract language, included purely to set up the contrast with what follows.

## The real model: productivity employers can't observe, but education they can

Two worker types, $L$ (productivity $v_L$) and $H$ (productivity $v_H > v_L$), population shares $\alpha_L,\alpha_H$. Crucially, **education doesn't raise productivity at all** in this model — its only role is that it's *cheaper for high-productivity workers to acquire* ($\beta_H<\beta_L$ per unit). A contract is now a pair $(t,w)$: required education level and wage. A type-$X$ worker's income from $(t,w)$ is $w-\beta_X t$, and preferences are lexicographic — maximize income first, break ties by preferring less education.

```tikz
\begin{document}
\begin{tikzpicture}[scale=1]
\draw[->] (0,0) -- (5.5,0) node[right] {$t$ (education)};
\draw[->] (0,0) -- (0,4.5) node[above] {$w$};
\draw[thick] (0,0.6) -- (5,3.6);
\node[right] at (5,3.6) {\scriptsize slope $\beta_L$};
\draw[thick] (0,1.6) -- (5,2.6);
\node[right] at (5,2.6) {\scriptsize slope $\beta_H$};
\fill (0,1.6) circle (2pt);
\node[left] at (0,1.6) {\scriptsize $c_L^*=(0,v_L)$};
\fill (3.4,3.4) circle (2pt);
\node[above] at (3.4,3.4) {\scriptsize $c_H^*=(t_H,v_H)$};
\end{tikzpicture}
\end{document}
```
*Figure — Iso-income lines: along a line of slope $\beta_X$, a type-$X$ worker is indifferent. The equilibrium contract pair sits where $c_L^*$ pays $L$-workers their full productivity with zero education, and $c_H^*$ pays $H$-workers their full productivity but requires just enough education ($t_H$, where $v_H-\beta_Lt_H=v_L$) that an $L$-worker is exactly indifferent between mimicking $c_H^*$ and taking $c_L^*$ honestly.*

**Proposition (characterization).** If an equilibrium exists, it is **separating** — exactly two contracts, $c_L^*=(0,v_L)$ and $c_H^*=(t_H,v_H)$ with $t_H$ solving $v_H-\beta_Lt_H=v_L$ — and **no pooling equilibrium ever exists**.

*Why pooling always unravels:* suppose a single contract $(t^*,w^*)$ served both types. If $w^*$ exceeds the population's average productivity, it loses money — violated immediately. If not, some entrant can offer a slightly-more-education, slightly-higher-wage contract that only an $H$-type finds worthwhile (an $L$-type, facing the steeper cost $\beta_L$, isn't willing to pay for the extra education to get the extra wage) — and since that contract only attracts $H$-types, it's profitable at a wage below $v_H$. The pooling contract is never safe from this kind of profitable "cream-skimming" entry.

*Why $t_H$ is pinned down exactly:* any *more* education than $t_H$ wastefully costs the $H$-type worker more than needed to already deter $L$-types from mimicking her; any *less* and an $L$-type worker would find it worthwhile to acquire the (cheaper-for-her-than-you'd-think, but still costly) education just to pocket $v_H$. $t_H$ is the minimum "wasteful" signal that still successfully separates the types — education here has **zero productive value**, its entire economic function is to be *differentially costly* enough to sort workers truthfully.

## Existence depends on the population mix

Whether $\{c_L^*,c_H^*\}$ actually *is* an equilibrium — rather than itself being undercut by some pooling contract that both types would prefer — depends on whether $L$-types are numerous enough. If the population's *average* productivity $v=\alpha_Lv_L+\alpha_Hv_H$ is low enough (many low-productivity workers), separating survives; if $H$-types dominate, a pooling contract paying close to $v$ can outcompete the costly separating equilibrium for both types simultaneously, and no equilibrium of *either* kind may exist. This closing observation is doing real interpretive work: whether **wasteful signaling emerges at all** is not a fixed feature of "asymmetric information exists" — it's a knife-edge property of the specific population composition, one of the clearest illustrations in the book that a plausible-sounding economic mechanism (education as a costly signal) is not automatically robust or universal.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §14. Model due to Spence (1973).*
