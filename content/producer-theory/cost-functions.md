---
title: "Cost Functions"
source: "Osborne & Rubinstein (2020), §6.4 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - producer-theory
  - cost-function
  - average-and-marginal-cost
prerequisites:
  - producer-theory/output-vs-profit-maximization
---
## Cost as a primitive, not always derived

Given a production function $f$, the cost of producing $y$ units is $wf^{-1}(y)$ — but it's often more convenient to start directly from a **cost function** $C(y)$, especially when only the output market is of interest.

**Definition.** $C:\mathbb{R}_+\to\mathbb{R}_+$ is a cost function if it's increasing, $C(0)=0$, and average cost $C(y)/y$ eventually exceeds any bound (production can't stay cheap forever). If $C(y)=k+c(y)$ for $y>0$ with $k>0$ fixed and $c$ increasing with $c(0)=0$, $k$ is the **fixed cost** and $c(y)$ the **variable cost**. $\text{AC}(y)=C(y)/y$ is average cost; $\text{MC}(y)=C'(y)$ (where differentiable) is marginal cost.

When cost genuinely comes from a single-input production function, $C(y)=wf^{-1}(y)$ has **no fixed cost**, and — since $f$ is concave — $C$ is **convex**: the same diminishing-returns assumption that shaped $f$ shows up as *increasing* marginal cost on the cost side.

## How AC and MC relate

**Proposition.**
**(a)** If $C$ is convex, $\text{AC}$ is increasing.
**(b)** If $C$ is differentiable, $\lim_{y\to0}\text{AC}(y)=\text{MC}(0)$.
**(c)** If $C$ is differentiable, $\text{AC}$ is increasing wherever $\text{AC}(y)<\text{MC}(y)$, decreasing wherever $\text{MC}(y)<\text{AC}(y)$.

*Proof of (c):* differentiating, $\text{AC}'(y) = C'(y)/y - C(y)/y^2 = (\text{MC}(y)-\text{AC}(y))/y$, which has the sign of $\text{MC}(y)-\text{AC}(y)$ directly. $\blacksquare$

The intuition for (c) is the same one used to explain grade-point averages: $C(y)$ is the *sum* of marginal costs up to $y$, so $\text{AC}(y)$ is literally the *average* of $\text{MC}$ over $[0,y]$ — adding a marginal cost above the current average necessarily *pulls the average up*, exactly like an above-average test score raising a GPA. This is why **MC crosses AC exactly at AC's minimum** — the standard textbook picture — and it requires no calculus beyond this averaging intuition to see why it must be true.

```tikz
\begin{document}
\begin{tikzpicture}[scale=1]
\draw[->] (0,0) -- (5.5,0) node[right] {$y$};
\draw[->] (0,0) -- (0,4.5) node[above] {\$};
\draw[thick] plot[smooth] coordinates {(0.3,3.8) (1,2.1) (1.8,1.3) (2.5,1.15) (3.5,1.6) (4.5,2.6) (5.2,3.6)};
\node[above] at (5.2,3.6) {$MC(y)$};
\draw[thick] plot[smooth] coordinates {(0.3,3.8) (1,2.6) (1.8,1.9) (2.5,1.7) (3.5,1.85) (4.5,2.2) (5.2,2.7)};
\node[right] at (5.2,2.7) {$AC(y)$};
\fill (2.5,1.7) circle (1.5pt);
\draw[dashed] (2.5,0) -- (2.5,1.7);
\end{tikzpicture}
\end{document}
```
*Figure — $MC$ crosses $AC$ exactly at $AC$'s minimum: while $MC<AC$, each extra unit pulls the average down; once $MC>AC$, each extra unit pulls it back up. This holds for any cost function, fixed cost or not — the U-shape itself comes from decreasing-then-increasing marginal cost, not from the fixed cost directly.*

## Optimal output for each objective, restated in AC/MC terms

**Output-maximizer** (Proposition 6.6): facing output price $p$, choose the *largest* $y^*$ with $\text{AC}(y^*)=p$ — the break-even output, exactly analogous to [the break-even input level for output-maximization on the input side](output-vs-profit-maximization.md), just restated on the cost-function side.

**Profit-maximizer** (Proposition 6.7), with $C$ convex and differentiable: choose $y^*$ with $\text{MC}(y^*)=p$, **provided** $p\geq \text{AC}(y^*)$ (otherwise produce nothing) — "price equals marginal cost, subject to covering average cost" is the textbook rule stated formally, with the *sufficiency* condition ($p\geq\text{AC}$) made explicit rather than left implicit.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §6.4.*
