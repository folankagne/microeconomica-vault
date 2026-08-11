---
title: "Satisficing and the Money Pump Argument"
source: "Osborne & Rubinstein (2020), §§2.4–2.5"
status: enriched
tags:
  - satisficing
  - money-pump
  - herbert-simon
prerequisites:
  - preferences-and-choice/property-alpha-and-the-rationalizability-theorem
---
## Satisficing: "good enough," not "best"

Herbert Simon's alternative to optimization: an employer interviews candidates in a fixed order (e.g. alphabetical) and stops at the *first* one clearing an aspiration threshold, rather than scanning every candidate for the best.

**Definition — satisficing choice function.** Given a valuation $v:X\to\mathbb{R}$, an aspiration level $v^*$, and an ordering $O$ of $X$: for $A=\{a_1,\dots,a_K\}$ ordered by $O$, choose the *first* $a_k$ with $v(a_k)\geq v^*$ if one exists; otherwise choose the *last* element of $A$ under $O$.

**Proposition.** Every satisficing choice function is rationalizable.

*Proof:* build $\succeq$ by ranking all "satisfactory" alternatives $X^+=\{x: v(x)\geq v^*\}$ in the order $O$ gives them, then all "unsatisfactory" alternatives $X^-=\{x: v(x)<v^*\}$ in the *reverse* of $O$. For any $A$: if $A\cap X^+\neq\emptyset$, the $\succeq$-best element of $A$ is the first element of $A\cap X^+$ under $O$ — exactly the satisficing choice. If $A\subseteq X^-$, the $\succeq$-best element is the *last* element of $A$ under the reversed order on $X^-$ — again exactly the satisficing choice. $\blacksquare$

This is the sharpest illustration in the chapter of why [property $\alpha$](property-alpha-and-the-rationalizability-theorem.md) matters more than the *psychological description* of the procedure: satisficing is explicitly **not** presented as utility maximization by its own designer (Simon proposed it as a *behavioral alternative* to optimization, motivated by bounded rationality), yet it satisfies $\alpha$ and is therefore observationally indistinguishable, choice-function by choice-function, from some agent maximizing some preference relation. Rationalizability is a statement about the *pattern* of choices, not about the cognitive process generating them.

## The money pump: a normative defense of rationalizability

Why should choice satisfy property $\alpha$ at all? One argument is that violating it is *exploitable*.

Suppose $X=\{a,b,c\}$ and a choice function assigns $a$ to $\{a,b\}$, $b$ to $\{b,c\}$, $c$ to $\{a,c\}$ — a cyclic pattern, clearly violating $\alpha$. If holding $y$ over $x$ (when $y$ is chosen over $x$) is worth at least \$1 to the agent, a manipulator can: give her $a$; offer to swap $a\to c$ for \$1 (she accepts, since $c$ beats $a$ in $\{a,c\}$); offer $c\to b$ for \$1 (accepts); offer $b\to a$ for \$1 (accepts) — three trades later she holds $a$ again, exactly where she started, and is \$3 poorer. The cycle repeats indefinitely: a **money pump**.

More generally, *any* violation of property $\alpha$ — not just a full 3-cycle — is exploitable this way: if $B\subset A$, $c(A)\in B$, but $c(B)\neq c(A)$, a manipulator can offer to swap $c(A)$ for $c(B)$ while restricting attention to $B$ (accepted, since $c(B)\neq c(A)$ is chosen there), then offer to swap back while restricting attention to the full set $A$ (accepted, since $c(A)$ is chosen there) — extracting money on every round trip.

**The caveat, stated honestly by the textbook itself:** the argument's force depends entirely on the agent never *noticing* she's being repeatedly exploited in a cycle. Whether that's a persuasive normative defense of rationality — versus simply a description of what a *naive* $\alpha$-violator would suffer — is left as an open question rather than resolved. It's a caution against over-reading "rationality is testable" as "irrationality is costly": the second claim needs the extra, non-trivial assumption that the agent can't detect the pattern.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§2.4–2.5.*
