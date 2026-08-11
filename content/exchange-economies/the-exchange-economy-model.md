---
title: "The Exchange Economy Model"
source: "Osborne & Rubinstein (2020), §§10.1–10.2 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - exchange-economy
  - competitive-equilibrium
prerequisites:
  - equilibrium-foundations/the-market-model-and-equilibrium
  - consumer-theory/the-consumers-problem
---
## From indivisible houses to divisible goods

**Definition — exchange economy.** $\langle N,(\succeq_i)_{i\in N},e\rangle$: individuals, each with a monotone, continuous preference over bundles $\mathbb{R}^2_+$ (exactly [the consumer-theory primitive](../consumer-theory/consumer-bundles-and-examples.md)), and an initial endowment bundle $e(i)$ for each. The one substantive change from [the housing market](../equilibrium-foundations/the-market-model-and-equilibrium.md): goods are now perfectly divisible, so $R^2_+$ replaces the finite set of houses $H$ everywhere.

Prices $p=(p_1,p_2)$, budget sets $B(p,e(i))=\{x: px\leq pe(i)\}$ — literally [the consumer's budget set](../consumer-theory/budget-sets-and-demand-functions.md), just with the endowment's *value* standing in for wealth $w$.

**Definition — competitive equilibrium.** $(p,a)$ where every $a(i)$ is optimal in $i$'s budget set, and $a$ is an **allocation**: $\sum_i a(i) = \sum_i e(i)$ — total consumption equals total endowment, good by good. As with [market equilibrium for houses](../equilibrium-foundations/the-market-model-and-equilibrium.md), the definition is scale-invariant: $(p,a)$ and $(\lambda p, a)$ for $\lambda>0$ are the same equilibrium.

## Three fully worked equilibria

**Perfect substitutes** ($u_i=x_1+x_2$ for both, endowments $(\alpha,0)$ and $(0,\beta)$): equal prices $(1,1)$ support a whole *family* of equilibria — the initial allocation itself, or any trade of $\varepsilon$ units each way, $0\leq\varepsilon\leq\min\{\alpha,\beta\}$ — since with equal prices every point on each budget line delivers the same utility. **Uniqueness of the equilibrium allocation fails here**, unlike [the housing market with strict preferences](../equilibrium-foundations/welfare-theorems-for-the-housing-market.md) — a first sign that divisibility changes more than just the math.

**Perfect complements** ($u_i=\min\{x_1,x_2\}$, same endowments): if $\alpha=\beta$, *any* positive price ratio works. If $\alpha\neq\beta$ (say $\alpha>\beta$), no equilibrium has *both* prices positive — instead, the scarce good's price goes to zero, since the individual who owns the abundant good literally cannot use more of it without the complementary good, so it becomes worthless at the margin. A further wrinkle: **an individual can be made better off by destroying part of her own endowment** — reducing the surplus of the abundant good can flip which good is "scarce," changing the equilibrium price system in the destroyer's favor. This directly echoes [the money pump argument's spirit](../preferences-and-choice/satisficing-and-the-money-pump-argument.md) in reverse: here it's not irrationality being exploited, just the fact that *having more* of something can be a genuine liability once its effect on equilibrium prices is taken into account.

**Cobb-Douglas** ($u_i=x_1x_2$ for both): a *unique* equilibrium, $p=(\beta/\alpha,1)$ with both individuals ending up at the equal split $(\alpha/2,\beta/2)$ — the clean, well-behaved benchmark case.

## A shortcut for verifying equilibrium

**Proposition.** If every individual's assigned bundle sits exactly on her budget line, and total demand equals total supply for **one** good, it automatically equals total supply for the **other** good too.

*Proof:* summing $p\cdot a(i) = p\cdot e(i)$ over all $i$ and rearranging gives $p_1(\sum a_1(i)-\sum e_1(i)) = p_2(\sum e_2(i)-\sum a_2(i))$; since $p_1,p_2>0$, one side vanishing forces the other to vanish too. $\blacksquare$

This is a genuine computational convenience (check market-clearing for one good, get the other for free), and it's the exact mechanism [the existence proof](existence-and-reopening-trade.md) leans on.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§10.1–10.2.*
