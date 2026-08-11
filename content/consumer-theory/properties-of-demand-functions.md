---
title: "Properties of Demand Functions"
source: "Osborne & Rubinstein (2020), §5.6"
status: enriched
tags:
  - normal-goods
  - giffen-goods
  - slutsky-equation
  - comparative-statics
prerequisites:
  - consumer-theory/rationalizing-demand-and-warp
---
## Three slices through a demand function

Fixing all but one variable of $x((p_1,p_2),w)$ gives three named objects: the **regular (Marshallian) demand function** for good 1, $x_1^*(p_1) = x_1((p_1,p_2^0),w^0)$ — good 1's own demand as a function of its own price; the **cross-demand function**, good 2's demand as a function of good 1's price; and the **Engel function**, demand for a good as a function of wealth alone, prices fixed. For fixed-budget-share demand $x=(\alpha w/p_1, (1-\alpha)w/p_2)$: regular demand for good 1 is $\alpha w^0/p_1$ (notably *independent* of $p_2^0$), cross-demand for good 2 given $p_1$ is the constant $(1-\alpha)w^0/p_2^0$, and the Engel function for good 1 is linear, $\alpha w/p_1^0$.

## Normal, regular, and Giffen goods

**Definitions.** A good is **normal** if its Engel function is increasing (more wealth $\Rightarrow$ buy more). A good is **regular** if its own regular demand function is *decreasing* in its own price; **Giffen** if that demand function is *increasing* in its own price. These properties can also be stated locally, at a specific $((p_1^0,p_2^0),w^0)$, rather than globally.

It's tempting to assume every good is regular ("demand curves slope down"), but **the standard assumptions — monotonicity, continuity, convexity, differentiability — do not by themselves guarantee it.** A rational consumer with perfectly well-behaved preferences can still, in principle, demand *more* of a good as its price rises.

**Proposition — a sufficient condition for normality.** If $\text{MRS}(x_1,x_2)$ is increasing in $x_2$ for every $x_1$, then good 1 is normal.

*Proof sketch:* raise wealth from $w$ to $w^0>w$ holding prices fixed. Let $a$ solve the problem at $w$, and let $a'$ be the point on the *new*, larger budget line directly above $a$ (same $x_1$). Since $a'$ has more of good 2 than $a$ at the same $x_1$, the hypothesis gives $\text{MRS}(a')>\text{MRS}(a)$ — meaning at $a'$ the consumer's willingness to trade good 2 for good 1 now *exceeds* the market price ratio (which [equals MRS exactly at the old optimum $a$](mrs-equals-price-ratio.md)), so the new optimum must involve strictly *more* of good 1 than $a_1$. $\blacksquare$

This is a **comparative statics** result: it compares two outcomes for two different parameter values directly, without modeling any dynamic path connecting them — a static "before/after" contrast, not a claim about adjustment over time.

## The Slutsky property

**Proposition.** Suppose demand $x$ is single-valued, satisfies WARP, and always spends the full budget. Raise $p_1$ to $p_1'>p_1$, and *simultaneously* adjust wealth to $w'$ — exactly enough to still afford the *original* bundle $x((p_1,p_2),w)$ at the new prices. Then $x_1((p_1',p_2),w') \leq x_1((p_1,p_2),w)$: demand for the good whose price rose does not increase, once the consumer is compensated to keep the old bundle affordable.

*Proof:* let $a=x((p_1,p_2),w)$, $b=x((p_1',p_2),w')$. By construction $a\in B((p_1',p_2),w')$, so $b$ is revealed at least as good as $a$. If $b_1>a_1$ held, the *steeper* new budget line (slope $-p_1'/p_2$, steeper than $-p_1/p_2$) would place $b$ strictly *inside* the *original* budget set $B((p_1,p_2),w)$ — since $a$ was chosen there, $a$ would be revealed *better than* $b$, violating WARP. $\blacksquare$

This is the Slutsky decomposition in embryo: it isolates the pure **substitution effect** of a price change — the part that remains after wealth is adjusted to neutralize the change in purchasing power — from the **income effect**, which this compensation scheme deliberately shuts down. It's also the theoretical explanation for why [Giffen behavior](#normal-regular-and-giffen-goods) requires a strong, specifically-signed income effect to overcome a substitution effect that, on its own, always points the "regular" direction: the Slutsky property guarantees the compensated demand curve is non-increasing even when the *uncompensated* one (ordinary regular demand) is not.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §5.6.*
