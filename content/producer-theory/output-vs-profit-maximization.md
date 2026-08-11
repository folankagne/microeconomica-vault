---
title: "Output Maximization versus Profit Maximization"
source: "Osborne & Rubinstein (2020), §§6.2–6.3 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - producer-theory
  - profit-maximization
prerequisites:
  - producer-theory/the-producer-and-production-functions
---
## Output maximization: produce as much as possible without a loss

**Definition.** Given prices $p,w$, an output-maximizing producer solves $\max_a f(a)$ subject to $pf(a)-wa\geq0$.

**Proposition.** If $f$ is *strictly* concave, the solution is: input $0$ if $pf(a)-wa<0$ for every $a>0$ (production is never worthwhile); otherwise the unique positive $a^*$ solving $pf(a^*)-wa^* = 0$ — the *largest* break-even input level, since strict concavity of $f$ makes $pf(a)-wa$ single-peaked, crossing zero at most twice, and output-maximization pushes to the *further* of the two zero-profit crossings.

```tikz
\begin{document}
\begin{tikzpicture}[scale=1]
\draw[->] (0,0) -- (5.5,0) node[right] {$a$};
\draw[->] (0,0) -- (0,4.5) node[above] {\$};
\draw[thick] plot[smooth] coordinates {(0,0) (0.7,1.3) (1.6,2.4) (2.8,3.15) (4,3.5) (5,3.65)};
\node[above] at (5,3.65) {$pf(a)$};
\draw[thick] (0,0) -- (5,3.1);
\node[right] at (5,3.1) {$wa$};
\fill (3.7,3.42) circle (1.5pt);
\node[below] at (3.7,0) {$a^*$};
\draw[dashed] (3.7,0) -- (3.7,3.42);
\end{tikzpicture}
\end{document}
```
*Figure — An output-maximizing producer expands input up to $a^*$, the point where the revenue curve $pf(a)$ meets the cost line $wa$ again from above — the furthest break-even point, since going further would mean operating at a loss.*

**Comparative statics.** A lower input price, a higher output price, or any technological improvement ($g(a)\geq f(a)$ for all $a$) shifts $a^*$ up or leaves it unchanged — never down. This follows directly from the picture: any of these three changes either rotates the cost line down or shifts the revenue curve up, and the break-even crossing point can only move outward.

## Profit maximization: the standard textbook default

**Definition.** A profit-maximizing producer solves $\max_a\, pf(a)-wa$ outright.

**Proposition.** If $f$ is differentiable and strictly concave: input $0$ if $pf(a)-wa<0$ everywhere; otherwise the unique $a^*$ solving the first-order condition $pf'(a^*)=w$ — marginal revenue product of input equals its price.

*Proof:* $pf(a)-wa$ is strictly concave in $a$ (since $f$ is), so the standard first-order condition characterizes its unique interior maximizer. $\blacksquare$

**Comparative statics — proved without calculus.** A higher input price or lower output price weakly *decreases* chosen input. Unlike the geometric argument above, this has a clean algebraic proof that uses *no* property of $f$ at all: writing $\alpha(w)$ for optimal input at price $w$, revealed-preference-style logic (optimality at $w_1$ and at $w_2$ simultaneously) gives $0\geq(w_1-w_2)(\alpha(w_1)-\alpha(w_2))$ directly — so $w_1<w_2\Rightarrow\alpha(w_1)\geq\alpha(w_2)$, structurally the same "compensated demand can't slope the wrong way" argument as [WARP-based comparative statics for consumers](../consumer-theory/properties-of-demand-functions.md), here requiring no differentiability or even concavity of $f$.

## Where the two objectives genuinely diverge

Both objectives respond the *same way* to price and (usually) technology changes — but not always: **a profit-maximizer can *reduce* output when technology improves** (a possibility the textbook illustrates but doesn't reduce to a single clean condition — it depends on how the *marginal*, not just total, product curve shifts), whereas an output-maximizer, constrained only to stay non-negative on profit, never does. This is the clearest structural gap between the two objectives: output-maximization is monotone in "more is better" almost by construction, while profit-maximization optimizes a genuinely different quantity that need not move in lockstep with output at all.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§6.2–6.3.*
