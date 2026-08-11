---
title: "Mixed Strategies and Interpreting Nash Equilibrium"
source: "Osborne & Rubinstein (2020), §§15.7–15.8 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - game-theory
  - mixed-strategy
  - war-of-attrition
prerequisites:
  - game-theory-basics/strategic-games-and-nash-equilibrium
  - choice-under-uncertainty/the-expected-utility-theorem
---
## Motivation: two populations, no stable pure convention

[Matching pennies](strategic-games-and-nash-equilibrium.md) has no pure Nash equilibrium. Consider instead two large populations, one playing each role; individuals are repeatedly matched at random, and a **steady state** requires each individual's belief about the *distribution* of the opposing population's actions to be correct, with her own action optimal given that belief. If population 1 plays $H$ with fraction $p_1\neq\tfrac12$, one action strictly dominates for population 2, so population 2 cannot mix — contradicting the belief that generated $p_1$ in the first place, unless $p_1=\tfrac12$ exactly, at which point *any* split for population 2 is consistent (everyone is indifferent), including the symmetric $\tfrac12$-$\tfrac12$ split. This population-frequency interpretation is what "mixed strategy" formalizes.

**Definition 15.6 (mixed strategy).** A **mixed strategy** for player $i$ is a probability distribution $\alpha_i$ over $A_i$. A strategy concentrated on a single action ($\alpha_i(a_i)=1$) is a **pure strategy**.

Because a mixed profile induces a *lottery* over action profiles, evaluating it needs [expected-utility preferences](../choice-under-uncertainty/the-expected-utility-theorem.md) over action profiles — a Bernoulli function $u_i$, not just an ordinal ranking of pure profiles.

**Definition 15.7 (mixed strategy equilibrium).** A profile $(\alpha_i)_{i\in N}$ is a **mixed strategy equilibrium** if for every player $i$ and every action $a_i$ with $\alpha_i(a_i)>0$, $i$'s expected payoff from $a_i$ (given $\alpha_{-i}$) is at least as high as from any other action — every action actually played with positive probability must itself be a best response.

Every Nash equilibrium is a (degenerate, pure) mixed strategy equilibrium and vice versa; the genuinely new content is that **every finite game has a mixed strategy equilibrium**, even when it has no pure one (proof beyond this book's scope) — mixing is what restores existence for games like matching pennies.

## Example: matching pennies and Bach-or-Stravinsky

In matching pennies, letting $p_1=\alpha_1(H)$, $p_2=\alpha_2(H)$: any pure strategy for either player is exploitable, and indifference for player $i$ requires the *other* player's mixing probability to equal $\tfrac12$ exactly. The **unique** mixed equilibrium is $p_1=p_2=\tfrac12$.

In [Bach or Stravinsky](strategic-games-and-nash-equilibrium.md), besides the two pure equilibria $(B,B)$ and $(S,S)$, a non-pure equilibrium exists: solving the indifference conditions gives $\alpha_2(B)=\tfrac13,\alpha_2(S)=\tfrac23$ and symmetrically $\alpha_1(B)=\tfrac23,\alpha_1(S)=\tfrac13$ — each player mostly plays her own favorite but sometimes "compromises." The probability the two actually meet is only $\tfrac49$, and each player's expected payoff ($\tfrac23$) is *worse* than her payoff at either pure equilibrium — mixing here is a genuine equilibrium, but not a *good* one for anybody, illustrating that equilibrium existence says nothing about equilibrium desirability.

## War of attrition (Example 15.15)

Two players contest an object worth $1$ each; each period both choose to fight or give up, and a player who outlasts the other by giving up at $t$ incurs cost $tc$. Pure equilibria have the form $(0,t_2)$ or $(t_1,0)$ — one side yields immediately, deterred by the other's credible willingness to wait. The **symmetric mixed equilibrium** requires each period's continuation to be exactly indifferent to giving up now, which pins down a **geometric distribution**: $\alpha(t)=c(1-c)^t$ for every $t\geq0$ — the unique distribution over stopping times consistent with every possible stopping period being a best response. This connects directly to the geometric/memoryless structure that recurs whenever indifference must hold at every stage of a repeated stopping decision.

## Interpreting Nash equilibrium (§15.8)

The book settles on **two** readings, deliberately not adjudicating between them:

1. **A stable norm or convention** — a mode of behavior known to all, self-enforcing because no one who expects it to hold has any incentive to deviate. The equilibrium $(Y,Y)$ in [the coordination game](strategic-games-and-nash-equilibrium.md) represents *the* convention players meet at $Y$; matching pennies, having no pure equilibrium, simply has no such stable norm.
2. **A steady state of belief-and-behavior across populations** — the interpretation this entry opened with, and the one for which mixed strategies are most natural: not "a player randomizes," but "a fixed fraction of a population consistently plays each action, and everyone's beliefs about that fraction are correct."

Both readings deliberately avoid claiming Nash equilibrium describes a one-shot process of *conscious strategic reasoning* by isolated individuals — that stronger claim is explicitly set aside as beyond this book's scope.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§15.7–15.8.*
