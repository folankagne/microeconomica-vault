---
title: "Existence, Strict Competition, and Kantian Equilibrium"
source: "Osborne & Rubinstein (2020), §§15.4–15.6 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - game-theory
  - existence
  - strictly-competitive
  - maxmin
  - kantian-equilibrium
prerequisites:
  - game-theory-basics/strategic-games-and-nash-equilibrium
---
## When must a Nash equilibrium exist?

[Matching pennies](strategic-games-and-nash-equilibrium.md) has no pure-strategy equilibrium, so existence is not automatic — this section gives two sufficient conditions.

**Proposition 15.1 (symmetric games).** Let $G$ be a two-player symmetric game with $A_1=A_2=I$ a closed, bounded interval, and suppose each player has a unique best response to every action of the other, continuous in that action. Then a **symmetric** Nash equilibrium $(x^*,x^*)$ exists.

*Proof idea:* let $g(x)=\mathrm{BR}_1(x)-x$; $g$ is continuous with $g(l)\geq0\geq g(r)$ on $I=[l,r]$, so the intermediate value theorem gives $x^*$ with $\mathrm{BR}_1(x^*)=x^*$, and symmetry of the game makes $x^*$ a best response for player 2 too.

If each player's best response is *increasing* in the other's action, the game has no asymmetric equilibria beyond the symmetric one(s) found this way. If best responses are *decreasing*, asymmetric equilibria can coexist with the symmetric one — e.g. $u_i(a_1,a_2)=-|1-a_1-a_2|$ has $\mathrm{BR}_i(a_j)=1-a_j$, so every pair $(x,1-x)$ is an equilibrium, only $(\tfrac12,\tfrac12)$ symmetric.

**Proposition 15.2 (finite supermodular games).** A two-player game with $A_1=\{1,\dots,K\}$, $A_2=\{1,\dots,L\}$, distinct payoffs, and each best response function **nondecreasing** in the other's action (a **supermodular** game) has a Nash equilibrium.

*Proof idea:* partition $A_1$ into maximal intervals on which player 2's best response $b_m$ is constant; if some interval's implied best response for player 1 falls back inside that same interval, that pair is an equilibrium; otherwise a counting argument (each interval's "return point" must eventually land in a *later* interval, but there are only finitely many intervals) forces a contradiction, so such a pair must exist. Both [the Cournot game](economic-applications-of-nash-equilibrium.md) (decreasing best responses — not supermodular but symmetric) and games with genuine strategic complementarities (like [the effort game](economic-applications-of-nash-equilibrium.md)) illustrate the kind of monotone best-response structure these two propositions exploit, from opposite directions.

## Strictly competitive games and maxmin reasoning

**Definition 15.5 (strictly competitive game).** A two-player game is **strictly competitive** if for all action pairs $a,b$: $a\succsim_1 b \iff b\succsim_2 a$ — the players' interests are exactly opposed. (Also called **zero-sum**: if $u_1$ represents $\succsim_1$, then $u_2=-u_1$ represents $\succsim_2$.) [The location game](economic-applications-of-nash-equilibrium.md) and [matching pennies](strategic-games-and-nash-equilibrium.md) are strictly competitive; [Bach or Stravinsky](strategic-games-and-nash-equilibrium.md) and [the prisoner's dilemma](strategic-games-and-nash-equilibrium.md) are not.

Consider a pessimistic player who picks the action maximizing her *worst-case* payoff: $\max_{a_i\in A_i}\min_{a_j\in A_j}u_i(a_i,a_j)$ — her **maxmin action**. In general games this pessimistic reasoning need not match Nash equilibrium at all (in a variant of Bach or Stravinsky with an asymmetric payoff, maxmin reasoning by both players yields the *non*-equilibrium outcome where they fail to meet). But in strictly competitive games, the two coincide exactly:

**Proposition 15.3 (maxminimization and Nash equilibrium).** Let $G$ be strictly competitive. (i) If $(a_1,a_2)$ is a Nash equilibrium, each $a_i$ solves player $i$'s maxmin problem. (ii) If $G$ has a Nash equilibrium, every player's payoff is the same across *all* equilibria.

*Proof idea:* at a Nash equilibrium, player 1's payoff already equals her worst case against $a_2$ specifically (since 2 has no incentive to deviate from $a_2$), and strict competitiveness converts "player 1 cannot do better than $u_1(a_1,a_2)$ by choosing differently" into "this is exactly the value of her maxmin problem" — the opposing-interests structure pins the two notions together. Part (ii) — equilibrium payoff uniqueness — then follows because every equilibrium payoff must equal this same maxmin value. This does **not** assert existence: matching pennies is strictly competitive and still has no pure Nash equilibrium, motivating [mixed strategies](mixed-strategies-and-interpreting-equilibrium.md) as the fix.

## Kantian equilibrium: an alternative to Nash

At a Nash equilibrium, a deviating player imagines everyone else's action **fixed**. At a **Kantian equilibrium**, a player imagines that if she scales her own action by a factor $\lambda>0$, every other player scales hers by the *same* $\lambda$ — a "what if everyone reasoned like me" counterfactual rather than a unilateral one. Formally $(a_1,a_2)$ is a Kantian equilibrium if $u_i(a_1,a_2)\geq u_i(\lambda a_1,\lambda a_2)$ for both $i$ and all $\lambda>0$.

Applied to [the Cournot duopoly](economic-applications-of-nash-equilibrium.md) with $c=0$: the Kantian condition reduces to $a_1+a_2=\tfrac12$ for *both* players, so **any** split with total output $\tfrac12$ is a Kantian equilibrium — compared to the unique Nash total output of $\tfrac23$ (from $q_1^*=q_2^*=\tfrac13$). Kantian reasoning internalizes the effect of one's own output increase on *both* players symmetrically, exactly the externality that unilateral Nash reasoning ignores — so Kantian equilibria sit closer to the jointly efficient (lower, less competitive) outcome. The point of including this alternative concept is not to replace Nash equilibrium but to make vivid that "no profitable unilateral deviation" is *one specific* stability notion among several coherent ones, not the only conceivable definition of equilibrium.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§15.4–15.6.*
