---
title: "Stability and the Gale-Shapley Matching"
source: "Osborne & Rubinstein (2020), §18.3 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - matching
  - stable-matching
  - gale-shapley
prerequisites:
  - mechanism-design-and-matching/the-gale-shapley-algorithm
---
## Blocking pairs and stability

A matching can satisfy everyone's "I got *some* partner" requirement and still be fragile: two individuals matched to other people might both prefer each other to their assigned partners, and would happily break their existing matches to pair up instead.

**Definition 18.4 (stable matching).** For a society $(X,Y)$ and preference profile $(\succsim_i)_{i\in X\cup Y}$, a matching $\mu$ is unstable if there exist $x\in X$, $y\in Y$ with $y\neq\mu(x)$ such that $x$ prefers $y$ to $\mu(x)$ **and** $y$ prefers $x$ to $\mu^{-1}(y)$ — such a pair $(x,y)$ is called a **blocking pair**. A matching is **stable** if no blocking pair exists.

**Example 18.5.** Take society $(\{1,2,3\},\{1,2,3\})$ where every $X$ has the same preference $Y_1\succ Y_2\succ Y_3$, while $Y_1: X_2\succ X_3\succ X_1$, $Y_2: X_3\succ X_2\succ X_1$, $Y_3: X_1\succ X_3\succ X_2$. Running [serial dictatorship](../equilibrium-foundations/the-jungle-model-and-equilibrium.md) with the $X$'s choosing in order $1,2,3$ gives each $X_i$ matched to $Y_i$ ($X_1$ takes her favorite $Y_1$, $X_2$ takes the best of what remains, $Y_2$, $X_3$ gets $Y_3$). This matching is **unstable**: $X_2$ prefers $Y_1$ to her own match $Y_2$, and $Y_1$ prefers $X_2$ to her own match $X_1$ — $(X_2,Y_1)$ is a blocking pair, and both would defect.

```tikz
\begin{document}
\begin{tikzpicture}[scale=1]
\node[circle,draw,fill=green!15,minimum size=7mm] (X1) at (0,0) {$X_1$};
\node[circle,draw,fill=green!15,minimum size=7mm] (X2) at (0,-1.5) {$X_2$};
\node[circle,draw,fill=green!15,minimum size=7mm] (X3) at (0,-3) {$X_3$};
\node[circle,draw,fill=orange!20,minimum size=7mm] (Y1) at (4,0) {$Y_1$};
\node[circle,draw,fill=orange!20,minimum size=7mm] (Y2) at (4,-1.5) {$Y_2$};
\node[circle,draw,fill=orange!20,minimum size=7mm] (Y3) at (4,-3) {$Y_3$};
\draw[thick] (X1) -- (Y1);
\draw[thick] (X2) -- (Y2);
\draw[thick] (X3) -- (Y3);
\draw[thick,dashed,red] (X2) -- (Y1);
\node[above] at (2,-0.55) {\scriptsize blocking pair};
\end{tikzpicture}
\end{document}
```
*Figure — Example 18.5: solid edges are the serial-dictatorship matching ($X_i$ matched to $Y_i$); the dashed edge marks the blocking pair $(X_2,Y_1)$, whom both prefer to their assigned partners — so the matching is unstable.*

Serial dictatorship, despite always producing *a* matching, offers no guarantee at all against this kind of unraveling: it only ever consults the $X$'s' preferences.

## The Gale-Shapley matching is always stable

**Proposition 18.2.** For any society and preference profile, the Gale-Shapley algorithm generates a stable matching.

*Proof.* Consider $\mathrm{GS}^X$ and let $\mu$ be its output matching. Suppose $x\in X$ prefers some $y\in Y$ to $\mu(x)$. Since $x$ ends up matched to $\mu(x)$ and proposals move down $x$'s preference list only after rejection, $x$ must at some earlier stage have proposed to $y$ (a $Y$ she prefers to her final match) and been **rejected** — in favor of some other $X$ whom $y$ preferred at that time. From that point on, $y$ only ever rejects a tentative match in favor of someone she likes even *more* — rejections only ever trade up for the rejecting side. So $y$'s eventual final partner $\mu^{-1}(y)$ is preferred by $y$ to that rejected $x$. Hence for every $x,y$ with $x$ preferring $y$ to $\mu(x)$, $y$ in turn prefers $\mu^{-1}(y)$ to $x$ — no blocking pair exists, so $\mu$ is stable. $\blacksquare$

The proof leans on exactly one structural fact about deferred acceptance: a $Y$'s tentative match only ever improves (in her own preferences) as the algorithm proceeds, since she rejects an existing tentative match only for someone she prefers more. This is the same "monotone improvement drives the argument" flavor as [the trading-cycle price argument](../equilibrium-foundations/top-trading-cycles-and-existence.md), though the mechanics are different (rejections tightening a $Y$'s standard, rather than prices ordering a cycle).

Note also the logical relationship to [Pareto stability](../exchange-economies/welfare-theorems-and-the-core.md): every stable matching is Pareto stable (no matching, stable or not, can make one individual strictly better off without making some other individual strictly worse off) — but the converse fails, so stability is the strictly finer, more demanding property, in the same spirit as [the core being strictly finer than Pareto stability](../exchange-economies/welfare-theorems-and-the-core.md#a-sharper-stability-concept-the-core) in the exchange-economy setting.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §18.3.*
