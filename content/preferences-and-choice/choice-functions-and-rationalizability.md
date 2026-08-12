---
title: "Choice Functions and Rationalizability"
source: "Osborne & Rubinstein (2020), §§2.1–2.2; Lecture 1"
status: enriched
tags:
  - choice-function
  - rationalizability
  - menu-dependence
prerequisites:
  - preferences-and-choice/utility-representation-theorem
---
## Choice as a separate primitive from preference

A preference relation describes a *mental attitude*, independent of any choice — you can have preferences about art you'll never see. **Choice** is a different, directly observable object: what an agent actually does when confronted with a specific menu.

**Definition — choice problem and choice function.** A choice problem for $X$ is a nonempty subset $A\subseteq X$. A choice function $C$ assigns to every choice problem $A$ a single member $C(A)\in A$.

The standard economic move connects the two by assuming the agent is **rational**: she has a preference relation $\succeq$, she's aware of the available set $A$, and she picks the $\succeq$-best element of $A$. When $\succeq$ is represented by a utility function $u$, this is literally $\max\{u(x): x\in A\}$.

## Rationalizability: does observed choice admit *any* underlying preference?

Since real people rarely *consciously* maximize a preference relation, the operative question is weaker: can behavior be **described as if** it does?

**Definition — rationalizable.** A choice function $C$ is rationalizable if there exists a preference relation $\succeq$ such that $C(A)$ is the unique $\succeq$-best element of $A$, for every choice problem $A$.

(Requiring the *unique* best element matters: allowing ties would let the trivial "everything is indifferent" relation rationalize any choice function whatsoever, making the concept vacuous.)

**Worked example.** For $X=\{a,b,c\}$: the choice function assigning $a$ to $\{a,b,c\}$, $a$ to $\{a,b\}$, $a$ to $\{a,c\}$, $b$ to $\{b,c\}$ is rationalized by $a\succ b\succ c$. But the choice function assigning $a$ to $\{a,b\}$, $c$ to $\{a,c\}$, $b$ to $\{b,c\}$ is **not** rationalizable: it would require $a\succ b$, $b\succ c$, **and** $c\succ a$ simultaneously — a direct violation of transitivity. Of the 24 possible choice functions on a 3-element set, only 6 are rationalizable.

## Three cases where menu-dependence breaks rationalizability

The textbook's examples share a structure: the choice from a menu depends on *which other alternatives are present*, not just on the alternative itself — something no single preference relation over the literal alternatives can capture.

- **The median voter.** An agent always picks the median of whatever set of ordered alternatives ($a_1<\dots<a_5$, say) she faces. From $\{a_1,\dots,a_5\}$ she picks $a_3$; from $\{a_3,a_4,a_5\}$ she picks $a_4$ — forcing both $a_3\succ a_4$ and $a_4\succ a_3$. Not rationalizable *over the original alternatives* — though it becomes rationalizable if the alternatives are redescribed as *positions relative to the median* rather than as fixed points.
- **Steak and salmon** (Luce & Raiffa, 1957). Offered salmon (\$2.50) or steak (\$4.00) in an unfamiliar restaurant, a diner picks salmon (worried the steak is mediocre at that price). Told that snails and frog's legs (\$4.50, both detested) are *also* available, he switches to steak. Choosing steak over salmon from the full menu but salmon over steak from the two-item menu cannot be rationalized over {salmon, steak, snails, frog's legs} — but it *is* rationalizable if "steak" is understood as two different goods, *low-quality steak* and *high-quality steak*, with the presence of exotic (expensive) alternatives serving as a quality signal for the steak itself.
- **The partygoer.** Invited by $A$ and $B_1$, she accepts $B_1$; invited by $A$, $B_1$, and $B_2$ (whose relationship with $B_1$ is tense), she accepts $A$ — to avoid the diplomatic cost of choosing one friend over the other in front of both. Not rationalizable over $\{A,B_1,B_2\}$, for the same underlying reason: the meaning of "choosing $B_1$" depends on whether $B_2$ is also in the room.

The common lesson: a choice function's non-rationalizability is often a sign that the *alternatives themselves* have been described too coarsely, collapsing genuinely distinct options (ordinary steak vs. steak-that-signals-quality; $B_1$-with-$B_2$-watching vs. $B_1$-alone) into one label.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§2.1–2.2; Lecture Slides 1, ITM (PSE/Paris 1).*
