---
title: NL Betting System Performance Testing — 60% Response Time & 75% Throughput Improvement
date: 2025-01-01
role: Solutions Architect
organization: Merquri Pte Ltd
project: National Lottery Platform (LottoMatik)
leadership_types:
  - technical
  - stakeholder
skills:
  - Performance Testing
  - Load Testing
  - JMeter
  - Kubernetes
  - AWS
  - Database Optimization
  - Solutions Architecture
  - System Design
impact: very_high
source_documents:
  - raw/appraisals/2025.md
  - raw/solution-proposals/MQ PNL Performance Test Plan - Oct 2025-1.pdf
---

# Context

The National Lottery (NL) / LottoMatik betting system needed performance validation before scaling to support larger user volumes. An earlier performance test (May 2025) had established a baseline. Ronald, as Solutions Architect, designed and executed a comprehensive follow-up performance test plan in October 2025.

# Problem

After the first round of testing, the system had several identified bottlenecks:
- Multiple pre-call APIs required per bet (adding network overhead)
- Inefficient database queries (no proper indexing)
- Excessive validation conditions
- System throughput was insufficient for projected load (<2000 bets/sec)
- Horizontal Pod Autoscaling (HPA) configuration was unverified

# Actions

- **Designed the Performance Test Plan** (prepared as Solutions Architect, vetted by PM Dominic Tan) covering objectives, test setup, strategy, and multiple test permutations.
- Defined quantitative objectives: 10,000 simultaneous transactions, ≤3s response time, blockchain commit verification, system stability.
- Directed optimisation implementation:
  - **Merged pre-call APIs**: folded GET /partner/lottery/bet/betslip/seq and GET /partner/lottery/nextDraw into the final /placeBet endpoint — reducing 4 API calls per bet to 1 (75% API call reduction).
  - Removed validation previously needed for previous results.
  - **Added database indexing** on draw date filter for more efficient querying.
- Designed test strategy using JMeter with ramp-up-and-hold methodology (Version 2).
- Configured isolated production-mirroring test environment on AWS (RDS db.large, Kubernetes HPA min 2/max 4).
- Ran multiple test case permutations from 100 TPS to 10,000 TPS burst.
- **Guided developers** to verify and correctly configure Horizontal Pod Autoscaling (HPA).

# Impact

- **Response time improved by 20–60%** across all test permutations.
- **Throughput increased from ~2,000 bets/sec to 3,500+ bets/sec** (75%+ improvement).
- Failed transaction rate dropped significantly (HR-A-003: from 23.05% → 0%; HR-A-002: from 0.26% → 0%).
- HPA verified to scale correctly under load.
- Total of 150,879 bets processed in a 24-minute ramp test (BR-V2-001).
- Established a scalable, evidence-based performance baseline for production planning.

# Evidence

- Raw document: MQ PNL Performance Test Plan - Oct 2025 (full test plan with results)
- 2025 Appraisal — Performance Testing section
- Test results documented: median response times, 90/95/99 percentiles, TPS, failure rates across 9 test cases (BR-V2-001, BR-001, BR-002, HR-A-001 through HR-A-006, ST-001)

# Related Projects

- [[National Lottery Platform]]

# Related Skills

- [[Solution Architecture]]
- [[Performance Engineering]]
- [[Kubernetes DevOps]]
- [[Stakeholder Management]]
