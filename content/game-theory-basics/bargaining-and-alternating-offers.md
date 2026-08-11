---
title: "Bargaining and Alternating Offers"
source: "Osborne & Rubinstein (2020), §16.4 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - game-theory
  - bargaining
  - rubinstein-bargaining
  - subgame-perfect-equilibrium
prerequisites:
  - game-theory-basics/extensive-games-and-backward-induction
---
Four bargaining protocols over splitting a pie $X=\{(x_1,x_2):x_1+x_2=1,\,x_i\geq0\}$, identical except for **who can propose, how many rounds there are, and whether waiting is costly** — and each variant's unique SPE prediction swings dramatically, the chapter's central point: bargaining *outcomes* are extremely sensitive to bargaining *procedure*.

## Protocol 1: take-it-or-leave-it (the ultimatum game, revisited)

[Already analyzed](extensive-games-and-backward-induction.md): player 1 proposes once, player 2 accepts or rejects. SPE gives (essentially) the entire pie to player 1 — whoever makes the one and only offer has all the power, since player 2's only credible move is to accept anything better than nothing.

## Protocol 2: finite horizon with alternating offers

Now offers alternate for up to $T$ periods, with disagreement after period $T$'s rejection ending the game at $(0,0)$.

**Proposition 16.5.** In every SPE of a finite-horizon bargaining game with alternating offers, the player who proposes in the **last** period gets the *entire* pie, and the other player gets nothing.

*Proof idea:* backward induction from period $T$: whoever proposes last simply offers the other the smallest acceptable amount (in the limiting case, zero), and this unravels backward — at $T-1$, the responder already anticipates getting nothing from waiting to $T$, so she accepts almost anything now, and so on to period $1$. All bargaining power concentrates entirely on **who moves last**, a strikingly fragile dependence on an arbitrary deadline.

## Protocol 3: infinite horizon, one-sided offers, no discounting

Remove the deadline — player 1 always proposes, player 2 always responds, forever, with no cost to delay.

**Proposition 16.6.** For **every** partition $x^*\in X$, an SPE exists in which agreement on $x^*$ is reached immediately. An SPE also exists in which the players **never** agree.

*Proof idea (agreement case):* player 1 always proposes $x^*$; player 2 accepts any offer giving her at least $x_2^*$ and nothing less. Neither has a profitable deviation: player 1 gains nothing by offering more than necessary, and player 2 gains nothing by holding out, since player 1 never budges. *Proof idea (disagreement case):* player 2's strategy interprets any offer other than $(1,0)$ as a "sign of weakness" that predicts player 1 will eventually concede everything — so she rejects every intermediate offer, which in turn (correctly, in equilibrium) deters player 1 from ever making one. **Removing the deadline destroys the sharp prediction entirely**: with no cost to waiting, essentially any split — indeed even permanent disagreement — can be rationalized as self-enforcing, since neither side is ever forced to concede by the mere passage of time.

## Protocol 4: infinite horizon, one-sided offers, with discounting

Reintroduce structure by making time costly: agreement on $x$ at period $t$ pays player $i$ a discounted $(\delta_i)^t x_i$, with $\delta_1=\alpha,\delta_2=\beta\in(0,1)$.

**Proposition 16.7.** For any $\alpha,\beta\in(0,1)$, the infinite-horizon game with one-sided offers and discounting has a **unique** SPE, in which player 1 gets the whole pie immediately.

*Proof idea:* let $M$ be the supremum of player 2's payoff across all SPE. If player 2 ever rejects an offer, the continuation game is identical to the whole game, so rejecting is worth at most $\beta M$ (one period's delay applied to the best she could ever hope for) — meaning she must accept any offer giving her more than $\beta M$. This bounds player 1's worst-case equilibrium payoff at $1-\beta M$, hence bounds $M$ itself: $M\leq \beta M$, which given $\beta<1$ forces $M=0$. With player 2's continuation value pinned at exactly zero, player 1 can always profitably offer her an arbitrarily small positive amount rather than nothing, so equilibrium play is immediate agreement at $(1,0)$ in the limit.

**Discounting alone — not the number of rounds, not who moves "first" — is what restores a sharp, essentially unique prediction**, and it does so in the most extreme possible way here because only player 1 ever proposes. (The book's discussion of the *fully* alternating-offers game with two-sided discounting — the celebrated Rubinstein 1982 bargaining solution, where impatience determines a smooth *split* of the pie between the players rather than an all-or-nothing outcome — is referenced but developed only for the one-sided-offer case in this chapter; the qualitative lesson still transfers: **whoever is more patient (higher $\delta$) captures a larger share**, since impatience is precisely the cost of insisting.)

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §16.4.*
