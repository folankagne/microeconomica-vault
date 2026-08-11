---
title: "Arrow's Impossibility Theorem"
source: "Osborne & Rubinstein (2020), §§20.3–20.4 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - social-choice
  - arrows-theorem
  - dictatorship
  - independence-of-irrelevant-alternatives
prerequisites:
  - social-choice/preference-aggregation-functions
---
## Five properties a preference aggregation function might have

**Neutrality.** Swapping two alternatives $x,y$ in *every* individual's ranking swaps them in the social ranking too — the PAF treats alternatives symmetrically, with no alternative privileged by name. All the examples in [the previous entry](preference-aggregation-functions.md) are neutral except external preferences.

**Anonymity.** Swapping *which two individuals* hold which preference relations leaves the social ranking unchanged — the PAF treats individuals symmetrically. Satisfied by everything except dictatorship.

**Positive responsiveness.** If one individual moves $x$ up one step (all else fixed) and $x$ was already at least as good as some $z$ socially, $x$ becomes *strictly* better than $z$ socially — the social ranking moves (weakly) in the direction any individual's ranking moves.

**Pareto.** If *every* individual ranks $x$ above $y$, the social ranking does too — unanimity is respected.

**Independence of irrelevant alternatives (IIA).** The social ranking of $x$ relative to $y$ depends **only** on individuals' relative rankings of $x$ and $y$ — not on how anyone ranks other alternatives, and not on where $x$ or $y$ sit relative to those other alternatives. Dictatorship satisfies IIA trivially (only the dictator's $x$-vs-$y$ ranking matters); some scoring rules **violate** it — a worked example in the textbook shows two profiles with *identical* relative rankings of $a$ and $b$ but different total scores for each, because a third alternative $c$'s position shifts, flipping the scoring rule's ranking of $a$ against $b$ even though no individual's $a$-vs-$b$ preference changed.

## The theorem

**Proposition 20.1 (Arrow's impossibility theorem).** Let $\langle N,X\rangle$ be a society with $|X|\geq3$. A PAF satisfies the Pareto property and IIA **if and only if it is dictatorial**.

*Proof idea (five steps, fixing an alternative $b$):*

1. **Extremal lemma.** In any profile where $b$ sits at the very top or very bottom of *every* individual's ranking, $b$ must be the unique social maximum or unique social minimum. (If some $a,c$ sandwiched $b$ socially, moving $c$ just above $a$ for everyone who ranks $a\succ c$ — without disturbing anyone's ranking of $b$ against $a$ or $c$ — forces, via Pareto and IIA, both $a\succsim b$ and $b\succsim c$ still holding while $c\succ a$ now holds too, a transitivity violation.)
2. **IIA locks this in across profiles.** Whether $b$ ends up socially top or bottom, in any such "$b$ extremal" profile, depends only on *which* individuals rank $b$ at the top — not on how they rank anything else.
3. **A pivotal individual $i^*$ exists.** Starting from $b$ at the bottom for everyone (social minimum, by Pareto) and moving $b$ to the top of each individual's ranking one at a time (in order $1,2,\dots,n$), $b$ must flip from social minimum to social maximum at *some* individual's turn — call her $i^*$. By Step 2, $i^*$'s identity doesn't depend on how the other alternatives are ranked.
4. **$i^*$ dictates every pairwise comparison not involving $b$.** Using a profile where $b$ is deliberately wedged between $a$ and $c$ in $i^*$'s ranking (top for everyone before $i^*$, bottom for everyone after, positioned freely for $i^*$ herself), Steps 1–3 combined with IIA and transitivity force the social ranking of $a$ vs. $c$ to match $i^*$'s.
5. **$i^*$ dictates comparisons involving $b$ too**, by a similar construction inserting a third alternative $c$ strategically. Together, Steps 4–5 make $i^*$ a dictator over *all* of $X$.

## What the theorem does and does not say

The chapter is careful to head off the common overreading: Arrow's theorem does **not** prove that "aggregating preferences is impossible" in general. It proves something narrower — that *no* PAF can simultaneously satisfy Pareto, IIA, **and** be non-dictatorial, when the domain includes *all* possible preference profiles over 3+ alternatives. Scoring rules with strictly decreasing weights satisfy every other property in this chapter and violate only IIA — so IIA specifically, not aggregation per se, is the fragile requirement. Restricting the domain also escapes the impossibility: if alternatives lie along a single dimension (a political spectrum) and every individual's preference is **single-peaked** on it, majority rule *does* produce a transitive social preference — the paradox needs the unrestricted-domain assumption to bite.

This entry resolves the tension flagged when [the same clash between unanimity, transitivity, and completeness was first previewed](../preferences-and-choice/preference-formation-models.md) early in the vault: individually reasonable aggregation ingredients do not automatically combine into a well-behaved social preference, and Arrow's theorem is the precise, general statement of exactly how much they fail to.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§20.3–20.4. Proposition 20.1 is due to Arrow (1951); the proof given is due to Geanakoplos.*
