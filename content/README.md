# Microeconomica — An Introduction to Microeconomics Knowledge Vault

A structured, cross-linked Markdown vault covering individual decision theory and consumer theory, built the same way as the [Econometrica](../Econometrica/) vault: one atomic concept per entry, YAML frontmatter, relative Markdown links (portable, Obsidian-readable, publishable via [Quartz](https://quartz.jzhao.xyz/) later without rewriting content).

## Format

Every entry is a single Markdown file inside a topic folder, with YAML frontmatter:

```yaml
---
title: Entry Title
source: "Osborne & Rubinstein (2020), §X.X" | "Lecture N"
status: stub | drafted | enriched
tags: [tag1, tag2]
prerequisites: [folder/other-entry]
---
```

See [`_template.md`](_template.md) for the full skeleton. Cross-links use relative Markdown links (e.g. from within `consumer-theory/`, `[the utility representation theorem](../preferences-and-choice/utility-representation-theorem.md)`), not wikilinks.

Entries covering material **neither the lectures nor the TDs actually taught** — written directly from the textbook to round the vault out into a fuller reference — carry a `beyond-lectures` tag, the same convention used in Econometrica's Part III.

`status` tracks how far an entry has come: **stub** (skeleton only), **drafted** (full prose, not yet cross-checked), **enriched** (reworked against the textbook with worked examples and proofs).

## Sources

- **Course-derived entries** (`preferences-and-choice/`, `consumer-theory/`, `choice-under-uncertainty/`): Introduction to Microeconomics, M1 Economics & Psychology (Paris School of Economics / Université Paris 1 Panthéon-Sorbonne), Lectures 1, 2, 4, 5 and TD1–TD4, cross-checked against the main textbook.
- **Main textbook**: Martin J. Osborne & Ariel Rubinstein, *Models in Microeconomic Theory* (Open Book Publishers, 2020), "she" edition, version 2020.3.26. Freely available under CC BY-NC-ND 4.0 at [doi.org/10.11647/OBP.0211](https://doi.org/10.11647/OBP.0211).
- **Reference textbook** (mentioned in lecture but not yet drawn on directly): Hal R. Varian, *Intermediate Microeconomics*.

## Topic map & reading order

### Part I — The course (Ch.1–5 of the textbook)
1. [`preferences-and-choice/`](preferences-and-choice/00-overview.md) — binary relations, the utility representation theorem, choice functions and rationalizability, property α, satisficing, behavioral violations *(Ch.1–2)*
2. [`consumer-theory/`](consumer-theory/00-overview.md) — bundles, monotonicity/convexity/continuity, MRS, budget sets, the consumer's problem, WARP, properties of demand *(Ch.4–5)*
3. [`choice-under-uncertainty/`](choice-under-uncertainty/00-overview.md) — lotteries, continuity & independence, the expected utility theorem, the Allais paradox, risk aversion *(Ch.3)*

### Part II — Extensions beyond the course (`beyond-lectures`)
Not part of the actual course — added directly from the textbook to cover the rest of *Models in Microeconomic Theory*.
4. [`producer-theory/`](producer-theory/00-overview.md) — the producer, output/profit maximization, cost functions *(Ch.6)*
5. [`monopoly/`](monopoly/00-overview.md) — uniform-price and discriminatory monopoly *(Ch.7)*
6. [`equilibrium-foundations/`](equilibrium-foundations/00-overview.md) — the jungle, the market *(Ch.8–9)*
7. [`exchange-economies/`](exchange-economies/00-overview.md) — competitive equilibrium, the core, Edgeworth box, production economies, asymmetric information *(Ch.10–14)*
8. [`game-theory-basics/`](game-theory-basics/00-overview.md) — strategic games, Nash equilibrium, extensive games, backward induction, bargaining *(Ch.15–16)*
9. [`mechanism-design-and-matching/`](mechanism-design-and-matching/00-overview.md) — the VCG mechanism, stable matching, the Gale-Shapley algorithm *(Ch.17–18)*
10. [`social-choice/`](social-choice/00-overview.md) — socialism as an economic system, Arrow's impossibility theorem, Gibbard-Satterthwaite *(Ch.19–20)*

### Reference
- [`pages/sources.md`](pages/sources.md) — bibliography
- [`pages/glossary.md`](pages/glossary.md) — concept/theorem name → entry link
- [`pages/status.md`](pages/status.md) — progress dashboard

### TD tutorials (password-protected, TA-only)
- [`td-tutorials/`](td-tutorials/00-overview.md) — tutorial sheets (TD1–TD4), the methodology handout, and teaching-session guidance, with full solutions and private teaching notes. This is the TA's own working copy, not public reference material — on the published site it sits behind a separate password gate from everything else above.

## Status

- [x] Part I — course-derived content (Ch.1–5): **20 entries, all enriched**
- [x] Part II — beyond-lectures extensions (Ch.6–20): **all 7 folders done**

See [`pages/status.md`](pages/status.md) for the folder-by-folder breakdown.

## Deferred (planned for a later session)

- Add the course's TD tutorial exercises and solutions to the vault, plus notes on how to run/teach a tutorial session. Kept out for now since this vault is study/reference-focused and the theory content (Part I + Part II) comes first.
