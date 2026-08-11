---
title: "The Public Project Problem and Strategy-Proof Mechanisms"
source: "Osborne & Rubinstein (2020), §§17.1–17.2 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - mechanism-design
  - public-project
  - strategy-proofness
prerequisites:
  - game-theory-basics/economic-applications-of-nash-equilibrium
---
## Turning the analysis on its head

Every model so far has taken the rules of interaction as given and asked what behavior results. **Mechanism design** reverses the question: fix a *desired* outcome property, and search for rules of interaction — a **mechanism** — that produce it. The textbook develops the idea through a single running model: a community deciding whether to carry out a joint project (a subway line, a bench in a community garden) that affects everyone.

**Definition (public project problem).** A public project problem $\langle N,D\rangle$ consists of a set $N=\{1,\dots,n\}$ of individuals and a set $D=\{0,1\}$ of public decisions ($1$ = the project is executed, $0$ = it is not).

Because the mechanism is allowed to require payments, preferences are defined not just over $d\in D$ but over pairs $(d,t_i)$ of decision and monetary transfer. Each individual $i$ is characterized by a single number $v_i\in\mathbb{R}$ (possibly negative): she is indifferent between "no project, no payment" and "project executed, pay $v_i$" (or receive $-v_i$ if $v_i<0$). Formally, her utility is
$$u_i(d,t_i)=\begin{cases}v_i+t_i & \text{if } d=1\\ t_i & \text{if } d=0.\end{cases}$$
If $v_i>0$ she benefits from the project and would pay up to $v_i$ for it; if $v_i<0$ she is hurt and would pay up to $-v_i$ to block it; $v_i=0$ means indifference. Notice her interest depends only on her *own* valuation — there is no externality built into the preferences themselves, only into the shared decision $d$.

**Definition (valuation profile).** A valuation profile $(v_i)_{i\in N}$ assigns a number $v_i$ to each individual, generating everyone's preferences over $(d,t_i)$ pairs as above.

## Direct mechanisms and the strategy-proofness requirement

The community does not observe valuations directly — only the individuals know their own $v_i$. A **direct mechanism** asks everyone to *report* a number and turns the reports into an outcome.

**Definition (direct mechanism with transfers).** For a public project problem $\langle N,D\rangle$, a direct mechanism with transfers is a collection $(\delta,\tau_1,\dots,\tau_n)$ of functions assigning to every profile of reports $(x_1,\dots,x_n)$ a decision $\delta(x_1,\dots,x_n)\in D$ and a transfer $\tau_i(x_1,\dots,x_n)$ for each $i\in N$.

Since each individual can report *any* number, she might benefit from misreporting — exaggerating a positive valuation, or exaggerating a negative one. The mechanism designer's ideal is to rule this out entirely.

**Definition (strategy-proof mechanism).** $(\delta,\tau_1,\dots,\tau_n)$ is strategy-proof if for every valuation profile $(v_i)_{i\in N}$, every individual $i$, every list of other reports $(x_1,\dots,x_{i-1},x_{i+1},\dots,x_n)$, and every alternative report $z_i$,
$$\delta(x_1,\dots,v_i,\dots,x_n)v_i+\tau_i(x_1,\dots,v_i,\dots,x_n)\;\geq\;\delta(x_1,\dots,z_i,\dots,x_n)v_i+\tau_i(x_1,\dots,z_i,\dots,x_n).$$
That is, reporting one's true valuation is optimal for $i$ *regardless of what everyone else reports* — exactly the [weakly-dominant-action property](../game-theory-basics/economic-applications-of-nash-equilibrium.md) that made truthful bidding attractive in the Vickrey (second-price) auction, now demanded of every individual simultaneously as a design goal rather than verified after the fact. (The definition does not require truth-telling to be the *only* optimal report — merely one of them.)

## Example: majority rule is strategy-proof, but throws away information

**Example 17.1 (majority rule).** The project is executed iff a majority of individuals report a positive number, i.e. $\delta(x_1,\dots,x_n)=1 \iff |\{i:x_i>0\}|>n/2$, with no transfers at all ($\tau_i\equiv0$).

This mechanism is strategy-proof. Take an individual with $v_i>0$: changing her report between two positive numbers never changes the outcome, and switching from positive to nonpositive can only flip the decision from execution to non-execution — strictly worse for her. So she can do no better than reporting truthfully; a symmetric argument covers $v_i<0$.

Majority rule's weakness is exactly what its strategy-proofness costs nothing to buy: it **ignores magnitudes**. If a few individuals would benefit hugely and a majority would be hurt only slightly, majority rule still blocks the project — a clearly inefficient outcome whenever the sum of valuations is actually positive.

## Example: fixing the magnitude problem breaks strategy-proofness

**Example 17.2 (summing reports).** The project is executed iff the sum of reports is positive, $\delta(x_1,\dots,x_n)=1\iff\sum_{j\in N}x_j>0$, again with no transfers.

This *is* sensitive to magnitudes, but it is **not** strategy-proof: an individual with $v_i>0$ whose truthful report leaves the total sum negative (so the project fails) is strictly better off reporting a large enough number to flip the sum positive — she has every incentive to exaggerate.

The natural next question is whether adding *transfers* to the summing-reports rule can restore strategy-proofness while keeping its sensitivity to magnitudes. It can — this is exactly [the Vickrey-Clarke-Groves mechanism](the-vickrey-clarke-groves-mechanism.md).

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§17.1–17.2.*
