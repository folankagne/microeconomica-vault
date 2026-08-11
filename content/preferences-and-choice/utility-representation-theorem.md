---
title: "The Utility Representation Theorem"
source: "Osborne & Rubinstein (2020), §1.4; Lecture 1"
status: enriched
tags:
  - utility-function
  - representation-theorem
  - ordinal-utility
prerequisites:
  - preferences-and-choice/binary-relations-and-preference-relations
---
## Why bother with a number at all

A preference relation is already a complete description of an agent's tastes. The reason to additionally look for a **utility function** $u:X\to\mathbb{R}$ representing it — $x\succeq y \iff u(x)\geq u(y)$ — is purely instrumental: maximizing a real-valued function over a set has known algorithms and well-understood calculus, while "find the $\succeq$-best element" does not, in general, admit either. If a utility representation exists, preference-maximization becomes ordinary function-maximization.

**Proposition (link to choice).** If $u$ represents $\succeq$, then $C_\succeq(A) = \{x\in A \mid x\succeq y\ \forall y\in A\} = \arg\max_{x\in A} u(x)$ for every $A\subseteq X$ — the $\succeq$-maximizers of any set coincide exactly with the $u$-maximizers. This is what licenses treating "preference maximization" and "utility maximization" as interchangeable throughout the rest of the course.

## The representation theorem

**Theorem.** A binary relation $\succeq$ on a *finite* set $X$ can be represented by a utility function if and only if it is complete and transitive.

The "only if" direction is short: if $u$ represents $\succeq$, completeness of $\succeq$ follows because any two reals are comparable ($u(x)\geq u(y)$ or $u(y)\geq u(x)$), and transitivity follows because $\geq$ on $\mathbb{R}$ is transitive.

The "if" direction is the substantive result, and it's constructive — the proof builds an explicit $u$, not just an existence argument. Define $Z(x) = \{z\in X \mid x\succ z\}$, the set of alternatives strictly worse than $x$. One shows: (i) $x\sim y \Rightarrow Z(x)=Z(y)$; (ii) $x\succ y \Rightarrow Z(y)\subsetneq Z(x)$ (strictly). Peeling off successive layers of minimal elements ($M_1$ = the worst alternatives, $M_2$ = the worst of what remains, and so on — finiteness of $X$ guarantees this process terminates) and setting $u(x) = k$ for $x\in M_k$ produces a valid representation: $u$ literally counts how many alternatives are worse than $x$.

**Worked example — cinema seats.** A 40-row, 50-column cinema; an agent lexicographically prefers rows further back, then (within a row) seats further left. The layer-peeling construction assigns utility $1$ to row 1, column 50 (last removed... first removed, i.e. worst), up to utility $2{,}000$ for row 40, column 1 (best) — collapsing to the closed form $u(x) = 50r(x) - c(x) + 1$ for row $r(x)$ and column $c(x)$.

## Where finiteness actually bites

The theorem's proof leans on $X$ being finite (to guarantee minimal elements exist and the layering process terminates). This isn't a proof artifact — **the theorem is false on infinite sets in general**:

**Proposition — a non-representable preference relation.** The lexicographic preference on the unit square $X=\{(x_1,x_2): x_1,x_2\in[0,1]\}$ — first coordinate decisive, second coordinate breaking ties — admits **no** utility representation at all.

*Proof idea:* Suppose $u$ represented it. For every $x_1\in[0,1]$, $(x_1,1)\succ(x_1,0)$, so $u(x_1,1) > u(x_1,0)$; pick a rational number $f(x_1)$ strictly between them. Distinct $x_1$'s give disjoint intervals (since raising $x_1$ strictly raises utility), so $f$ is an injection from the uncountable set $[0,1]$ into the countable set $\mathbb{Q}$ — impossible by Cantor's diagonal argument. $\blacksquare$

This is the direct payoff of introducing lexicographic preferences among [the preference-formation models](preference-formation-models.md): they're the standard example showing utility representability is a genuinely restrictive extra property beyond completeness and transitivity, once infinite alternative sets are in play.

## Utility is ordinal, not cardinal

**Proposition.** If $f:\mathbb{R}\to\mathbb{R}$ is strictly increasing and $u$ represents $\succeq$, then $w = f\circ u$ also represents $\succeq$.

*Proof:* $w(x)\geq w(y) \iff f(u(x))\geq f(u(y)) \iff u(x)\geq u(y)$ (since $f$ is strictly increasing) $\iff x\succeq y$. $\blacksquare$

So $u$ and $3u-7$ and $u^3$ (for $u>0$) all represent the *same* preference relation whenever $u$ does. Concretely: if $u(\text{MD})=2$ and $u(\text{JD})=u(\text{MBA})=0$ represents some ranking, then so does $v(\text{MD})=1,\, v(\text{JD})=v(\text{MBA})=0$, and so does $g(\text{MD})=2,\, g(\text{JD})=g(\text{MBA})=\sqrt2$ — but $\ell(\text{MD})=2,\ell(\text{JD})=1,\ell(\text{MBA})=0$ does **not**, since it breaks the required indifference $\text{JD}\sim\text{MBA}$ by assigning them different values. The content of a utility representation is exhausted by the *ranking* it induces; the numbers themselves, and any notion of "how much more," carry no independent meaning. This is why $u$ is called an **ordinal** utility function, and it's the reason [marginal rate of substitution](../consumer-theory/differentiable-preferences-and-mrs.md) — a ratio of derivatives of $u$ — turns out to be invariant to which particular representation $u$ is used, while $u$'s raw *level* is not economically meaningful on its own.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §1.4; Lecture Slides 1, ITM (PSE/Paris 1).*
