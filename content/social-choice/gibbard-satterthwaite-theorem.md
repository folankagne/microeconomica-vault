---
title: "The Gibbard-Satterthwaite Theorem"
source: "Osborne & Rubinstein (2020), §20.5 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - social-choice
  - strategy-proofness
  - dictatorship
  - gibbard-satterthwaite
prerequisites:
  - social-choice/arrows-impossibility-theorem
---
## From ranking alternatives to choosing one

A **preference aggregation function** outputs an entire social *ranking*; a **social choice rule** is leaner — it outputs a single chosen *alternative* for each preference profile.

**Definition (social choice rule).** A function $f$ assigning some $x\in X$ to every profile of strict preference relations over $X$.

**Definition (unanimity).** $f((\succsim_i)_{i\in N})=x$ whenever $x$ is every individual's top choice — the rule respects full consensus.

**Definition (strategy-proofness).** For every individual $j$ and every profile, reporting her *true* preference relation is (weakly) optimal for $j$, no matter what everyone else reports: $f(\succsim)\succsim_j f(\succsim_j',\succsim_{-j})$ for every misreport $\succsim_j'$. This is exactly [the dominant-strategy truthfulness property from the second-price/Vickrey auction](../game-theory-basics/economic-applications-of-nash-equilibrium.md) — a social choice rule is strategy-proof precisely when truthful reporting is a *dominant strategy* for every participant, generalizing that single-good result to an arbitrary set of social alternatives.

## The theorem

**Proposition 20.2 (Gibbard-Satterthwaite theorem).** For any society $\langle N,X\rangle$ with $|X|\geq3$, any social choice rule that is unanimous and strategy-proof is a **dictatorship**: some individual $i^*$'s top-ranked alternative is always chosen.

Any dictatorship trivially satisfies both properties (the dictator has nothing to gain by lying since her top choice is always implemented; nobody else's report changes the outcome at all, so truth is as good as anything). The content of the theorem is the converse — proved here by **reducing to Arrow's theorem**, not from scratch.

*Proof idea (six steps):*

1. **Local robustness.** If raising one alternative $y$ in one individual $j$'s ranking is the *only* change to a profile, the chosen outcome can shift to at most $\{x,y\}$ (the old winner or the newly-raised alternative) — anything else would let $j$ profitably misreport.
2. **Two-alternative confinement.** Whenever $x$ and $y$ are every individual's top two alternatives (in either order), $f$ must choose one of $x,y$ — never some third alternative, again by strategy-proofness (someone could otherwise misreport to force a better top-two outcome).
3. **IIA-like invariance.** Within such "$x,y$ top two for everyone" profiles, the choice between $x$ and $y$ depends only on individuals' *relative* rankings of $x$ vs. $y$, not on their order otherwise — proved by transforming one profile into another one alternative-swap at a time, using Steps 1–2 at each swap.
4. **Constructing a derived PAF.** Define a social preference $\succsim$ from $f$ by: $x\succsim y$ iff $f$ chooses $x$ when $x,y$ are (artificially) moved to the top of every individual's ranking, preserving each individual's original relative order of $x$ and $y$. Steps 2–3 show this $\succsim$ is complete and transitive — i.e. an honest preference relation, not just a binary comparison.
5. **The derived PAF satisfies Arrow's hypotheses.** Step 3's invariance is exactly IIA for this derived $\succsim$; unanimity of $f$ delivers the Pareto property for $\succsim$. **By Arrow's impossibility theorem itself, $\succsim$ must be dictatorial** — some $i^*$'s ranking always determines $\succsim$.
6. **$i^*$'s dictatorship transfers back to $f$.** Since $\succsim$ dictated by $i^*$ pins down the pairwise comparison used to define the top-two choice in Step 2, $f$ always selects $i^*$'s $\succsim_{i^*}$-favorite alternative — $f$ is a dictatorship with the *same* dictator as the derived PAF.

## Why this matters beyond voting

Gibbard-Satterthwaite is the reason [mechanism design](../mechanism-design-and-matching/00-overview.md) cannot generally hope for a rule that is simultaneously unanimous, strategy-proof, and responsive to more than a single individual's preferences, once three or more outcomes are on the table — the **second-price auction's** truthfulness (only two possible "alternatives" in a sense — who wins — but with continuous payments as a side channel) survives specifically *because* money provides an extra degree of freedom the pure social-choice setting here lacks. Any real voting mechanism with three or more candidates is therefore manipulable by *some* voter in *some* circumstance, unless it is a dictatorship — not a flaw of any particular electoral system, but a structural fact about the entire class of unanimous, strategy-proof rules.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §20.5. The proof given uses Arrow's impossibility theorem (Proposition 20.1); several other proofs exist in the literature.*
