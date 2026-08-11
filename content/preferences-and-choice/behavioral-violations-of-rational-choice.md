---
title: "Behavioral Violations of Rational Choice"
source: "Osborne & Rubinstein (2020), §2.6"
status: enriched
tags:
  - behavioral-economics
  - decoy-effect
  - framing-effects
  - mental-accounting
prerequisites:
  - preferences-and-choice/property-alpha-and-the-rationalizability-theorem
---
## Three ways real choices violate rationality, with real data

Osborne & Rubinstein close the choice chapter with three online experiments (run at gametheory.tau.ac.il, roughly 1,200–4,000 participants each) that isolate specific, replicable violations of the rationality model — not just abstract counterexamples like [the median voter or steak/salmon](choice-functions-and-rationalizability.md), but measured population-level effects.

## Attention effect (asymmetric dominance / decoy effect)

Choosing between Camera A (rating 9.1, 6 MP) and Camera B (rating 8.3, 9 MP): A wins, 48% to 52% — roughly a coin flip, tilted slightly to B. Add Camera C (rating 8.1, 7 MP — *dominated* by B on both dimensions, and not obviously appealing on its own) to the menu: A 30%, **B 68%**, C 2%. Nobody chooses the dominated decoy — but its mere presence drags a large share of choosers from A to B, the option that dominates it. This is a direct, measured **violation of [property $\alpha$](property-alpha-and-the-rationalizability-theorem.md)**: removing C (an alternative nobody chooses) should be irrelevant to the A-vs-B choice under rationality, yet it visibly is not.

## Framing effects

Two "roulette" pairs with identical underlying prize distributions, described differently:

| | White | Red | Green | Yellow |
|---|---|---|---|---|
| Roulette A | 90%, \$0 | 6%, \$45 | 1%, \$30 | 3%, −\$15 |
| Roulette B | 90%, \$0 | 7%, \$45 | 1%, −\$10 | 2%, −\$15 |

Choice A vs. B splits roughly evenly (51% A). Now the *same* two lotteries, with the Yellow outcome of A and the Red outcome of B each split into two separately-labeled contingencies (mathematically identical prize distributions, differently presented as C and D):

| | White | Red | Black | Green | Yellow |
|---|---|---|---|---|---|
| Roulette C | 90%, \$0 | 6%, \$45 | 1%, \$30 | 1%, −\$15 | 2%, −\$15 |
| Roulette D | 90%, \$0 | 6%, \$45 | 1%, \$45 | 1%, −\$10 | 2%, −\$15 |

D dominates C outright, and **93%** choose D — a near-unanimous shift from the roughly 50-50 split on the payoff-equivalent A/B framing. Splitting one outcome into two labeled contingencies changes nothing about the actual gamble, but makes a dominance relationship visible that participants weren't extracting from the "cancel the similar-looking rows" simplification they were apparently applying to A vs. B.

## Mental accounting

Two logically identical scenarios: (i) you bought a \$40 ticket, then lost the *ticket* — buy another? (ii) you're about to buy a \$40 ticket, then discover you lost \$40 in *cash* — buy the ticket anyway? Both reduce to the same choice — "\$80 total and see the show" vs. "\$40 total and don't" — yet **65%** would rebuy after losing the ticket, versus **79%** after losing equivalent cash. The likely mechanism: losing the *ticket* gets mentally coded against a "ticket budget" (now feels like paying \$80 for one ticket, too much), while losing *cash* gets filed as an unrelated loss, leaving the ticket's mental price at its face \$40.

## What these have in common

All three findings share a structure: the *same* underlying alternatives, described or contextualized differently, produce systematically different choices — precisely the menu-dependence and description-dependence that [rationalizability](choice-functions-and-rationalizability.md) rules out by assumption. Since a rational choice function's output can depend only on which alternatives are available, not on how they're grouped, labeled, or accompanied by irrelevant options, these results are not edge cases but direct empirical violations of the model's core assumption — measured, in these particular experiments, at rates far too large to dismiss as noise (a swing from 51% to 93% is not sampling error). This is the natural point of contact between this course's individual-choice-theory backbone and behavioral/experimental economics more broadly.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §2.6.*
