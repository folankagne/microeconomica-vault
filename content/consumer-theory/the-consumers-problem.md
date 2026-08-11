---
title: "The Consumer's Problem"
source: "Osborne & Rubinstein (2020), §5.3"
status: enriched
tags:
  - consumers-problem
  - existence
  - uniqueness
prerequisites:
  - consumer-theory/budget-sets-and-demand-functions
---
## Definition

A **rational consumer** has a fixed preference relation and, from every budget set, chooses the best affordable bundle. Formally, the **consumer's problem** for $\succeq$ and $((p_1,p_2),w)$ is: find the $\succeq$-best bundle in $B((p_1,p_2),w)$ — equivalently, if $\succeq$ is represented by $u$, solve $\max_{(x_1,x_2)\in X} u(x_1,x_2)$ subject to $p_1x_1+p_2x_2\leq w$.

## When a solution exists, and when it's unique

**Proposition.** Fix a preference relation and a budget set.

**(a) Continuity $\Rightarrow$ existence.** If $\succeq$ is [continuous](monotonicity-continuity-and-convexity.md), it has a continuous utility representation; since prices are positive, the budget set is compact, and a continuous function on a compact set attains a maximum by a standard result — so a solution exists.

**(b) Strict convexity $\Rightarrow$ at most one solution.** If distinct $a,b$ both solved the problem, the budget set's own convexity puts $(a+b)/2$ inside it too, and [strict convexity of $\succeq$](monotonicity-continuity-and-convexity.md) makes that midpoint strictly better than both — contradicting optimality of $a$ and $b$.

**(c) Monotonicity $\Rightarrow$ the solution is on the budget line.** If a solution $(a_1,a_2)$ satisfied $p_1a_1+p_2a_2<w$, some money is left unspent; adding a small $\varepsilon$ of each good stays affordable and, by monotonicity, is strictly preferred — contradicting optimality.

The three conditions are doing genuinely different jobs: continuity buys *existence* (a purely topological fact about compact sets), strict convexity buys *uniqueness*, and monotonicity buys the intuitive "spend everything" property — none of the three implies either of the others.

## Two fully worked solutions

**Complementary goods**, $u=\min\{x_1,x_2\}$ (monotone but only convex, not *strictly* convex). Monotonicity forces the solution onto the budget line; and since increasing whichever coordinate is currently smaller is always a free improvement (up to the point of equality), any optimum must have $x_1=x_2$. Combined with the budget line: $x^*=(w/(p_1+p_2), w/(p_1+p_2))$ — **unique**, even though strict convexity (the sufficient condition from part (b)) fails here. A useful reminder that sufficient conditions aren't necessary: uniqueness can hold for other reasons entirely.

**Perfect substitutes**, $u=x_1+x_2$. When $p_1\neq p_2$: spend everything on the cheaper good — $(w/p_1,0)$ if $p_1<p_2$. When $p_1=p_2$: *every* bundle on the budget line solves the problem — the flat indifference lines are exactly parallel to the budget line, so uniqueness genuinely fails here (consistent with $u=x_1+x_2$ being convex but not strictly convex).

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §5.3.*
