---
title: "The Vickrey-Clarke-Groves Mechanism"
source: "Osborne & Rubinstein (2020), §17.3 (beyond-lectures)"
status: enriched
tags:
  - beyond-lectures
  - mechanism-design
  - vcg-mechanism
  - strategy-proofness
prerequisites:
  - mechanism-design-and-matching/public-project-problem-and-strategy-proofness
---
## Adding penalties to the summing-reports rule

[The summing-reports mechanism](public-project-problem-and-strategy-proofness.md) uses the right decision rule — execute the project iff $\sum_j x_j>0$ — but fails to be strategy-proof because reports are unconstrained. The **Vickrey-Clarke-Groves (VCG) mechanism** keeps that decision rule and adds transfers designed specifically to remove the incentive to misreport.

The transfers are built around **pivotality**. Individual $i$'s report is pivotal (in the execution-inducing direction) if the project *is* executed given all reports, but *would not be* absent $i$'s report — i.e. $\sum_j x_j>0$ but $\sum_{j\neq i}x_j\leq0$. In that case $i$ pays a penalty equal to the sum of the others' reports: she is charged for single-handedly flipping the outcome from non-execution to execution. Symmetrically, if $i$'s report is pivotal in the *blocking* direction ($\sum_j x_j\leq0$ but $\sum_{j\neq i}x_j>0$), she pays the negative of the others' sum — a penalty for single-handedly blocking a project the rest of the community favored. An individual whose report is not pivotal in either sense pays nothing. All transfers are nonpositive: nobody ever *receives* money from the mechanism, only pays or breaks even.

**Definition 17.5 (VCG mechanism).** $\delta(x_1,\dots,x_n)=1 \iff \sum_{j\in N}x_j>0$, and
$$\tau_i(x_1,\dots,x_n)=\begin{cases}\displaystyle\sum_{j\in N\setminus\{i\}}x_j & \text{if }\displaystyle\sum_{j\in N\setminus\{i\}}x_j\leq0 \text{ and }\sum_{j\in N}x_j>0\\[1.5ex] \displaystyle-\sum_{j\in N\setminus\{i\}}x_j & \text{if }\displaystyle\sum_{j\in N\setminus\{i\}}x_j>0 \text{ and }\sum_{j\in N}x_j\leq0\\[1ex] 0 & \text{otherwise.}\end{cases}$$

**Example 17.3.** For $n=5$, the mechanism gives:

| $x_1$ | $x_2$ | $x_3$ | $x_4$ | $x_5$ | $\delta$ | $\tau_1$ | $\tau_2$ | $\tau_3$ | $\tau_4$ | $\tau_5$ |
|---|---|---|---|---|---|---|---|---|---|---|
| 5 | −1 | −1 | −1 | −1 | 1 | −4 | 0 | 0 | 0 | 0 |
| −5 | 1 | 1 | 1 | 1 | 0 | −4 | 0 | 0 | 0 | 0 |
| −7 | 1 | 1 | 3 | 4 | 1 | 0 | 0 | 0 | −1 | −2 |
| −5 | 2 | 2 | 2 | 2 | 1 | 0 | 0 | 0 | 0 | 0 |

In row 1, individual 1's report of $5$ single-handedly flips a would-be-blocked project ($\sum_{j\neq1}x_j=-4\leq0$) into an executed one, so she pays the penalty $-4$. In row 3, individuals 4 and 5 are each pivotal in blocking direction relative to the others and pay accordingly, while 2 and 3 are not pivotal at all and pay nothing even though the project passes.

## Strategy-proofness

**Proposition 17.1.** For any public project problem, the VCG mechanism is strategy-proof.

*Proof idea.* Fix individual $i$ with $v_i>0$ and let $S=\sum_{j\neq i}x_j$ be the sum of the other reports. Three cases exhaust the possibilities, and in each, reporting $v_i$ is (weakly) optimal:
- If $S>0$: reporting $v_i$ (or any positive number) executes the project with zero transfer, giving utility $v_i$ — the best possible, since $i$ cannot do better than getting the project for free.
- If $-v_i<S\leq0$: reporting $v_i$ (or anything $>-S$) executes the project with transfer $S$, giving utility $S+v_i>0$; reporting $\leq-S$ instead blocks the project for utility $0<S+v_i$ — worse.
- If $S\leq-v_i\leq0$: reporting $v_i$ (or anything $\leq-S$) blocks the project for utility $0$; reporting $>-S$ instead executes it with transfer $S$, giving utility $v_i+S\leq0$ — no better.

In every case, $i$'s payoff from reporting $v_i$ weakly beats every alternative report, for every possible $S$ (hence for every possible profile of others' reports). A symmetric case analysis handles $v_i\leq0$. $\blacksquare$

The key structural trick is that $i$'s transfer, whenever it is nonzero, is **frozen at $S$** — a quantity $i$'s own report cannot influence — so the only thing her report controls is *whether* the pivotal penalty is triggered at all, and truthful reporting triggers it exactly when triggering it is in her own interest.

## Why VCG's appeal is still limited

The mechanism is strategy-proof using nothing more exotic than pivotality, but four features temper its practical attractiveness:

1. **Payments without execution.** An individual can be charged even when the project is *not* carried out — e.g. valuation profile $(-5,1,1,1,1)$ blocks the project yet individual 1 still pays $4$, which many people would find hard to accept as legitimate.
2. **Opacity.** Unlike majority rule, it takes real work to see *why* truthful reporting is optimal regardless of others' reports — the incentive argument is not transparent to a lay participant.
3. **No budget balance, and returning the surplus breaks strategy-proofness.** Collected payments are not returned to the individuals; if they are redistributed (e.g. split equally), truthful reporting can stop being optimal. With two individuals, $v_1=1$ and individual 2 reporting $10$: reporting truthfully gives individual 1 utility $1$, but reporting $-8$ still executes the project (since individual 2's report alone makes the sum positive) while individual 2 now pays $8$, half of which — $4$ — returns to individual 1, for a total utility of $5>1$. It can be shown more generally that **no strategy-proof mechanism with this same execute-iff-sum-positive decision rule can be budget-balanced** (transfers summing to zero for every profile).
4. **Insensitivity to wealth.** Since the criterion only looks at the *sign* of the valuation sum, two wealthy individuals who each benefit slightly (valuation $100$ apiece) can force through a project that hurts $99$ impoverished individuals significantly (valuation $-1$ apiece) — and the VCG transfers do not even require the wealthy beneficiaries to pay anything, since neither is pivotal.

## Connection to the second-price auction

The same strategy-proofness idea, specialized to selling a single good to the highest-valuation individual rather than deciding a binary public project, reproduces exactly the [second-price (Vickrey) auction](../game-theory-basics/economic-applications-of-nash-equilibrium.md): the winner is whoever reports the highest number, and she pays the highest *other* report. This is precisely the "truthfulness is dominant" result asserted (but not proved from mechanism-design first principles) in that entry — the VCG framework here supplies the general argument of which second-price bidding is a special case.

*Source: Osborne & Rubinstein (2020), Models in Microeconomic Theory, §17.3.*
