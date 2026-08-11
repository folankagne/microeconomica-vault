---
title: "Pareto Stability in the Jungle"
source: "Osborne & Rubinstein (2020), §§8.3–8.5 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - pareto-stability
  - jungle-model
prerequisites:
  - equilibrium-foundations/the-jungle-model-and-equilibrium
---
## A second, power-free notion of stability

**Definition — Pareto stability.** Allocation $b$ Pareto-dominates $a$ if every individual weakly prefers $b$'s assignment to $a$'s, and at least one strictly prefers it. An allocation is **Pareto stable** if nothing dominates it. Unlike jungle equilibrium, this notion says nothing about power — it only asks whether unanimous, voluntary improvement is possible. (The textbook deliberately avoids the more common name "Pareto efficient/optimal" here, to keep the concept's *equilibrium* character — immunity to a specific kind of upset, unanimous agreement — separate from any normative connotation of "efficient" or "optimal.")

## Serial dictatorship is Pareto stable too

**Proposition.** For *any* ordering of individuals — not just one derived from a power relation — the serial-dictatorship allocation is Pareto stable.

*Proof idea:* if some $b$ Pareto-dominated the serial-dictatorship allocation $a$, take the *first* individual $i_r$ (in the dictatorship order) who's strictly better off under $b$. Everyone before her got the same house under both (no ties in preference), so $b(i_r)$ must be some house $a(i_s)$ assigned later in the order ($s>r$) — but $a(i_r)$ was chosen as $i_r$'s *favorite remaining* house at her turn, which already included $a(i_s)$ as an option, contradicting $b(i_r)=a(i_s) \succ_{i_r} a(i_r)$. $\blacksquare$

## Jungle equilibrium and Pareto stability coincide (mostly)

**Proposition.** The equilibrium of every jungle is Pareto stable. *Immediate*, given the pieces already assembled: [the unique jungle equilibrium is exactly the serial-dictatorship allocation for the power ordering](the-jungle-model-and-equilibrium.md), and serial-dictatorship allocations are always Pareto stable.

**The converse, via a social planner.** Given *any* Pareto stable allocation $a$, is there *some* power relation that makes $a$ the jungle equilibrium? **Yes** — constructively: by a lemma (some individual always holds her favorite house in any Pareto stable allocation, else a preference cycle among "who holds whose favorite" could be exploited to construct a Pareto improvement), make that individual the strongest; remove her and her house, and repeat on the smaller remaining society (which inherits Pareto stability). The resulting power ranking makes $a$ the unique equilibrium.

Together: **jungle-equilibrium allocations are *exactly* the Pareto stable allocations** — power-based and unanimous-agreement-based stability pick out the identical set of outcomes, just reached by different social mechanisms. This gives a clean diagnostic: observing a group that "doesn't quarrel" over its housing allocation is consistent with *either* a hidden power structure *or* pure voluntary consensus — the allocation alone can't distinguish which produced it.

## A caveat: externalities break the equivalence

All of this assumed each individual cares only about *her own* house. If individuals also care about *who their neighbors are* (a textbook extension briefly noted, not developed in depth here), jungle equilibria can fail to be Pareto stable — someone with the power to evict a disliked neighbor may create an outcome everyone, including herself, would unanimously reject in favor of a different arrangement. The clean equivalence above is a genuine consequence of assuming preferences are purely private, not a general feature of power-based allocation.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§8.3–8.5.*
