---
title: "Top Trading Cycles and Existence"
source: "Osborne & Rubinstein (2020), §9.2 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - top-trading-cycles
  - existence
  - gale-algorithm
prerequisites:
  - equilibrium-foundations/the-market-model-and-equilibrium
---
## Trading cycles: the atoms of any reallocation

**Definition.** A trading cycle is a sequence of distinct individuals $(i_1,\dots,i_k)$: person $i_1$ receives $i_2$'s initial house, $i_2$ receives $i_3$'s, ..., $i_k$ receives $i_1$'s — a rotation (a single-person cycle $(i_1)$ just means "keeps her own house"). A **trading partition** covers every individual with exactly one cycle.

**Lemma.** For any two allocations $a,b$ of the same market, a **unique** trading partition transforms $a$ into $b$ — constructed by simply chasing where each house moves: start anywhere, follow who-gets-whose-house until the chain closes into a cycle, then start a fresh cycle with anyone not yet covered. Every reallocation, however achieved, decomposes uniquely into simultaneous rotations.

```tikz
\begin{document}
\begin{tikzpicture}[scale=1.3]
\node (i1) at (0,2) {$i_1$};
\node (i2) at (2,2) {$i_2$};
\node (i3) at (1,0) {$i_3$};
\draw[->,thick] (i1) -- (i2);
\draw[->,thick] (i2) -- (i3);
\draw[->,thick] (i3) -- (i1);
\end{tikzpicture}
\end{document}
```
*Figure — A trading cycle $(i_1,i_2,i_3)$: $i_1$ receives $i_2$'s initial house, $i_2$ receives $i_3$'s, and $i_3$ receives $i_1$'s — a closed rotation, achievable either simultaneously or as a sequence of bilateral swaps.*

**Proposition.** In any market equilibrium $(p,a)$, every member of the same trading cycle (in the partition that transforms $e$ to $a$) holds houses of the **same price**. *Proof:* around the cycle, each successive house must be affordable for the previous holder ($p(e(i_l))\geq p(e(i_{l+1}))$), and the cycle closes back on itself — a chain of $\geq$'s that returns to its start forces every link to be an *equality*. $\blacksquare$

## The top trading cycle algorithm

**Definition — top trading cycle.** A cycle $(i_1,\dots,i_k)$ where each $i_l$'s **favorite house in the entire market** happens to be the one $i_{l+1}$ initially owns.

**Procedure (Gale's Top Trading Cycle algorithm).** Start anywhere; follow the arrow "points to the owner of my favorite house" — since the number of individuals is finite, this chain must eventually revisit someone, closing a cycle. That closed loop is a top trading cycle: assign everyone in it their favorite house (which, by construction, is exactly what the cycle delivers), remove them and their houses from the market, and repeat on what's left.

**Proposition (existence).** This procedure always terminates in a full allocation, and the resulting $(p,a)$ — with prices decreasing across successive rounds of the algorithm, equal within each round's cycle — is a market equilibrium.

This is the constructive payoff, exactly parallel to [serial dictatorship for the jungle](the-jungle-model-and-equilibrium.md): a simple, finite, always-terminating procedure that *proves* an equilibrium exists by literally building one. Unlike the jungle's serial dictatorship, though, top trading cycles let *groups* of individuals swap simultaneously in a way that makes everyone in the group strictly better off relative to their own initial holding — a form of mutual benefit that raw power-based serial dictatorship has no mechanism for at all.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §9.2. Algorithm due to David Gale, reported in Shapley & Scarf (1974).*
