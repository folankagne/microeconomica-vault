---
title: "Indivisible Goods, Money, and Uncertainty"
source: "Osborne & Rubinstein (2020), §§11.1–11.2 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - supply-and-demand
  - state-contingent-claims
  - insurance
prerequisites:
  - exchange-economies/welfare-theorems-and-the-core
  - choice-under-uncertainty/the-expected-utility-theorem
---
## Variant 1: the ordinary supply-and-demand diagram, derived properly

A market for one indivisible unit-or-nothing good, traded for money. Each individual $i$ has a **valuation** $v_i\geq0$; preferences are $u_i(x_1,x_2)=x_1+v_ix_2$ (quasilinear — money enters linearly, so there's no wealth effect to worry about). This is [the exchange-economy machinery](../exchange-economies/the-exchange-economy-model.md), specialized to $X=\mathbb{R}_+\times\{0,1\}$ rather than $\mathbb{R}^2_+$.

**Proposition (full characterization).** Order individuals by valuation, $v_1\geq\cdots\geq v_n$; let $s$ be the number of units available (sellers). A price $p$ is an equilibrium price if and only if $v_{s+1}\leq p\leq v_s$ — the price sits between the valuation of the marginal seller and the marginal buyer.

```tikz
\begin{document}
\begin{tikzpicture}[scale=1]
\draw[->] (0,0) -- (6,0) node[right] {units};
\draw[->] (0,0) -- (0,4.5) node[above] {price};
\draw[thick] plot coordinates {(0,3.8) (1,3.4) (1,3) (2,2.6) (2,2.1) (3,1.7) (3,1.3) (4,1) (4,0.6) (5,0.3)};
\node[right] at (5,0.3) {buyers' valuations};
\draw[thick] plot coordinates {(0,0.3) (1,0.6) (1,1) (2,1.3) (2,1.7) (3,2.1) (3,2.6) (4,3) (4,3.4) (5,3.8)};
\node[right] at (5,3.8) {sellers' valuations};
\fill[gray!25] (2.9,1.75) rectangle (3.1,2);
\draw[dashed] (3,0) -- (3,2.6);
\node[below] at (3,0) {$s$};
\end{tikzpicture}
\end{document}
```
*Figure — Buyers' valuations plotted descending, sellers' ascending: the shaded band between them at quantity $s$ is exactly the equilibrium price range $[v_{s+1},v_s]$ — the ordinary supply-and-demand crossing, now derived as a special case of competitive equilibrium in an exchange economy, not introduced as a separate primitive.*

**Pareto stability and the core coincide exactly with competitive equilibrium here** — a genuinely stronger and cleaner result than [the general exchange-economy case](welfare-theorems-and-the-core.md): every core allocation of this specific market is *also* a competitive equilibrium allocation (not just the reverse), so "immune to coalitional deviation" and "supportable by a single market-clearing price" turn out to be the *same* set of outcomes, not merely nested ones. This tight coincidence is special to the linear, quasilinear structure of this market — it does not carry over to the general two-good exchange economy of the previous chapter.

## Variant 2: uncertainty as just another pair of goods

**The trick**: relabel "future states of the world" as goods. With two equally-agreed-upon states occurring with probabilities $\pi_1,\pi_2$, a **state-contingent claim** $(x_1,x_2)$ pays $x_1$ if state 1 occurs, $x_2$ if state 2 occurs — and if every individual's enjoyment of money doesn't depend on *which* state delivers it, $(x_1,x_2)$ is literally [a lottery](../choice-under-uncertainty/lotteries-and-preferences-over-lotteries.md), and expected-utility preferences $\pi_1u_i(x_1)+\pi_2u_i(x_2)$ are exactly [a Bernoulli-function representation](../choice-under-uncertainty/the-expected-utility-theorem.md) applied to this two-good bundle space. The indifference curves of such a preference have slope $-\pi_1/\pi_2$ exactly along the 45° line $x_1=x_2$ — "full insurance," equal consumption regardless of the state — which is precisely where [risk-averse](../choice-under-uncertainty/risk-aversion-and-the-bernoulli-function.md) agents with concave $u_i$ want to sit if state-contingent trade is available on fair terms.

This single reframing turns [the entire exchange-economy apparatus](welfare-theorems-and-the-core.md) — competitive equilibrium, existence, Pareto stability, the core — into a theory of **insurance and betting markets**: individuals whose risk exposures run in opposite directions across states (one is wealthy in state $A$ and poor in state $B$, the other the reverse) can trade contingent claims to *both* end up better insured, exactly the two-person example motivating the section. No new machinery is required — uncertainty, in this model, is not a separate topic from exchange, it's an exchange economy in a different coordinate system.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§11.1–11.2.*
