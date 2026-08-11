---
title: "The Matching Problem and Matching Methods"
source: "Osborne & Rubinstein (2020), §18.1 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - matching
  - stable-matching
  - matching-methods
prerequisites:
  - equilibrium-foundations/the-jungle-model-and-equilibrium
---
## Two-sided, one-to-one matching

Some individuals are $X$'s and some are $Y$'s, and every individual of each type must be matched with exactly one individual of the other type — managers with assistants, pilots with copilots. Each $X$ has preferences over the $Y$'s and vice versa, and everyone strictly prefers being matched to remaining unmatched. This is structurally close to [the housing market of Chapter 8](../equilibrium-foundations/the-jungle-model-and-equilibrium.md) — a finite population, one-to-one assignment, strict preferences — but now *both* sides have preferences over each other, rather than one side (owners) simply holding indivisible objects (houses) that the other side ranks.

**Definition 18.1 (society and preference profile).** A society $(X,Y)$ consists of finite sets $X,Y$ with the same number of members. A preference profile $(\succsim_i)_{i\in X\cup Y}$ assigns each $x\in X$ a strict preference relation over $Y$, and each $y\in Y$ a strict preference relation over $X$.

**Definition 18.2 (matching).** A matching for $(X,Y)$ is a one-to-one function $\mu:X\to Y$. For a matching $\mu$ and $x\in X$, the pair $(x,\mu(x))$ is called a match.

```tikz
\begin{document}
\begin{tikzpicture}[scale=1]
\node[circle,draw,fill=green!15,minimum size=7mm] (X0) at (0,0) {$x_1$};
\node[circle,draw,fill=green!15,minimum size=7mm] (X1) at (0,-1.3) {$x_2$};
\node[circle,draw,fill=green!15,minimum size=7mm] (X2) at (0,-2.6) {$x_3$};
\node[circle,draw,fill=orange!20,minimum size=7mm] (Y0) at (4,0) {$y_2$};
\node[circle,draw,fill=orange!20,minimum size=7mm] (Y1) at (4,-1.3) {$y_1$};
\node[circle,draw,fill=orange!20,minimum size=7mm] (Y2) at (4,-2.6) {$y_3$};
\draw[thick,->] (X0) -- (Y0);
\draw[thick,->] (X1) -- (Y1);
\draw[thick,->] (X2) -- (Y2);
\node at (-0.3,0.9) {\scriptsize $X$};
\node at (4.3,0.9) {\scriptsize $Y$};
\end{tikzpicture}
\end{document}
```
*Figure — A matching $\mu$ for a society with three $X$'s and three $Y$'s: $\mu(x_1)=y_2$, $\mu(x_2)=y_1$, $\mu(x_3)=y_3$, drawn as a one-to-one function from $X$ to $Y$. Every individual is matched, and no $Y$ is claimed by two $X$'s.*

A **matching method** is simply a rule for producing a matching from any preference profile — the object of study for the rest of this chapter.

**Definition 18.3 (matching method).** A matching method for a society is a function that assigns a matching to each preference profile for the society.

## Three example methods

**Example 18.1 (serial dictatorship).** The $X$'s, in a fixed order, each choose their favorite remaining $Y$ — exactly [serial dictatorship in the jungle](../equilibrium-foundations/the-jungle-model-and-equilibrium.md), now applied with the $Y$'s playing the role of the houses and only the $X$'s' preferences consulted at all. This always terminates in a matching, so it does define a matching method — but, unlike the jungle (where only one side has preferences at all), ignoring the $Y$'s' preferences entirely turns out to have a real cost, developed in [the next entry](the-gale-shapley-algorithm.md).

**Example 18.2 (minimizing aggregate rank).** For each pair $(x,y)$, let $n_x(y)$ be $y$'s rank in $x$'s preferences and $n_y(x)$ be $x$'s rank in $y$'s preferences, and let $I(x,y)=\alpha(n_x(y),n_y(x))$ for some function $\alpha$ increasing in both arguments (e.g. $\alpha(n_1,n_2)=n_1+n_2$) — a measure of the pair's joint dissatisfaction. This method picks the matching minimizing $\sum_{(x,y)\in\mu} I(x,y)$ over the whole society at once.

**Example 18.3 (iterative selection of the best match).** A greedy variant of Example 18.2: repeatedly choose the single pair $(x,y)$ with the smallest $I(x,y)$ among individuals not yet matched, remove both from consideration, and continue until everyone is matched.

All three are reasonable-sounding rules, and all three can behave badly — serial dictatorship can produce matchings two individuals would rather unravel (worked out in [the stability entry](stability-and-the-gale-shapley-matching.md)), while the aggregate-rank methods require an essentially arbitrary choice of $\alpha$ and can be computationally demanding to optimize exactly. The chapter's centerpiece is a fourth method — [the Gale-Shapley algorithm](the-gale-shapley-algorithm.md) — with a simple procedural description and much stronger guarantees.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §18.1.*
