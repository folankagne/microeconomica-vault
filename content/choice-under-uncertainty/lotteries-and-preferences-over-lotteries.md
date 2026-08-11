---
title: "Lotteries and Preferences over Lotteries"
source: "Osborne & Rubinstein (2020), §§3.1–3.2"
status: enriched
tags:
  - lotteries
  - uncertainty
prerequisites:
  - preferences-and-choice/binary-relations-and-preference-relations
---
## Lotteries as a special case of "alternatives"

**Definition.** A lottery over a prize set $Z$ is a function $p:Z\to\mathbb{R}$ assigning positive probability to finitely many prizes, summing to 1; its **support** $\text{supp}(p)$ is the set of prizes with $p(z)>0$. Notation: $[z]$ is the degenerate lottery yielding $z$ for certain; $\alpha_1\cdot z_1\oplus\cdots\oplus\alpha_K\cdot z_K$ is the lottery yielding $z_k$ with probability $\alpha_k$.

This is simply [the general preference-relation model](../preferences-and-choice/binary-relations-and-preference-relations.md) with $X=L(Z)$, the set of all lotteries. Nothing about completeness, transitivity, or [the utility representation theorem](../preferences-and-choice/utility-representation-theorem.md) changes — what's new is the *structure* $L(Z)$ carries (it's a mixture space: you can take convex combinations of lotteries), which licenses two extra properties, [continuity and independence](continuity-and-independence-axioms.md), that have no counterpart for a generic alternative set.

```tikz
\begin{document}
\begin{tikzpicture}[scale=1.3]
\draw[->] (0,0) -- (2.5,0) node[right] {$p_1$};
\draw[->] (0,0) -- (0,2.5) node[above] {$p_2$};
\draw[very thick] (0,2) -- (2,0);
\fill (0,2) circle (1.5pt);
\fill (2,0) circle (1.5pt);
\fill (1,1) circle (1.5pt);
\node[left] at (0,2) {$[z_2]$};
\node[below] at (2,0) {$[z_1]$};
\node[above right] at (1,1) {$0.5{\cdot}z_1\oplus0.5{\cdot}z_2$};
\end{tikzpicture}
\end{document}
```
*Figure — The set of lotteries over two prizes, $L(\{z_1,z_2\})$, is the line segment of points $(p_1,p_2)$ with $p_1+p_2=1$: every point is a probability mixture of the two degenerate lotteries $[z_1]$ and $[z_2]$ at the endpoints. With three prizes, the same idea gives a triangle instead of a segment.*

## Three preference relations over lotteries that are *not* expected utility

These serve as running counterexamples for the properties introduced next:

- **Pessimist.** Rank lotteries by their *worst* possible outcome: $p\succeq q$ iff the worst prize in $\text{supp}(p)$ is at-least-as-good (under some fixed $\succeq^*$ over prizes) as the worst prize in $\text{supp}(q)$. A different $\succeq^*$ generates a different pessimist.
- **Good and bad.** Partition $Z$ into "good" and "bad" prizes; rank lotteries purely by the total probability mass on "good," $G(p)=\sum_{z\in\text{good}}p(z)$.
- **Minimizing options.** Prefer lotteries with *smaller support* — fewer possible realizations — independent of what the realizations actually are; sensible for an agent who wants to be maximally prepared rather than caring about the outcome itself.

Each is a perfectly coherent preference relation (complete, transitive) — but, as the next entry shows, each fails at least one of continuity or independence, and is therefore *not* expressible as maximizing an expected value.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§3.1–3.2.*
