---
title: "The Jungle Model and Equilibrium"
source: "Osborne & Rubinstein (2020), §§8.1–8.2 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - equilibrium
  - jungle-model
  - matching
prerequisites:
  - preferences-and-choice/binary-relations-and-preference-relations
---
## Setup: individuals, houses, power

A **society** $\langle N,H,(\succeq_i)_{i\in N}\rangle$ has equally many individuals and houses (one house per person), each individual with a *strict* preference over houses (no ties, for cleanliness). An **allocation** is a one-to-one assignment of houses to individuals.

A **jungle** adds a **power relation** $\succ$ — complete, transitive, antisymmetric (no ties in strength either) — on the individuals: $i\succ j$ means $i$ can simply *take* $j$'s house, and $j$ vacates without resistance (no cost of fighting, no coalitions, no property rights at all — the polar-opposite assumption to [the market model](the-market-model-and-equilibrium.md), which introduces exactly the property rights this model deliberately omits).

**Definition — equilibrium of a jungle.** Allocation $a^*$ is an equilibrium if no individual $i$ prefers the house held by any *weaker* individual $j$ (i.e. $i\succ j$) to her own: for no $i,j$ with $i\succ j$ does $a^*(j)\succ_i a^*(i)$ hold.

## Existence and uniqueness, via a simple procedure

**Serial dictatorship.** Order individuals by strength; the strongest picks her favorite house from everything, the second-strongest picks her favorite from what's left, and so on down the power ranking.

**Proposition (existence).** The serial-dictatorship allocation, run in order of the power relation, is always an equilibrium. *Proof:* each individual receives her favorite house among those not already claimed by someone stronger — by construction, exactly the equilibrium condition.

**Proposition (uniqueness).** Every jungle has *exactly one* equilibrium. *Proof sketch:* suppose $a,b$ are both equilibria and let $i^*$ be the *strongest* individual where they disagree. Everyone stronger than $i^*$ holds the same house under both, so the *set* of houses available to $i^*$ and everyone weaker is identical under $a$ and $b$ — meaning $a(i^*)$ is held by some weaker $j$ under $b$, and $b(i^*)$ by some weaker $k$ under $a$. Equilibrium of $a$ forces $a(i^*)\succeq_{i^*} b(i^*)$; equilibrium of $b$ forces $b(i^*)\succeq_{i^*}a(i^*)$ — together with strict preferences, a contradiction unless $a(i^*)=b(i^*)$. $\blacksquare$

The uniqueness result is stronger than it might look: it isn't just that serial dictatorship *happens* to find a stable outcome — *no other* allocation, however constructed, can also be stable. Raw power, in this model, pins down the outcome completely.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§8.1–8.2. Based on Piccione & Rubinstein (2007).*
