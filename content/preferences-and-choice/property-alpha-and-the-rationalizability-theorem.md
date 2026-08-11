---
title: "Property α and the Rationalizability Theorem"
source: "Osborne & Rubinstein (2020), §2.3; Lecture 1"
status: enriched
tags:
  - property-alpha
  - independence-of-irrelevant-alternatives
  - iia
prerequisites:
  - preferences-and-choice/choice-functions-and-rationalizability
---
## Turning "is it rationalizable?" into a checkable condition

[Rationalizability](choice-functions-and-rationalizability.md) is defined by existential quantification over preference relations — not obviously checkable from data on a choice function alone. Property $\alpha$ converts it into a directly testable condition on observed choices.

**Definition — property $\alpha$.** A choice function $c$ satisfies property $\alpha$ if for any sets $B\subset A\subseteq X$ with $c(A)\in B$, we have $c(B)=c(A)$.

In words: if $x^*$ is chosen from the larger set $A$, and some *unchosen* alternatives are removed to form a smaller set $B$ (with $x^*$ still in $B$), choice from $B$ must still be $x^*$. This is why the condition is also called **Independence of Irrelevant Alternatives (IIA)**: eliminating options that weren't going to be chosen anyway shouldn't flip the choice among the ones that remain. None of [the median voter, steak/salmon, or partygoer examples](choice-functions-and-rationalizability.md) satisfy it — in each, removing an unchosen alternative *does* flip the choice.

## The equivalence theorem

**Proposition 1.** Every rationalizable choice function satisfies property $\alpha$.

*Proof:* if $\succeq$ rationalizes $c$, then $c(A)\succeq y$ for all $y\in A$ implies $c(A)\succeq y$ for all $y$ in any subset $B\subset A$ — so $c(A)$ remains the $\succeq$-best element of $B$, forcing $c(B)=c(A)$. $\blacksquare$

**Proposition 2 (the harder direction).** If $X$ is finite, any choice function satisfying property $\alpha$ is rationalizable.

*Proof (constructive):* let $a_1=c(X)$, $a_2=c(X\setminus\{a_1\})$, $a_3=c(X\setminus\{a_1,a_2\})$, and so on — peeling off the chosen element from the shrinking remainder. Define $\succeq$ by $a_1\succ a_2\succ\cdots\succ a_n$. For any choice problem $A$, let $a_m$ be the *first* element of $A$ in this sequence. By construction $c(\{a_m,\dots,a_n\})=a_m$, and since $A\subseteq\{a_m,\dots,a_n\}$ with $a_m\in A$, property $\alpha$ forces $c(A)=a_m$ — exactly the $\succeq$-best element of $A$. $\blacksquare$

Together with [the utility representation theorem](utility-representation-theorem.md), this closes a three-way loop for finite $X$: **property $\alpha$ $\iff$ rationalizable by some $\succeq$ $\iff$ rationalizable by some utility function** $u$, i.e. $C(A)=\arg\max_{x\in A}u(x)$ for every $A$. Any one of the three can be taken as the primitive definition of "behaves rationally"; the others follow.

## The practical payoff: building preferences from choice data

Property $\alpha$ isn't just a characterization result — it's a recipe. If observed choices satisfy $\alpha$, the constructive proof of Proposition 2 tells you *exactly how* to recover the underlying preference relation from the data: repeatedly ask what's chosen from the whole remaining set, peel it off, repeat. This is the theoretical basis for treating revealed choices as data on preferences at all, e.g. when estimating utility functions from limited choice observations to extrapolate further behavior.

The flip side is equally important: property $\alpha$ is not the *only* way to be behaviorally coherent. [Satisficing](satisficing-and-the-money-pump-argument.md) — Herbert Simon's alternative procedure — is not preference-maximization by construction, yet turns out to satisfy $\alpha$ and is therefore rationalizable too; observationally, a satisficer is indistinguishable from a preference-maximizer.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §2.3; Lecture Slides 1, ITM (PSE/Paris 1).*
