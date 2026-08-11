---
title: "Profit-Maximizing Monopoly and Deadweight Loss"
source: "Osborne & Rubinstein (2020), §7.2.1 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - monopoly
  - deadweight-loss
  - price-controls
prerequisites:
  - monopoly/monopolistic-markets-and-marginal-revenue
---
## The MR = MC condition

**Proposition.** In a uniform-price monopolistic market with differentiable demand, if the profit-maximizing monopolist's optimal output $y^*$ is positive, then $\text{MR}(y^*)=\text{MC}(y^*)$.

*Proof:* the monopolist maximizes $P(y)y-C(y)$ over $y$; the standard first-order condition for a differentiable interior maximum gives the result directly. $\blacksquare$

This is necessary, **not sufficient** — [marginal revenue need not be monotone](monopolistic-markets-and-marginal-revenue.md), so $\text{MR}=\text{MC}$ can hold at several outputs simultaneously, and the profit-maximizer is whichever crossing gives the largest *cumulative* gap between the MR and MC curves (the area between them), not merely *a* crossing point.

## Inefficiency and deadweight loss

Since $\text{MR}(y)<P(y)$ always, the monopolist's chosen price *exceeds* marginal cost at $y^*$ — a signature of inefficiency: some potential buyers would pay more than it costs to produce another unit, yet the monopolist doesn't sell it to them, because doing so would require lowering the price on *all* units sold, not just the marginal one.

Using $W(y)=\int_0^y P(x)\,dx$ as a measure of consumer welfare (the area under inverse demand — the natural generalization of "sum of willingness-to-pay" to a continuous good) and total cost as the area under MC, total welfare is maximized at $y^c$ where $P(y^c)=\text{MC}(y^c)$ — the competitive, price-taking outcome. Since the monopolist instead produces $y^*<y^c$, the resulting welfare shortfall is the **deadweight loss**.

```tikz
\begin{document}
\begin{tikzpicture}[scale=1]
\draw[->] (0,0) -- (6,0) node[right] {$y$};
\draw[->] (0,0) -- (0,4.5) node[above] {\$};
\draw[thick] plot[smooth] coordinates {(0.3,3.8) (1.5,3) (3,2.1) (4.5,1.3) (5.7,0.7)};
\node[right] at (5.7,0.7) {$P(y)$};
\draw[thick] plot[smooth] coordinates {(0.3,3.8) (1.2,2.4) (2.2,1.4) (3.2,0.7) (4,0.3)};
\node[below] at (4,0.25) {$MR(y)$};
\draw[thick] plot[smooth] coordinates {(0.3,0.6) (1.5,0.9) (3,1.5) (4.5,2.3) (5.7,3.1)};
\node[right] at (5.7,3.1) {$MC(y)$};
\fill (2.1,1.35) circle (1.5pt);
\fill (3.55,2.05) circle (1.5pt);
\draw[dashed] (2.1,0) -- (2.1,2.5);
\draw[dashed] (3.55,0) -- (3.55,2.5);
\node[below] at (2.1,0) {$y^*$};
\node[below] at (3.55,0) {$y^c$};
\fill[gray!30] (2.1,1.35) -- (3.55,2.05) -- (3.55,1.5) -- cycle;
\end{tikzpicture}
\end{document}
```
*Figure — The monopolist stops at $y^*$ where $MR=MC$, not at the efficient $y^c$ where $P=MC$. The shaded triangle between $y^*$ and $y^c$ — bounded by the demand curve above and the MC curve below — is the deadweight loss: value that would be created by producing those units (buyers value them above cost) but isn't, because the monopolist would have to cut price on inframarginal units too.*

## Two policy responses

**Price ceiling.** Capping the price at $p^{\max}=P(y^c)$ effectively flattens $\text{MR}$ at $p^{\max}$ for outputs where the uncapped price would exceed it — since the monopolist can now sell *up to* the point where demand hits the cap without further price cuts on inframarginal units, the incentive to restrict output to protect price disappears exactly at $y^c$. Chosen correctly, this eliminates the deadweight loss entirely (at the cost of the monopolist's rents, which the policy doesn't attempt to preserve).

**Per-unit subsidy.** A subsidy $t$ per unit sold shifts the *entire* MR curve up by $t$ (revenue effectively rises by $t$ per unit regardless of quantity), moving the MR–MC crossing rightward toward $y^c$. Unlike the price ceiling, this changes the monopolist's *actual* incentives rather than capping the outcome — but the textbook flags an important caveat: **if consumers themselves fund the subsidy** (e.g. via taxes), the policy may leave them worse off even though output rises, since they're now paying for the subsidy in addition to whatever they still pay the monopolist directly.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §7.2.1.*
