---
title: "The Edgeworth Box"
source: "Osborne & Rubinstein (2020), §10.9 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - edgeworth-box
  - core
prerequisites:
  - exchange-economies/welfare-theorems-and-the-core
---
## Constructing the box

Take [the two separate consumer diagrams](../consumer-theory/consumer-bundles-and-examples.md) for individuals 1 and 2, **rotate individual 2's diagram 180°**, then slide the two together so their endowment points coincide. The result is a single rectangle: every point inside it represents a *complete allocation* of the fixed total bundle — individual 1's consumption read from the bottom-left corner $O_1$, individual 2's consumption read (using her rotated axes) from the top-right corner $O_2$. This single trick is what makes two agents' entire consumption problems, and every feasible way of dividing the total endowment between them, visible on one diagram.

```tikz
\begin{document}
\begin{tikzpicture}[scale=1]
\draw[thick] (0,0) rectangle (6,4);
\node[below left] at (0,0) {\scriptsize $O_1$};
\node[above right] at (6,4) {\scriptsize $O_2$};
\fill (2.3,2.6) circle (1.8pt);
\node[left] at (2.2,2.6) {\scriptsize $e$};
\fill (3.4,1.9) circle (1.8pt);
\node[below] at (3.4,1.8) {\scriptsize $a$};
\draw[thick] (1.3,3.4) -- (4.6,0.6);
\draw[thick] plot[smooth] coordinates {(1.6,3.7) (2.4,2.6) (3.4,1.9) (4.6,1.4) (5.7,1.1)};
\draw[thick] plot[smooth] coordinates {(0.5,0.9) (1.6,1.3) (2.6,1.7) (3.4,1.9) (4.4,2.7) (5.3,3.6)};
\end{tikzpicture}
\end{document}
```
*Figure — The Edgeworth box. Endowment $e$ and the equilibrium allocation $a$ both sit on the budget line (straight, since both face the same price ratio). At $a$, individual 1's indifference curve (bulging toward $O_1$) and individual 2's (bulging toward $O_2$) are tangent to each other and to the budget line — the two-agent picture of [MRS equals the price ratio](../consumer-theory/mrs-equals-price-ratio.md), holding for both agents simultaneously.*

## Reading off Pareto stability and the core directly

The full **set of Pareto stable allocations** is exactly the locus of points where individual 1's and individual 2's indifference curves are tangent to each other — the "contract curve" running between the two corners $O_1$ and $O_2$: off this curve, the two indifference curves *cross* rather than touch, meaning some nearby point lies inside both agents' preferred regions simultaneously — a Pareto improvement always available. On the curve, no local direction of movement can help one agent without hurting the other, by construction of tangency.

The **core**, for this two-person case, is the *sub-segment* of that same contract curve lying between the two indifference curves that pass **through the endowment point $e$ itself** — exactly the portion each individual likes at least as well as her own endowment. Points on the contract curve *outside* that segment are still Pareto stable, but aren't in the core, since at least one individual would rather keep her own endowment than accept that particular Pareto-stable trade — precisely [the gap illustrated by the "Pareto stable but not in the core" example](welfare-theorems-and-the-core.md), now made visually obvious rather than needing an algebraic construction.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §10.9.*
