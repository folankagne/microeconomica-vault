---
title: "Economic Applications: Auctions, Location, and Oligopoly"
source: "Osborne & Rubinstein (2020), §15.3 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - game-theory
  - auctions
  - cournot
  - bertrand
  - hotelling
prerequisites:
  - game-theory-basics/strategic-games-and-nash-equilibrium
  - producer-theory/output-vs-profit-maximization
  - monopoly/monopolistic-markets-and-marginal-revenue
---
## Auctions: how the selling rule shapes the equilibrium

**First-price sealed-bid auction (Example 15.6).** Bidders simultaneously submit bids for a single object; the highest bidder wins and pays *her own bid*. Nash equilibrium requires the winner to bid strictly below her valuation (bidding one's true value earns zero surplus even when winning, so a marginal shading is always profitable), and there are *many* Nash equilibria — any profile in which the winner's bid lies between the two highest valuations and every losing bid is low enough to deter deviation supports an equilibrium.

**Second-price sealed-bid auction / Vickrey auction (Example 15.7).** Same format, but the winner pays the *second-highest* bid. **Bidding one's own valuation truthfully is a weakly dominant action** — $u_i(v_i,b_{-i})\geq u_i(b_i,b_{-i})$ for every $b_{-i}$ and every alternative bid $b_i$ — a genuinely stronger equilibrium property than ordinary Nash equilibrium, since it holds regardless of what anyone else does. (This "truthfulness is dominant" property reappears as the central design goal of Problem 2 in [mechanism design](../mechanism-design-and-matching/00-overview.md).) Still, many *other* Nash equilibria exist alongside truthful bidding — and in experiments, a majority of subjects do not actually bid their valuations even in this format (Kagel and Levin 1993), echoing the [traveler's dilemma](strategic-games-and-nash-equilibrium.md)'s lesson that stated equilibrium predictions and observed play can diverge sharply.

## The location game: a strictly competitive Hotelling model

Two sellers choose locations $a_1,a_2\in[0,1]$ along a street of uniformly distributed customers; each customer buys from whichever seller is closer, splitting the tied market share. **Claim.** The unique Nash equilibrium is $(\tfrac12,\tfrac12)$: any deviation from the midpoint costs market share, and if the sellers differ, whoever is farther from $\tfrac12$ can profitably move toward the other. Locating at $\tfrac12$ **guarantees** a market share of at least $\tfrac12$, and no location can guarantee more — an action with this property is called a **maxmin action** (formalized for strictly competitive games generally in [the next entry](existence-strict-competition-and-kantian-equilibrium.md)). Strikingly, the three-player variant of this same game has **no** Nash equilibrium at all — adding a single player destroys existence, since every symmetric or asymmetric configuration admits a profitable unilateral move.

## The effort game: reading off equilibrium from best-response functions

Two players choose effort $a_i\geq0$ at quadratic cost $a_i^2$, with payoff $u_i(a_i,a_j)=a_i(c+a_j)-a_i^2$ (a joint project with complementary effort). Each player's unique best response is $\mathrm{BR}_i(a_j)=\tfrac12(c+a_j)$ — increasing in the other's effort, i.e. efforts are **strategic complements** — and the two best-response lines cross at exactly one point.

```tikz
\begin{document}
\begin{tikzpicture}[scale=1]
\draw[->] (0,0) -- (5.5,0) node[right] {$a_1$};
\draw[->] (0,0) -- (0,5) node[above] {$a_2$};
\draw[thick] (0,1.2) -- (4.6,3.5) node[right] {\scriptsize $\mathrm{BR}_1(a_2)$};
\draw[thick] (1.2,0) -- (3.5,4.6) node[above] {\scriptsize $\mathrm{BR}_2(a_1)$};
\fill (2.35,2.35) circle (2pt);
\node[below right] at (2.35,2.35) {\scriptsize $(c,c)$};
\draw[dashed] (2.35,0) -- (2.35,2.35) -- (0,2.35);
\end{tikzpicture}
\end{document}
```
*Figure — Best-response functions for the effort game: solving $a_1=\tfrac12(c+a_2)$ and $a_2=\tfrac12(c+a_1)$ simultaneously gives the unique Nash equilibrium $(c,c)$, exactly where the two lines intersect.*

## Cournot: quantity-setting oligopoly

Two producers choose quantities $q_1,q_2$; price is $\max\{1-Q,0\}$ where $Q=q_1+q_2$, and each incurs constant marginal cost $c\in[0,1)$. Each firm's best response is $\mathrm{BR}_i(q_j)=\max\{0,\tfrac12(1-q_j-c)\}$ — **decreasing** in the rival's quantity, i.e. quantities are **strategic substitutes** (the opposite slope from the effort game). The unique Nash equilibrium is $q_1^*=q_2^*=\tfrac13(1-c)$. With $n$ symmetric firms, the same logic gives $q_i^*=(1-c)/(n+1)$, equilibrium price $1-(1-c)n/(n+1)$: as $n\to\infty$ the price converges to marginal cost $c$ and profit converges to zero — **Cournot competition converges to the competitive outcome** as the market becomes atomistic, connecting this strategic model back to [zero-profit competitive pricing](../monopoly/profit-maximizing-monopoly-and-deadweight-loss.md) in the limit.

## Bertrand: price-setting duopoly

Same cost structure, but firms choose *prices*; all demand goes to the lower-priced firm (split if tied). Unlike Cournot, a best response to some prices fails to exist (the optimal response to $p_j\in(c,\tfrac12)$ would be "slightly undercut," which has no minimum with continuous prices) — yet the game still has a **unique** Nash equilibrium, $(c,c)$: both prices equal marginal cost, profits are driven to zero, exactly as in Cournot's $n\to\infty$ limit but reached here with only **two** firms. This is the classic "Bertrand paradox" — price competition with homogeneous goods is far more competitive than quantity competition, even with just two sellers.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §15.3.*
