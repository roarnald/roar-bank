---
title: Cascading Failure Prevention — Bulkhead + Circuit Breaker Proposal (Approved)
date: 2025-09-17
role: Solutions Architect
organization: Merquri Pte Ltd
project: National Lottery Platform (LottoMatik)
leadership_types:
  - technical
  - stakeholder
skills:
  - Solution Architecture
  - System Reliability
  - Distributed Systems
  - Incident Response
  - Stakeholder Communication
impact: very_high
source_documents:
  - raw/appraisals/2025.md
  - raw/solution-proposals/Cascading Failure - Solution Proposal-1.pdf
---

# Context

On 9 September 2025, the NL system experienced incident NLINCIDENT-261: a full system outage that disrupted all business operations. Admin Backoffice was unable to query data and the Agent Application could not process ticket purchases. All endpoints were unresponsive.

# Problem

Root cause investigation revealed:
- Internal DFNN staff were running bots to mass-query report data, generating a burst of long-running database queries.
- These queries exhausted all connections in the HikariCP database connection pool.
- When no connections were available, Spring threw `CannotGetJdbcConnectionException` — causing a cascading failure that took the entire system offline.
- The hotfix (adding an index on `bet_group_id`) mitigated one specific endpoint but left the architectural risk wide open for any future burst.

# Actions

- Conducted deep-dive root cause investigation.
- Prepared "Cascading Failure Solution Proposal" (12 September 2025); **approved by Kar Wai Cheng on 17 September 2025**.
- Proposed two complementary solutions:

**Solution 1 — Bulkhead Pattern (Connection Pool):**
- Option A: Dedicated HikariCP connection pools per service group — prevents a single function's failure from exhausting all connections.
- Option B: Reserved connection logic via application code guard — limits long-running report queries to at most 50% of available connections.

**Solution 2 — Circuit Breaker Pattern (resilience4j):**
- Implements fail-fast methodology using a finite state machine (CLOSED → OPEN → HALF_OPEN).
- Recommended: Time-based sliding window with slow call rate threshold — ideal for endpoint health measured by query duration, not just error rate.
- When report endpoints become slow (long DB queries), circuit opens → 429 Too Many Requests → system can self-recover.

- Also separately proposed **Bot Prevention** measures (23 September 2025) as the upstream human-behaviour root cause.

# Impact

- Proposal approved at architecture level.
- Addresses a system-wide single point of failure that had already caused a real production outage.
- Pattern also subsequently applied in Right-Sizing Microservices proposal (March 2026).

# Evidence

- Solution Proposal: "Cascading Failure Solution Proposal" (Prepared 12 Sep 2025, Approved 17 Sep 2025 by Kar Wai Cheng)
- 2025 Appraisal — Cascading Failure Prevention section
- Related: NLINCIDENT-261

# Related Projects

- [[National Lottery Platform]]

# Related Skills

- [[Solution Architecture]]
- [[Distributed Systems]]
- [[System Reliability]]
- [[Incident Response]]
