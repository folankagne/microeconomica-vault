---
title: "The Allais Paradox"
source: "Osborne & Rubinstein (2020), §3.4"
status: enriched
tags:
  - allais-paradox
  - independence-axiom
  - behavioral-economics
prerequisites:
  - choice-under-uncertainty/the-expected-utility-theorem
---
## The two questions

**Question 1.** Choose between $L_1$ (\$4,000 with probability 0.2, else \$0) and $R_1$ (\$3,000 with probability 0.25, else \$0).

**Question 2.** Choose between $L_2$ (\$4,000 with probability 0.8, else \$0) and $R_2$ (\$3,000 for certain).

The key algebraic relationship: $L_1 = 0.25\cdot L_2\oplus0.75\cdot[\$0]$ and $R_1=0.25\cdot R_2\oplus0.75\cdot[\$0]$ — both pairs are the *same* compound-lottery construction (25% chance of playing the "Question 2" lottery, 75% chance of \$0), differing only in whether $L_2$ or $R_2$ sits in the 25%-probability slot. By [the independence axiom](continuity-and-independence-axioms.md), any expected-utility-consistent preference must rank $L_1$ vs. $R_1$ **exactly** the way it ranks $L_2$ vs. $R_2$ — only two response patterns, ($L_1,L_2$) or ($R_1,R_2$), are consistent with expected utility at all.

## What people actually choose

From 7,932 responses: 20% choose ($L_1,L_2$), 31% choose ($R_1,R_2$) — together, 51%, the expected-utility-consistent patterns. Of the remainder, only 5% choose ($R_1,L_2$). The single most popular pattern — **44%** — is ($L_1,R_2$): risk-seeking on the low-stakes comparison, risk-averse on the high-stakes one. Osborne & Rubinstein note dryly that this group "include[s] the authors of this book" — the paradox isn't a fringe anomaly, it's close to the modal response.

## Why ($L_1$, $R_2$) is intuitively appealing but formally inconsistent

Two separate psychological stories, one for each question:

- **Question 2**: the security of \$3,000 *for certain* feels qualitatively different from an 80% chance at \$4,000 — the small residual risk of walking away with nothing looms large when certainty is on the table, pushing toward $R_2$ (risk aversion at the margin of certainty).
- **Question 1**: neither option offers certainty, so the frame shifts — probabilities 0.20 and 0.25 look "close enough" to ignore, so attention shifts to the prize difference (\$4,000 vs. \$3,000), pushing toward $L_1$.

Both intuitions are individually reasonable — but [the independence axiom](continuity-and-independence-axioms.md) says the "\$0 with 75% probability" component, present identically in both $L_1$/$R_1$, is supposed to be *irrelevant* to how the remaining 25%-probability slot gets compared. The paradox shows real preferences don't obey that cancellation: certainty (an all-or-nothing distinction) carries independent psychological weight that expected utility's linearity-in-probabilities cannot represent.

## What this does and doesn't settle

The textbook is explicit that this isn't a case of "irrational" subjects to be corrected — it's evidence that **the independence axiom itself**, not just some ancillary assumption, fails as a positive description of choice for a very large share of people, even sophisticated ones. The chapter notes that many alternative theories have been proposed to accommodate this and related findings (Allais-type violations, and others explored in behavioral decision theory), but adds a caution worth taking seriously: "the behavior of many people is inconsistent with any of these alternatives; each theory seems at best to fit some people's behavior in some contexts." There is no single settled replacement for expected utility — only a family of competing patches, each capturing part of the picture.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §3.4. Original: Allais (1953).*
