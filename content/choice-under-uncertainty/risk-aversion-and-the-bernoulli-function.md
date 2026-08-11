---
title: "Risk Aversion and the Bernoulli Function"
source: "Osborne & Rubinstein (2020), §3.5"
status: enriched
tags:
  - risk-aversion
  - concavity
  - certainty-equivalent
prerequisites:
  - choice-under-uncertainty/the-expected-utility-theorem
---
## Defining risk attitudes directly on preferences

For monetary prizes ($Z=\mathbb{R}_+$), write $E(p)=\sum_z p(z)z$ for a lottery's expected value.

**Definitions.** $\succeq$ is **risk-neutral** if $[E(p)]\sim p$ for every lottery $p$ — the agent cares only about the mean, indifferent between a lottery and its certain expected value. $\succeq$ is **risk-averse** if $[E(p)]\succeq p$ always, and **strictly risk-averse** if $[E(p)]\succ p$ for every genuinely random $p$ (support size $>1$) — the sure expected value is *weakly* (resp. *strictly*) preferred to bearing the risk.

These definitions apply to *any* preference relation over lotteries, expected-utility-consistent or not — risk aversion is a primitive behavioral property, not something that presupposes the expected-utility model. Two everyday observations map directly onto it: buying insurance (paying to *reduce* risk, even though insurance typically has a negative expected value once the insurer's margin is included) is evidence of strict risk aversion; gambling (paying to *increase* risk relative to a certain amount) is evidence *against* risk aversion.

## The concavity characterization

**Proposition.** For $\succeq$ consistent with expected utility with Bernoulli function $v$: $\succeq$ is risk-averse $\iff$ $v$ is concave.

*Proof ($\Rightarrow$):* risk aversion gives $[\alpha x+(1-\alpha)y] \succeq \alpha\cdot x\oplus(1-\alpha)\cdot y$ for any two prizes $x,y$ and $\alpha\in[0,1]$; translating via $U$, $v(\alpha x+(1-\alpha)y) \geq \alpha v(x)+(1-\alpha)v(y)$ — exactly the definition of concavity.

*Proof ($\Leftarrow$):* if $v$ is concave, Jensen's inequality gives $v(E(p)) = v\big(\sum_z p(z)z\big) \geq \sum_z p(z)v(z) = U(p)$ directly, so $[E(p)]\succeq p$ for every $p$. $\blacksquare$

This is the reason [the affine-uniqueness of Bernoulli functions](the-expected-utility-theorem.md) matters practically, not just as a technical footnote: concavity is *not* preserved under arbitrary increasing transformations (only affine ones), so "is $v$ concave?" is only a well-posed, representation-independent question because Bernoulli functions are cardinal rather than ordinal. Asking whether an *ordinary* ordinal utility function over sure outcomes is concave would be meaningless — any strictly increasing transform represents the same preference equally well, concave or not — but asking it of a Bernoulli function is meaningful precisely because independence pins the admissible transformations down to positive affine ones.

```tikz
\begin{document}
\begin{tikzpicture}[scale=1]
\draw[->] (0,0) -- (6,0) node[right] {$z$};
\draw[->] (0,0) -- (0,4.5) node[above] {$v(z)$};
\draw[thick] plot[smooth] coordinates {(0.3,0.4) (1,1.5) (2,2.5) (3,3.15) (4,3.6) (5,3.9) (5.7,4.05)};
\draw[dashed] (1,1.5) -- (5,3.9);
\draw[dashed] (3,0) -- (3,3.15);
\draw[dashed] (2.3,0) -- (2.3,2.75);
\draw[dashed] (0,2.75) -- (3,2.75);
\fill (1,1.5) circle (1.5pt);
\fill (5,3.9) circle (1.5pt);
\fill (3,2.75) circle (1.5pt);
\fill (3,3.15) circle (1.5pt);
\node[below] at (1,0) {$z_1$};
\node[below] at (5,0) {$z_2$};
\node[below] at (3,0) {$E(p)$};
\node[below] at (2.3,0) {$CE(p)$};
\node[left] at (0,2.75) {$U(p)$};
\end{tikzpicture}
\end{document}
```
*Figure — Jensen's inequality, drawn: the chord between $(z_1,v(z_1))$ and $(z_2,v(z_2))$ sits below the concave curve $v$. At $E(p)$, the chord gives the lottery's expected utility $U(p)$, strictly below $v(E(p))$ — so the sure amount $E(p)$ beats the lottery. The certainty equivalent $CE(p)$, where the curve itself reaches height $U(p)$, sits strictly to the left of $E(p)$.*

## The certainty equivalent

Though not named as a formal definition in this section, the quantity implicit throughout — the sure amount of money exactly indifferent to a given lottery, $CE(p)$ solving $v(CE(p))=U(p)$ — is the natural summary statistic risk aversion generates: for a strictly risk-averse agent, $CE(p) < E(p)$ always (Jensen's inequality again, strictly), with the gap $E(p)-CE(p)$ serving as a money-metric measure of how costly the lottery's risk is to the agent. This is the concept underlying insurance pricing (an agent will pay up to $E(p)-CE(p)$ above actuarially fair pricing to eliminate a risk) and underlies every applied risk-aversion problem in the course's tutorials — from valuing a risky asset to choosing how much of a risky project to buy.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §3.5. Concept originally due to Pratt (1964).*
