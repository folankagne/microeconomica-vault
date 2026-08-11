---
title: "The Producer and the Production Function"
source: "Osborne & Rubinstein (2020), §6.1 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - producer-theory
  - production-function
prerequisites:
  - consumer-theory/the-consumers-problem
---
## A hook: the layoff decision

The textbook opens the chapter with a scenario rather than a definition: you're a VP deciding how many of 196 workers to keep, given a table where profit is *not* monotonic in headcount — it peaks at 100 workers retained (profit \$2M) and falls on either side (down to a \$8M *loss* at zero workers, and down to \$0.4M profit at full staffing). Laying off more than 96 workers is dominated (worse on both output *and* profit than laying off exactly 96), but among the sensible options — 0, 26, 52, or 96 layoffs — different objectives point to genuinely different answers. This is the running example for the whole chapter: which of several coherent objectives should "the producer" be modeled as pursuing?

## The producer, formally

While a consumer *trades* goods (redistributing what already exists), a **producer** *transforms* them — inputs (raw materials, but also information or attention) into outputs. The model here restricts to a single input and single output.

**Definition — production function.** $f:\mathbb{R}_+\to\mathbb{R}_+$ is a production function if it is continuous, nondecreasing, concave, satisfies $f(0)=0$, and its increments vanish in the limit: for any $\varepsilon>0$ there's a $y$ with $f(y+1)-f(y)<\varepsilon$.

Each condition has a direct interpretation: $f(0)=0$ (no input, no output), nondecreasing (more input never hurts), and — the substantive economic assumption — **concavity**, meaning each additional unit of input contributes *no more* than the previous one did: diminishing returns, built directly into the definition rather than assumed as an afterthought.

## The producer's environment: price-taking

The producer pays $w$ per unit of input, sells at $p$ per unit of output, and — in this chapter — is a **price-taker**: her own choices are assumed too small relative to the market to move $p$ or $w$. (This assumption is dropped in [the monopoly chapter](../monopoly/00-overview.md), where the producer's output decision *does* move the price she sells at.) Using $a$ units of input to produce $y=f(a)$ units of output yields profit $\pi = py - wa$.

## Four candidate objectives

The producer is modeled as having preferences over triples $(a,y,\pi)$ — not necessarily caring *only* about profit:

- **Output maximization**: maximize $y$ subject to $\pi\geq0$ — never operate at a loss, but otherwise produce as much as possible.
- **Profit maximization**: maximize $\pi$ outright, full stop.
- **Profit maximization with a floor**: maximize $\pi$ subject to $y\geq\bar y$ for some minimum acceptable output level — e.g. a firm with contractual delivery obligations.
- **A cooperative**: choose membership size $a$ (each member contributes one unit of labor) to maximize profit *per member*, $\pi/a$ — a genuinely different optimization target from any of the above, since it's a ratio, not a level.

The chapter develops the first two in full ([output maximization](output-vs-profit-maximization.md) and [profit maximization](output-vs-profit-maximization.md)); the latter two are flagged as coherent alternatives but not worked out in detail. The point of listing all four together is to make clear, before any results are proven, that "maximize profit" is a *choice* of assumption, not a logical necessity of what it means to be a producer — precisely the tension the opening layoff vignette is designed to surface.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §6.1.*
