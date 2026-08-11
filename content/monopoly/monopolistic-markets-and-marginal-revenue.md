---
title: "Monopolistic Markets and Marginal Revenue"
source: "Osborne & Rubinstein (2020), §§7.1–7.2 intro (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - monopoly
  - marginal-revenue
prerequisites:
  - producer-theory/cost-functions
---
## From price-taker to price-setter

[Producer theory](../producer-theory/00-overview.md) assumed the producer's own choices don't move market prices — appropriate when she's small relative to the market. A **monopolist** is the opposite case: the *sole* supplier of a good, so her chosen output directly determines the price at which it clears.

**Definition — monopolistic market.** A market $\langle(q_i)_{i=1}^k, C, \succeq\rangle$ consists of: (i) demand functions $q_i:\mathbb{R}_+\to\mathbb{R}_+$, one per market **segment**, each decreasing in price; (ii) a monopolist with a continuous, convex cost function $C$ (with $C(0)=0$) and preferences over $((y_1,\dots,y_k),\pi)$ — output sold per segment and profit, the same generalized-objective structure [used for producers generally](../producer-theory/the-producer-and-production-functions.md).

**Definition — uniform-price market.** The monopolist must charge the *same* price across all segments — e.g. because price discrimination by an observable characteristic (like gender) is legally prohibited, or because **arbitrage** (buying cheap in one segment, reselling in another) undermines any attempt to charge different prices, a constraint that binds harder for easily-resold goods (books) than for services consumed on the spot (haircuts).

Writing total demand $Q(p)=\sum_i q_i(p)$ (decreasing, hence invertible — call the inverse $P$), the monopolist's problem of choosing a price is equivalent to choosing an output $y=Q(p)$ directly, with profit $\Pi(y)=P(y)y - C(y)$.

## Marginal revenue

**Definition.** For differentiable inverse demand $P$, marginal revenue at output $y$ is $\text{MR}(y) = [P(y)y]' = P(y) + P'(y)y$.

Since $P$ is decreasing, $\text{MR}(y) < P(y)$ always: selling one more unit adds roughly $P(y)$ in revenue from that unit, but *also* forces the price down on every other unit already being sold — the second term is exactly that cannibalization cost, and it's the entire reason a monopolist's incentives diverge from a price-taker's.

**A subtlety: MR need not be monotone**, even though $P$ is decreasing — a fact that doesn't follow automatically from the model's assumptions and needs its own example to establish. With an indivisible good and three consumers willing to pay at most \$10, \$6, and \$5 respectively: $P(1)=10$, $P(2)=6$, $P(3)=5$, so total revenue is $10, 12, 15$ at $y=1,2,3$ — giving $\text{MR}(1)=10$, $\text{MR}(2)=2$, $\text{MR}(3)=3$. Marginal revenue **falls then rises** ($\text{MR}(3)>\text{MR}(2)$), even though the price schedule itself is monotonically falling. The lesson: "MR is decreasing" is a common *additional* simplifying assumption in applied work, not a theorem that follows from decreasing demand alone.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §§7.1–7.2.*
