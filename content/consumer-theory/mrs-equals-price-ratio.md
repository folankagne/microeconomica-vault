---
title: "Optimality: MRS Equals the Price Ratio"
source: "Osborne & Rubinstein (2020), §5.4"
status: enriched
tags:
  - marginal-rate-of-substitution
  - tangency-condition
  - corner-solution
prerequisites:
  - consumer-theory/differentiable-preferences-and-mrs
  - consumer-theory/the-consumers-problem
---
## The tangency condition

**Proposition.** For a monotone, convex, differentiable preference relation, if $x^*$ solves the consumer's problem at $(p_1,p_2,w)$:

**(a)** $x_1^*>0$ and $x_2^*>0 \implies \text{MRS}(x^*)=p_1/p_2$.
**(b)** $x_1^*=0 \implies \text{MRS}(x^*)\leq p_1/p_2$.
**(c)** $x_2^*=0 \implies \text{MRS}(x^*)\geq p_1/p_2$.

*Proof idea for (a):* suppose $\text{MRS}(x^*)<p_1/p_2$ at an interior optimum. Moving along the budget line — giving up a little of good 1, gaining $p_1/p_2$ times as much of good 2 — is by hypothesis an improvement whenever the trade rate exceeds MRS, so [differentiability](differentiable-preferences-and-mrs.md) guarantees a nearby, still-affordable bundle that's strictly preferred, contradicting optimality. The corner cases (b)–(c) fail for a subtler reason: at $x_1^*=0$, the consumer *would* want to trade good 2 for more good 1 if she could, but can't reduce consumption of a good she isn't consuming — so only the one-sided inequality survives, not the equality.

This is the formal version of the geometric "tangency" picture: at an interior optimum, the indifference curve's slope ($-\text{MRS}$) must match the budget line's slope ($-p_1/p_2$) exactly, since [MRS is the rate the consumer is willing to trade at](differentiable-preferences-and-mrs.md) and $p_1/p_2$ is the rate the market lets her trade at — any mismatch leaves a profitable trade on the table.

```tikz
\begin{document}
\begin{tikzpicture}[scale=1]
\draw[->] (0,0) -- (5.5,0) node[right] {$x_1$};
\draw[->] (0,0) -- (0,5.5) node[above] {$x_2$};
\draw[thick] (0,4) -- (4,0);
\node[below] at (4,0) {$w/p_1$};
\node[left] at (0,4) {$w/p_2$};
\draw[thick] plot[smooth] coordinates {(0.8,5) (1,4) (1.6,2.5) (2,2) (2.5,1.6) (4,1) (5,0.8)};
\fill (2,2) circle (2pt);
\node[above right] at (2,2) {$x^*$};
\end{tikzpicture}
\end{document}
```
*Figure — At the interior optimum $x^*$, the indifference curve is tangent to the budget line: both have the same slope, $-p_1/p_2=-\text{MRS}(x^*)$. Anywhere else on the budget line, the two slopes differ and a profitable trade remains — which is exactly what the proof of part (a) exploits.*

## Two fully solved examples

**Cobb-Douglas-type**, $u=x_1x_2$. Corner bundles ($x_1=0$ or $x_2=0$) give $u=0$, strictly worse than any interior bundle, so the solution is interior and part (a) applies: $\text{MRS}(x^*)=x_2^*/x_1^*=p_1/p_2$, i.e. $p_1x_1^*=p_2x_2^*$. Combined with [the budget line](the-consumers-problem.md) ($p_1x_1^*+p_2x_2^*=w$, from monotonicity): $x^*=(w/(2p_1), w/(2p_2))$ — the consumer splits her budget evenly, a clean closed form recovered entirely from the tangency condition plus the budget constraint, no calculus of a Lagrangian required beyond computing MRS itself.

**Concave quasilinear**, $u=\sqrt{x_1}+x_2$. Here $\text{MRS}(x_1,x_2)=1/(2\sqrt{x_1})$ — note it does *not* depend on $x_2$ at all. Along the budget line, as $x_1$ rises from $0$ to $w/p_1$, MRS *falls* monotonically from its corner value $2\sqrt{w/p_2}$ (evaluated at the corner $x_1=0$, $x_2=w/p_2$) down toward $0$. Two regimes follow directly: if $2\sqrt{w/p_2}\geq p_1/p_2$ — the price ratio is reachable somewhere along this falling path — the interior tangency condition binds, giving $x_2^*=p_1^2/(4p_2^2)$, $x_1^*=w/p_1-p_1/(4p_2)$; if instead $2\sqrt{w/p_2}\leq p_1/p_2$, even the corner's MRS never reaches the market's asking price ratio, and the corner solution $x^*=(0,w/p_2)$ applies — the consumer never finds good 1 worth buying at all. This is the direct illustration of part (b) of the tangency proposition: corner solutions aren't edge-case pathologies, they're what happens whenever MRS at the corner already falls short of the price ratio.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §5.4.*
