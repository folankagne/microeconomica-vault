---
title: "Binary Relations and Preference Relations"
source: "Osborne & Rubinstein (2020), §1.1, §1.3; Lecture 1"
status: enriched
tags:
  - preferences
  - binary-relations
  - completeness
  - transitivity
prerequisites: []
---
## The questionnaire metaphor

Take a set of alternatives $X$ — phone contracts, jobs, consumption bundles, contingent plans. The lecture frames an agent's tastes as her answers to a **questionnaire Q**: for every pair $x, y \in X$, she reports exactly one of "I strictly prefer $x$ to $y$" ($x \succ y$), "I strictly prefer $y$ to $x$" ($y \succ x$), or "I am indifferent" ($x \sim y$). Three features of this setup are easy to miss because they're built into the questionnaire's design rather than stated as assumptions: she must answer every pair (**completeness** — no "I can't compare them"), her answer doesn't depend on when she's asked (**stability** — no "most days I prefer $x$, but not always"), and the answer format carries no information about *how much* she prefers one to the other (**ordinality** — "I like $x$ twice as much as $y$" isn't an available response).

## Binary relations, formally

Osborne & Rubinstein work instead with a **binary relation** $\succeq$ on $X$ (a subset of $X \times X$), read "at least as good as," built from a second questionnaire **R**: for every pair, "$x$ is at least as preferred as $y$" ($x \succeq y$), where *both* answers can be given for the same pair. The two questionnaires translate into each other exactly: $x \succeq y$ and $y \succeq x$ together mean $x \sim y$; $x \succeq y$ alone (not $y\succeq x$) means $x \succ y$. The $\succeq$ formulation is less intuitive but algebraically far more convenient, which is why it's the one used going forward.

**Definition — complete.** $\succeq$ on $X$ is complete if for all $x, y \in X$, $x \succeq y$ or $y \succeq x$ (or both). Completeness implies reflexivity ($x \succeq x$ for every $x$) as a special case — a property the raw Q-questionnaire couldn't even ask about, since nobody compares an alternative to itself.

**Definition — transitive.** $\succeq$ is transitive if $x \succeq y$ and $y \succeq z$ imply $x \succeq z$, for all $x,y,z \in X$.

**Definition — preference relation.** A preference relation on $X$ is a complete and transitive binary relation on $X$.

The derived relations $\sim$ (indifference: $x\succeq y$ and $y\succeq x$) and $\succ$ (strict preference: $x\succeq y$ but not $y\succeq x$) inherit transitivity from $\succeq$ — proved directly from the definitions, not assumed separately. $\sim$ is additionally reflexive and symmetric, making it an **equivalence relation**; its equivalence classes are called **indifference sets**, alternatives the agent regards as equally desirable.

## Why transitivity is the assumption doing the work

Completeness is close to definitionally forced by requiring an answer to every question. Transitivity is a genuine, falsifiable restriction, and the textbook doesn't hide that it's contestable:

- **The sugar-grain argument.** Let $c$ be a cup of coffee, $c+i$ the same cup with $i$ grains of sugar. Since one more grain is imperceptible, $c+i \sim c+(i+1)$ for every $i$ — yet after $100{,}000$ grains, $c \succ c+100{,}000$ is obvious. Chained indifference need not preserve itself.
- **Condorcet cycles from aggregating criteria.** Ranking three restaurants $a,b,c$ by majority vote of three food critics with rankings $a\succ_1 b\succ_1 c$, $c\succ_2 a\succ_2 b$, $b\succ_3 c\succ_3 a$ gives $a\succ b$ (2 of 3 critics), $b\succ c$ (2 of 3), **and** $c\succ a$ (2 of 3) — a genuine intransitive cycle, not a paradox of notation.

Despite these, the course keeps transitivity, because it's both the most standard assumption and — as [the utility representation theorem](utility-representation-theorem.md) shows — the thing that makes preferences representable by a single number at all.

## Transitivity under experimental pressure

Osborne & Rubinstein report their own online questionnaire: 36 pairwise comparisons among nine vacation packages (city, hotel quality, food quality, price), roughly 1,300 respondents. Only **15%** answer with zero transitivity violations; the median respondent violates transitivity on 6 out of 84 possible triples. Strikingly, a quarter of respondents rank inconsistently across three options where two ("options 1 and 2") describe the *literally identical* package with its attributes listed in a different order — almost everyone calls those two indifferent, so the inconsistency comes entirely from how each is compared to a third, genuinely different option. The order in which attributes are *listed* measurably moves stated preferences, even holding the substance fixed. This is exactly the kind of finding [the later evidence on choice inconsistent with rationality](behavioral-violations-of-rational-choice.md) generalizes.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§1.1, 1.3; Lecture Slides 1, "Introduction to Microeconomics" (ITM, PSE/Paris 1, M1 Economics & Psychology).*
