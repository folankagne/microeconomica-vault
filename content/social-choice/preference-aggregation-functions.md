---
title: "Preference Aggregation Functions"
source: "Osborne & Rubinstein (2020), §§20.1–20.2 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - social-choice
  - voting
  - condorcet-paradox
prerequisites:
  - preferences-and-choice/binary-relations-and-preference-relations
---
## Why majority rule alone isn't enough

The most natural way to aggregate individual preferences over more than two alternatives — pairwise majority rule ("society prefers $a$ to $b$ iff a majority of individuals do") — need not produce a transitive social preference. The **Condorcet paradox**: with three individuals and alternatives $a,b,c$ ranked $a\succ b\succ c$, $b\succ c\succ a$, $c\succ a\succ b$ respectively, a majority (individuals 1,3) prefers $a$ to $b$, a majority (1,2) prefers $b$ to $c$, and a majority (2,3) prefers $c$ to $a$ — a cycle $a\succ b\succ c\succ a$, violating transitivity of [the preference relation](../preferences-and-choice/binary-relations-and-preference-relations.md) itself. This single example is the reason the chapter needs a richer object than "just take majority rule."

## The formal object

**Definition (society, Ch.20 sense).** A society is a finite set of individuals $N$ and a finite set of alternatives $X$.

**Definition (preference aggregation function, PAF).** A PAF for $\langle N,X\rangle$ assigns a **social preference relation** over $X$ to every profile of *strict* individual preference relations over $X$ — the domain is *all* possible strict preference profiles (a substantive assumption, revisited in [Arrow's theorem](arrows-impossibility-theorem.md)'s discussion of restricted domains), and the output relation need not itself be strict.

## Five examples spanning the space of PAFs

1. **Counting votes.** Each individual "votes" for her top alternative; alternatives are ranked by vote totals (any non-favorite alternative is tied for last).
2. **Scoring rules.** Fix a decreasing point schedule $p(1)\geq p(2)\geq\cdots$; each alternative earns $p(k)$ points from an individual who ranks it $k$-th, alternatives are ranked by total points summed across individuals. Counting votes is the special case $p(1)=1$, $p(k)=0$ for $k\geq2$; the Eurovision Song Contest's points system is another instance.
3. **Pairwise contests.** Each pair of alternatives is a head-to-head majority "contest"; an alternative earns 1 point per contest won and $\tfrac12$ per tie, ranked by total points.
4. **External preferences.** The social ranking is a *fixed* preference relation $\succsim^*$, completely ignoring the individuals' reported preferences — included as a degenerate extreme case.
5. **Dictatorship.** The social ranking simply *is* one fixed individual $i^*$'s preference relation, regardless of everyone else's — the other degenerate extreme.

These five examples span the space the rest of the chapter axiomatizes: from "ignore individuals entirely" (external preferences) through genuinely aggregative rules (scoring, pairwise contests) to "listen to exactly one individual" (dictatorship) — with [Arrow's impossibility theorem](arrows-impossibility-theorem.md) about to show that, under two seemingly mild requirements, only the dictatorship extreme survives.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§20.1–20.2.*
