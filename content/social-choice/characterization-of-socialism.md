---
title: "Characterization of Socialism"
source: "Osborne & Rubinstein (2020), §19.3 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - social-choice
  - fairness
  - socialism
  - axiomatic-characterization
prerequisites:
  - social-choice/economic-systems-and-fairness-properties
---
## The result: four axioms pin down exactly one system

**Proposition 19.1.** The only economic system that is **efficient**, **symmetric**, **monotone in own productivity**, and **monotone in others' productivities** is **socialism**: all wealth is produced by the individuals with the highest productivity, and total wealth is divided equally among *all* individuals — $F_i(\lambda_1,\dots,\lambda_n)=\max\{\lambda_1,\dots,\lambda_n\}/n$ for every $i$.

*Proof idea.* Fix a productivity profile with maximum $M$. **Step 1 — cap each individual's wealth at $M/n$.** Suppose some individual $i$ got more than $M/n$. Since every other individual's productivity is at most $M$, repeatedly applying *monotonicity in others' productivities* (raising each other individual's productivity up to $M$ can only help $i$, never hurt her) shows $i$ would get at least as much wealth if *everyone* had productivity $M$. Then applying *monotonicity in own productivity* to $i$ herself (if her own productivity was below $M$, raising it to $M$ can't hurt her either) shows $i$'s wealth in the all-productivity-$M$ profile is at least her original wealth. But by *symmetry*, in the all-$M$ profile every individual gets the *same* wealth $H$; if $H>M/n$, the wealth profile $(H,\dots,H)$ would sum to more than $M$ — infeasible, since $M$ is the maximum total producible wealth. Contradiction, so no individual can exceed $M/n$. **Step 2 — feasibility forces exact equality.** *Efficiency* requires the wealths to sum to exactly $M$; since no individual exceeds $M/n$ and there are $n$ individuals, every individual must receive *exactly* $M/n$.

The elegance of this proof is that it needs no calculus and no explicit construction — it derives the *unique* candidate purely by bounding every individual's wealth from above (via the two monotonicity properties plus symmetry) and then using efficiency to convert "at most $M/n$ each" into "exactly $M/n$ each," the same "bound-then-force-equality-via-a-budget-constraint" logic that appears in [the value-summing argument for the welfare theorems](../exchange-economies/welfare-theorems-and-the-core.md).

## Independence: all four axioms are needed

**Proposition 19.2.** The four properties are **independent** — for each one, some economic system satisfies the *other three* but violates that one:

- *Not efficient*: $F_i=\min\{\lambda_1,\dots,\lambda_n\}/n$ (equal split of the *minimum*, not maximum, productivity).
- *Not symmetric*: all wealth to individual 1 regardless of who is most productive: $F_1=\max\{\lambda_1,\dots,\lambda_n\}$, $F_i=0$ otherwise.
- *Not monotone in own productivity*: the *least*-productive individuals split $\max\{\lambda_1,\dots,\lambda_n\}$ equally, everyone else gets zero — becoming more productive can knock you out of the low-productivity group and *cost* you your share.
- *Not monotone in others' productivities*: the *most*-productive individuals split $\max\{\lambda_1,\dots,\lambda_n\}$ equally — a rival's productivity rising to match yours dilutes your equal share, potentially to zero.

This four-way independence check — construct, for each axiom, a system violating only that one — is a standard companion move to any axiomatic characterization; the same pattern appears when checking [the independence of the expected-utility axioms](../choice-under-uncertainty/continuity-and-independence-axioms.md) or [Arrow's axioms](arrows-impossibility-theorem.md).

## What the result is (and isn't) claiming

The chapter is explicit that Proposition 19.1 is not an argument *for* socialism — it is a demonstration that "socialism," so named, is the unique answer to *one specific* combination of efficiency-and-fairness demands, and that other combinations of axioms characterize other systems entirely (e.g. Problem 3 in the textbook develops the **Shapley value** as the unique system satisfying efficiency, symmetry, and two different "contribution"-based axioms). Notice also what the model leaves out: individuals' *needs* play no role (only productivity), and there is no incentive concern — each individual is assumed to produce her full output $\alpha_i\lambda_i$ regardless of how much of it she personally keeps, sidestepping any question of whether socialism-as-defined would actually elicit that production in practice.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §19.3. Inspired by the work of John Roemer (Roemer 1986).*
