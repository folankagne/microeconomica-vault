---
title: "Monotonicity, Continuity, and Convexity"
source: "Osborne & Rubinstein (2020), §§4.3–4.5; Lecture 2"
status: enriched
tags:
  - monotonicity
  - convexity
  - continuity
prerequisites:
  - consumer-theory/consumer-bundles-and-examples
---
## Monotonicity: goods are good

**Monotone**: $x_1\geq y_1, x_2\geq y_2 \Rightarrow x\succeq y$, and $x_1>y_1, x_2>y_2 \Rightarrow x\succ y$. **Strongly monotone**: $x_1\geq y_1$, $x_2\geq y_2$, and $x\neq y$ (more of *at least one* good, not less of the other) $\Rightarrow x\succ y$. Of [the six standard examples](consumer-bundles-and-examples.md), all are monotone except the ideal-bundle preference (more of a good you've already exceeded the ideal amount of makes you *worse* off); only the lexicographic and constant-tradeoff (with both $v_1,v_2>0$) preferences are strongly monotone — complementary goods and the threshold example are monotone but not strongly so, since adding more of the *currently useless* good leaves utility unchanged.

## Continuity: no preference cliffs

**Continuous**: whenever $x\succ y$, there is $\varepsilon>0$ such that every bundle within $\varepsilon$ of $x$ is still preferred to every bundle within $\varepsilon$ of $y$. **Lexicographic preferences are the standard example of discontinuity**: $(1,2)\succ(1,0)$, yet the bundle $(1-\varepsilon/2, 2)$ — arbitrarily close to $(1,2)$ — is *worse* than $(1,0)$ for every $\varepsilon>0$, since dropping the first coordinate even infinitesimally flips the ranking entirely.

**Proposition.** A preference relation represented by a continuous utility function is continuous. *(Converse also holds, but the proof is beyond this course's level — due to Debreu 1954.)* A useful corollary: for continuous $\succeq$ with $a\succ b\succ c$, some point on the segment from $a$ to $c$ is indifferent to $b$ — an intermediate-value-type argument that resurfaces, in a different guise, for [preferences over lotteries](../choice-under-uncertainty/the-expected-utility-theorem.md).

## Convexity: averages are (weakly) better than extremes

**Convex**: $a\succeq b \Rightarrow \lambda a+(1-\lambda)b \succeq b$ for all $\lambda\in(0,1)$. **Strictly convex**: the same with strict preference whenever $a\neq b$. The motivating intuition (Osborne & Rubinstein's political-candidate example): if a change makes you better off, a *partial* change probably does too — but the converse needn't hold, since a change that makes you worse off might still be an improvement over the *status quo* along the way.

**Proposition — convexity via upper contour sets.** $\succeq$ is convex $\iff$ $\{x\in X: x\succeq x^*\}$ is a convex set for every $x^*$. *Proof:* if $\succeq$ is convex and $a,b$ both weakly beat $x^*$, then (WLOG $a\succeq b$) convexity gives $\lambda a+(1-\lambda)b\succeq b$, and transitivity extends this to $\succeq x^*$. The converse direction is the mirror argument.

**Proposition — concave utility implies convex preferences** (not conversely: $\min\{x_1,x_2\}$ is concave and convex-inducing, but so is $(\min\{x_1,x_2\})^2$, which is *not* concave — convexity of preferences is strictly weaker than concavity of any particular representation).

**Convexity and decreasing MRS.** For $a=(10,10)$, $b=(11,10-\beta)$, $c=(12,10-\beta-\gamma)$ with $a\sim b\sim c$ under a strongly monotone, convex preference: $\beta\geq\gamma$ — the amount of good 2 the consumer will give up for a further unit of good 1 *shrinks* as good 1 accumulates. *Proof sketch:* if $\beta<\gamma$, then $(11, 10-\tfrac12(\beta+\gamma)) = \tfrac12 a+\tfrac12 c$, which convexity forces to be $\succeq c\sim b$ — but strong monotonicity says a bundle with *less* of good 2 than $b$ at the same $x_1=11$ must be worse than $b$, a contradiction. This is the discrete precursor to [the smooth "diminishing MRS" property](differentiable-preferences-and-mrs.md) used throughout the rest of the chapter.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§4.3–4.5; Lecture Slides 2, ITM (PSE/Paris 1).*
