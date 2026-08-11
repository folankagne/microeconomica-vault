---
title: "Models of Preference Formation"
source: "Osborne & Rubinstein (2020), §1.2"
status: enriched
tags:
  - preferences
  - lexicographic-preferences
  - condorcet-paradox
prerequisites:
  - preferences-and-choice/binary-relations-and-preference-relations
---
## Preferences are taken as given — but it's worth asking where they'd come from

The standard move in economic theory is to *endow* an agent with a preference relation and not ask where it originates. Osborne & Rubinstein briefly step outside that convention to check which natural preference-formation stories actually deliver a valid preference relation (complete and transitive) and which don't — a useful diagnostic for [why transitivity is the load-bearing assumption](binary-relations-and-preference-relations.md).

## Schemes that work

- **Value function.** The agent has a number $v(x)$ in mind for each alternative; $x\succeq y \iff v(x)\geq v(y)$. Always complete and transitive, since $\geq$ on the reals is complete and transitive — this is exactly a [utility function](utility-representation-theorem.md) by construction, just introduced before the formal machinery.
- **Distance function.** One alternative is "ideal"; $x\succeq y \iff d(x)\leq d(y)$ for a distance $d$ from the ideal. A special case of a value function with $v(x) = -d(x)$.
- **Lexicographic preferences.** Two complete, transitive relations $\succeq_1,\succeq_2$ rank two separate features (e.g. memory size, then screen resolution for computers), with the first breaking all ties and the second used only to break ties in the first: $x\succeq y$ iff $x\succ_1 y$, or $x\sim_1 y$ and $x\succeq_2 y$. Completeness is inherited directly from $\succeq_1,\succeq_2$; transitivity requires checking two cases (first feature decisive, or tied and second feature decisive) but goes through cleanly. This construction reappears as the canonical example of a preference relation that **cannot** be represented by any utility function once $X$ is infinite — see [the utility representation theorem](utility-representation-theorem.md).

## Schemes that break completeness or transitivity

- **Unanimity rule.** $n$ separate complete/transitive criteria $\succeq_1,\dots,\succeq_n$ (e.g. a parent weighing each child's preferences); define $x\succeq y$ iff $x\succeq_i y$ for **every** $i$. This is transitive but generally **not complete**: if criterion $j$ ranks $x$ above $y$ while criterion $k$ ranks $y$ above $x$, unanimity is simply silent on the pair.
- **Majority rule.** Three complete, transitive, *antisymmetric* criteria (antisymmetric: no ties within any single criterion); define $x\succeq y$ iff a majority of the three rank $x$ above $y$. This **is** complete — for any pair, at least two of three criteria must agree on a ranking — but is generally **not transitive**: the Condorcet-cycle example is precisely this construction (three critics ranking three restaurants), reproduced formally here as $a\succ_1 b\succ_1 c$, $b\succ_2 c\succ_2 a$, $c\succ_3 a\succ_3 b$, giving the cycle $a\succ b\succ c\succ a$.

## The pattern worth remembering

Aggregating several individually well-behaved rankings into one does not automatically produce a well-behaved ranking — unanimity trades away completeness, majority rule trades away transitivity. Nothing about *individually* reasonable aggregation rules guarantees the two properties a preference relation needs simultaneously. This exact tension resurfaces, formalized and made precise, when the course reaches [social preference aggregation and Arrow's impossibility theorem](../social-choice/arrows-impossibility-theorem.md) later in the book.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §1.2.*
