---
title: "Consumption Bundles and Examples of Preferences"
source: "Osborne & Rubinstein (2020), §§4.1–4.2; Lecture 2"
status: enriched
tags:
  - consumer-theory
  - bundles
  - indifference-curves
prerequisites:
  - preferences-and-choice/utility-representation-theorem
---
## Bundles as the set of alternatives

For a consumer, the set of alternatives is $X = \mathbb{R}^2_+$ — pairs of nonnegative quantities of two goods. A **bundle** $(x_1,x_2)$ need not literally be tables and potatoes; it can be attention devoted to two projects, or one's own welfare versus a partner's. Treating quantities as continuous (rather than integer) is a modeling convenience, not a claim that $\pi$ tables is a meaningful purchase — it buys tractable tradeoff analysis at the cost of that literalism.

Vector operations on bundles carry direct economic content: $x+y$ combines two bundles into one; $\lambda x$ scales a bundle by a positive factor $\lambda$ (e.g. $x/m$ divides a bundle into $m$ equal parts); and for $\lambda\in(0,1)$, $\lambda x + (1-\lambda)y$ is the bundle on the line segment between $x$ and $y$ — the operation that convexity, below, is defined in terms of.

## Indifference curves

For a preference relation $\succeq$ and bundle $a$, the **indifference set** (indifference curve) of $a$ is $\{y\in X: y\sim a\}$ — equivalently, if $\succeq$ is represented by $u$, the contour $\{y: u(y)=u(a)\}$. The full collection of indifference sets is exactly the partition induced by the equivalence relation $\sim$.

## Six worked examples

| Example | Utility function | Shape |
|---|---|---|
| Constant tradeoff | $v_1x_1+v_2x_2$ | Parallel lines, slope $-v_1/v_2$ |
| Only good 2 valued | $x_2$ | Horizontal lines |
| Threshold then good 2 | $x_1$ if $x_1\leq10$, else $11+x_2$ | Kinked at $x_1=10$ |
| Complementary goods | $\min\{x_1,x_2\}$ | L-shaped ("right shoe, left shoe") |
| Ideal bundle | $-(\lvert x_1-x_1^*\rvert+\lvert x_2-x_2^*\rvert)$ | Diamond-shaped, centered at $x^*$ |
| Lexicographic | *(none — [not representable](../preferences-and-choice/utility-representation-theorem.md))* | Every indifference set is a single point |

The lexicographic case is the direct specialization, to bundles, of [the non-representability result proved earlier](../preferences-and-choice/utility-representation-theorem.md) for the unit square: since $x\succ y$ or $y\succ x$ for *every* pair of distinct bundles, indifference sets collapse to single points, and Cantor's diagonal argument again rules out any utility representation.

These six examples are the recurring cast for the rest of the chapter: each gets checked against monotonicity, continuity, and convexity in turn, and several reappear as [worked solutions of the consumer's problem](the-consumers-problem.md).

```tikz
\begin{document}
\begin{tikzpicture}[scale=1]
\draw[->] (0,0) -- (5.5,0) node[right] {$x_1$};
\draw[->] (0,0) -- (0,5.5) node[above] {$x_2$};
\draw[thick] plot[smooth] coordinates {(0.5,5) (0.7,3.6) (1,2.5) (1.6,1.6) (2.5,1) (3.6,0.7) (5,0.5)};
\draw[thick] plot[smooth] coordinates {(0.8,5) (1.1,3.6) (1.6,2.5) (2.5,1.6) (3.6,1) (5,0.7)};
\draw[thick] plot[smooth] coordinates {(1.2,5) (1.6,3.6) (2.3,2.5) (3.5,1.6) (5,1.1)};
\node[right] at (5,0.5) {$u=1$};
\node[right] at (5,0.7) {$u=2$};
\node[right] at (5,1.1) {$u=3$};
\end{tikzpicture}
\end{document}
```
*Figure — A family of indifference curves for a monotone, strictly convex preference relation (e.g. $u=x_1x_2$): curves further from the origin mean higher utility, and each is bowed toward the origin — the geometric signature of convexity developed in the next entry.*

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§4.1–4.2; Lecture Slides 2, ITM (PSE/Paris 1).*
