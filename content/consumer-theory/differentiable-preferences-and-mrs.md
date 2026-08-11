---
title: "Differentiable Preferences and the Marginal Rate of Substitution"
source: "Osborne & Rubinstein (2020), §4.6, §5.4; Lecture 2"
status: enriched
tags:
  - marginal-rate-of-substitution
  - differentiability
  - local-valuations
prerequisites:
  - consumer-theory/monotonicity-continuity-and-convexity
---
## Differentiability: what makes an indifference curve smooth

**Definition.** A monotone, convex preference relation is **differentiable** if for every bundle $z$ there exist nonnegative **local valuations** $(v_1(z), v_2(z))$ such that $v_1(z)\delta_1+v_2(z)\delta_2>0$ implies $z+(\varepsilon\delta_1,\varepsilon\delta_2)\succ z$ for some $\varepsilon>0$. Geometrically: there's a line through $z$ such that every direction strictly above it is a (locally) strict improvement. Only the *ratio* $v_1(z)/v_2(z)$ is pinned down — $(v_1,v_2)$ and $(\alpha v_1,\alpha v_2)$ for $\alpha>0$ describe the same local valuations.

**Proposition.** If $\succeq$ is monotone, convex, and represented by $u$ with continuous partial derivatives, then $\succeq$ is differentiable and $(v_1(z),v_2(z))$ can be taken to be $u$'s partial derivatives at $z$ *(proof beyond this course's level)*. For $u(x_1,x_2)=x_1x_2$: $(v_1(z),v_2(z))=(z_2,z_1)$.

## The marginal rate of substitution

**Definition.** For monotone, convex, differentiable $\succeq$, $\text{MRS}(z) = v_1(z)/v_2(z)$.

Two equivalent ways to see what it measures: (i) as **slope of the indifference curve** — for the indifference curve $x_2=g(x_1)$ through $z$ implicitly defined by $u(x_1,g(x_1))=k$, differentiating gives $g'(x_1) = -\partial u/\partial x_1 \big/ \partial u/\partial x_2$, and $\text{MRS} = -g'(x_1)$; (ii) as a **willingness-to-trade** statement — giving up a small amount $\alpha$ of good 1 for $\beta$ of good 2 is an improvement iff $\beta/\alpha > \text{MRS}(z)$, so MRS is exactly the exchange rate that leaves the consumer on the same indifference curve.

**Worked example.** $u(x_1,x_2)=x_1x_2$: partial derivatives give $\text{MRS}=x_2/x_1$. Directly from the indifference curve $x_2=k/x_1$: $g'(x_1)=-k/x_1^2 = -x_1x_2/x_1^2=-x_2/x_1$, matching.

## MRS is ordinal, not tied to any one representation

**Proposition.** If $u$ and $w$ both represent $\succeq$, then $\text{MRS}_u = \text{MRS}_w$ at every bundle.

*Proof:* since both represent the same $\succeq$, $u = f\circ w$ for some strictly increasing $f$ (the [utility representation multiplicity result](../preferences-and-choice/utility-representation-theorem.md)). By the chain rule, $\partial u/\partial x_i = f'(w)\cdot \partial w/\partial x_i$, so the factor $f'(w)>0$ cancels in the ratio $\text{MRS}_u = (\partial u/\partial x_1)/(\partial u/\partial x_2) = (\partial w/\partial x_1)/(\partial w/\partial x_2)=\text{MRS}_w$. $\blacksquare$

This is the direct payoff of [ordinality](../preferences-and-choice/utility-representation-theorem.md): although the utility *level* $u(x)$ carries no independent economic meaning, the MRS — a property of the underlying preference relation itself — is fully representation-invariant. It is why economists can speak of "the" marginal rate of substitution at a bundle without first fixing a particular cardinalization.

## MRS across the standard examples

- **Cobb-Douglas-type** $u=x_1x_2$: $\text{MRS}=x_2/x_1$, strictly positive and defined everywhere on the interior — the canonical smooth, strictly convex case.
- **Quasilinear** $u(x_1,x_2)=x_2+v(x_1)$ for concave $v$ (e.g. $v(x_1)=\log(x_1+1)$): $\text{MRS}=v'(x_1)$, independent of $x_2$ — every indifference curve is a vertical translate of a single curve, since changing $x_2$ shifts utility one-for-one without touching the tradeoff rate.
- **Perfect complements** $u=\min\{x_1,x_2\}$: the formula breaks down at the kink (partial derivatives aren't both defined), and off the 45° line, one good has zero marginal value — no interior MRS to speak of.
- **Useless good** $u=x_1$: $\partial u/\partial x_2=0$ everywhere, so the MRS ratio is undefined (division by zero) — consistent with vertical indifference "curves" (lines), since no amount of good 2 compensates for less of good 1.

The perfect-complements and useless-good cases are exactly where [convexity holds but strict convexity and interior differentiability fail](monotonicity-continuity-and-convexity.md) — a reminder that the smooth MRS machinery is the *typical* case, not a universal feature of convex preferences.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §4.6, §5.4; Lecture Slides 2, ITM (PSE/Paris 1).*
