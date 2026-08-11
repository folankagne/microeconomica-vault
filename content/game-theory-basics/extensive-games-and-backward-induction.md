---
title: "Extensive Games and Backward Induction"
source: "Osborne & Rubinstein (2020), §§16.1–16.3 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - game-theory
  - extensive-game
  - subgame-perfect-equilibrium
  - backward-induction
prerequisites:
  - game-theory-basics/strategic-games-and-nash-equilibrium
---
## The model: histories, not just actions

An **extensive game** (with perfect information) $\langle N,H,P,(\succsim_i)_{i\in N}\rangle$ replaces simultaneous action profiles with **sequences of moves**: $H$ is a set of **histories** (finite sequences of actions, closed under taking prefixes), $Z\subseteq H$ the **terminal** ones, $P:H\setminus Z\to N$ assigns the mover to each nonterminal history, and each player has preferences $\succsim_i$ over $Z$ only. Every earlier action is assumed observed before the next move — this is the "perfect information" restriction.

```tikz
\begin{document}
\begin{tikzpicture}[scale=1, level distance=14mm, sibling distance=28mm]
\node {1}
  child { node[below] {} edge from parent node[left] {In} }
  child { node[draw,rectangle,inner sep=2pt] {$1,5$} edge from parent node[right] {Out} };
\node at (-1.4,-1.4) {2};
\draw (-1.4,-1.4) -- (-2.6,-2.8) node[below] {$2,2$};
\draw (-1.4,-1.4) -- (-0.2,-2.8) node[below] {$0,0$};
\node at (-2.6,-2.0) {\scriptsize Cooperate};
\node at (-0.2,-2.0) {\scriptsize Fight};
\end{tikzpicture}
\end{document}
```
*Figure — The entry game: player 1 chooses In or Out; if In, player 2 chooses Cooperate or Fight. Payoffs are (player 1, player 2). This single tree is the running example for every concept below.*

**Definition (strategy).** A **strategy** for player $i$ specifies an action at *every* history after which $i$ moves — including histories that never arise if $i$ follows that very strategy. This is stronger than an everyday "plan of action": a strategy for player 1 in a longer game must specify what she'd do even at nodes her own earlier choices make unreachable, because evaluating what *other* players should do requires knowing what would happen off the path too.

Each strategy profile $s$ generates a unique **terminal history** $z(s)$ by applying $s_{P(\varnothing)}$, then whichever player moves next, and so on. More generally $z(h,s)$ is the terminal history reached if history $h$ has occurred and play then follows $s$.

## Two solution concepts, one crucial difference

**Nash equilibrium of an extensive game**: $z(s)\succsim_i z(s_{-i},r_i)$ for every player $i$ and every alternative strategy $r_i$ — no player can do better by deviating, *evaluated only at the start of the game*.

**Definition (subgame perfect equilibrium, SPE)**: $z(h,s)\succsim_i z(h,(s_{-i},r_i))$ for **every** player $i$ and **every** nonterminal history $h$ with $P(h)=i$ — optimality must hold after *every* history, including ones $s$ itself never reaches.

In the entry game, $(\text{Out},\text{Fight})$ is a Nash equilibrium: given that 2 threatens Fight, entering is worse than staying Out, so Out is optimal, and given Out, 2's off-path plan is never tested. But this threat is **not credible** — if In actually occurred, 2 strictly prefers Cooperate — so $(\text{Out},\text{Fight})$ fails subgame perfection, while $(\text{In},\text{Cooperate})$ survives as the unique SPE. This gap between Nash and subgame-perfect equilibrium — an empty threat sustaining an outcome nobody would actually carry out — is the central reason SPE, not plain Nash equilibrium, is the working solution concept for sequential games.

## Two examples of multiplicity

**Ultimatum game (Example 16.1).** Player 1 proposes a split $(x_1,x_2)$ of two units; player 2 accepts (Y) or rejects (N), with disagreement giving both zero. Nash equilibrium is nearly unrestrictive — *any* split is sustainable by pairing it with a threat from player 2 to reject anything else — but subgame perfection forces player 2 to accept any offer she weakly prefers to disagreement, leaving exactly two SPE: $((2,0),(Y,Y,Y))$ and $((1,1),(Y,Y,N))$, both giving player 1 (almost) everything, since player 2 cannot credibly threaten to reject a positive offer.

**Centipede game (Example 16.2).** Players alternately choose to stop (grabbing a fixed split) or continue (shrinking their own payoff while growing the pie for both, if eventually stopped). Every Nash equilibrium happens to yield immediate stopping, but *many* Nash equilibria exist (off-path behavior is unconstrained); backward induction pins down a **unique** SPE — stop at the very first opportunity — by an inductive argument from the last possible move backward. Experimentally, most people continue for a while, one of the sharper documented gaps between subgame-perfect prediction and observed play.

## Backward induction: computing SPE by working from the end

**Definition (diameter).** The diameter of history $h$ is the number of actions remaining in the longest continuation of $h$.

**Backward induction procedure.** Start with histories of diameter $1$ (one move from terminal): the mover there simply picks her best available terminal outcome. Substituting that choice in, histories of diameter $2$ now have a well-defined "if I move here, this predictable outcome follows," so their movers optimize too — and so on back to the initial history. This is well-defined whenever the game has finitely many histories (or, more generally, whenever an optimal action always exists at each step).

**Definition (one-deviation property).** A strategy profile satisfies this if, at every history, the mover cannot improve her payoff by changing *only* her action at that single history, holding the rest of her strategy fixed.

**Proposition 16.1.** In a finite-horizon extensive game, a strategy profile satisfies the one-deviation property if and only if it is a subgame perfect equilibrium.

*Proof idea:* SPE trivially implies the one-deviation property (a subset of all possible deviations). The converse needs finiteness: if some multi-step deviation improved a player's payoff, take a *shortest* such profitable deviation and consider its last step — by minimality, everything after that step already matches an SPE-consistent continuation, so the one-deviation property applied at that last step already rules out the deviation, a contradiction. This telescoping argument is exactly why finite horizons matter — with infinite histories the equivalence can fail.

**Proposition 16.2.** A strategy profile is generated by backward induction if and only if it is a subgame perfect equilibrium.

*Proof idea:* by construction, backward induction satisfies the one-deviation property at every history (each step optimizes exactly one player's action, holding the already-fixed continuation constant), so Proposition 16.1 delivers subgame perfection immediately. This is the practical payoff of the whole apparatus: to *find* an SPE, it suffices to solve the game end-first, one move at a time — exactly the method used on [the entry game](#the-model-histories-not-just-actions) and [the ultimatum game](#two-examples-of-multiplicity) above, and the same method [bargaining](bargaining-and-alternating-offers.md) applies to games with many, or infinitely many, periods.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§16.1–16.3.*
