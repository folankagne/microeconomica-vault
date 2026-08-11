---
title: "Strategic Games and Nash Equilibrium"
source: "Osborne & Rubinstein (2020), §§15.1–15.2 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - game-theory
  - nash-equilibrium
  - strategic-game
prerequisites:
  - preferences-and-choice/binary-relations-and-preference-relations
---
## The model

A **strategic game** is a triple $\langle N,(A_i)_{i\in N},(\succsim_i)_{i\in N}\rangle$: a finite set of players $N$, and for each player $i$ a set of actions $A_i$ and a preference relation $\succsim_i$ over **action profiles** $(a_j)_{j\in N}$ — not just over her own action, since what she cares about depends on everyone's choices jointly. This is the simultaneous-move counterpart of [the consumer's problem](../consumer-theory/the-consumers-problem.md): instead of one agent optimizing against fixed prices, $n$ agents optimize against each other's choices at once.

**Definition (best response).** Player $i$'s **best response** to an action profile $a_{-i}$ of the other players is an action $a_i\in A_i$ such that $(a_i,a_{-i})\succsim_i(a_i',a_{-i})$ for every $a_i'\in A_i$.

**Definition (Nash equilibrium).** An action profile $a^*=(a_i^*)_{i\in N}$ is a **Nash equilibrium** if for every player $i$, $a_i^*$ is a best response to $a_{-i}^*$ — equivalently, no single player can gain by unilaterally deviating, holding everyone else's action fixed.

The "holding everyone else's action fixed" clause is doing all the conceptual work: Nash equilibrium is a check of one-shot, one-player deviations, not a claim about coordinated or sequential deviations — a theme this entry's examples probe directly, and one that [extensive games](extensive-games-and-backward-induction.md) revisit by adding an explicit order of moves.

## Basic examples: the four canonical $2\times2$ games

**Traveler's dilemma (Example 15.1).** Two travelers independently claim a reimbursement in $\{2,\dots,100\}$; if the claims match, both are paid that amount, and if they differ, both are paid the *lower* claim, with the higher claimer additionally fined $2$ and the lower claimer additionally rewarded $2$. Iterated best-response reasoning drives the unique Nash equilibrium all the way down to $(2,2)$ — yet in experiments with over 21,000 game-theory students, only 22% actually chose the equilibrium action, most choosing something close to 100. This is one of the sharpest illustrations in the book that Nash equilibrium is a property of the *modeled* preferences, and its predictive failure here says as much about whether real payoffs match the stated dollar amounts (spite, trust, non-monetary utility) as about the solution concept itself.

**Prisoner's dilemma (Example 15.2).** Two suspects each choose Cooperate (stay silent) or Defect (confess); each strictly prefers to Defect regardless of the other's choice (Defect strictly dominates), yet $(D,D)$ is strictly worse for *both* than $(C,C)$. This is the canonical illustration that individually rational behavior — indeed, dominant-strategy behavior — need not be Pareto stable; the unique Nash equilibrium is not the Pareto-efficient outcome.

**Definition (symmetric game).** A two-player game is **symmetric** if $A_1=A_2$ and player 1's preference over $(a_1,a_2)$ agrees with player 2's preference over $(a_2,a_1)$ (swapping the two players' roles leaves the game unchanged).

**Bach or Stravinsky / "Where to meet?" (Example 15.3).** Two people want to meet, but disagree about the venue; each strictly prefers meeting at her own favorite to meeting at the other's, and strictly prefers *any* meeting to not meeting at all. Two pure Nash equilibria exist — $(B,B)$ and $(S,S)$ — with no way, within the model alone, to select between them; this is the first example in the book where multiplicity of equilibrium is the substantive finding, not a defect to be resolved.

**Matching pennies / odds-or-evens (Example 15.4).** Each player shows a coin; player 1 wants the faces to match, player 2 wants them to differ. This game is **strictly competitive** — a genuine conflict of interest — and has **no** pure-strategy Nash equilibrium: whatever pure profile is proposed, one player has a profitable deviation. This is the motivating example for [mixed strategies](mixed-strategies-and-interpreting-equilibrium.md).

**Coordination game (Example 15.5).** Both players choose among the same three options and are rewarded (differently) for matching; three symmetric Nash equilibria exist, one Pareto-dominating the other two — showing that even absent conflicting interests, "which equilibrium" remains a genuine question.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§15.1–15.2.*
