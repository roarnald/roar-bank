---
title: Right-Sizing Microservices — Proposed Bulkhead for Kubernetes Pods (Approved)
date: 2026-03-17
role: Solutions Architect
organization: Merquri Pte Ltd
project: National Lottery Platform (LottoMatik)
leadership_types:
  - technical
  - stakeholder
skills:
  - Solution Architecture
  - Kubernetes
  - Distributed Systems
  - System Reliability
  - Incident Response
impact: very_high
source_documents:
  - raw/solution-proposals/Right-Sizing Microservices - Solution Proposal-1.pdf
---

# Context

In March 2026, multiple incidents occurred where lottery draw operations were incomplete due to application pods restarting between critical steps. Database rollbacks were required to fix state. Investigation revealed CPU/memory spikes aligned with the blockchain retry cron job — a backlog of 300,000 failed blockchain transactions was overwhelming the shared application pods.

# Problem

A Kafka queue had been set up to throttle blockchain API calls to Kaleido (private blockchain provider). As the customer base grew, this retry mechanism's backlog grew to 300,000 failed transactions. The retry load shared the same application pods as all other operations — ticket purchasing, draw operations, and backoffice. This created a critical shared resource choke point.

# Actions

- Conducted root cause investigation.
- Immediate hotfix: increased HPA configuration (insufficient at 300k backlog).
- **Proposed batched API requests**: chunked Kaleido requests to max 10,000 per batch — prevented their fail-first mechanism, reduced pod CPU spikes. Deployed to production 11 March 2026 and confirmed stable.
- Prepared "Right-Sizing Microservices" Solution Proposal (17 March 2026); **approved by Kar Wai Cheng on 24 March 2026**.
- Proposed a 3-phase roadmap:

**Phase 1**: Batching Requests (already deployed, working)

**Phase 2**: Bulkhead Pattern for Application Pods:
  - Split into 3 dedicated pod groups:
    1. Current Main Application — customer-facing (bet placement)
    2. Backoffice Operations — draw operations, jackpot configuration
    3. Blockchain Retry Operations — blockchain transaction commits
  - Each group isolated: failure in one cannot cascade to others.

**Phase 3**: Clean Up and Maximum Utilization:
  - Code-split and segregate functions across dedicated pods.
  - Enable 24/7 blockchain retry (vs. current 5-minute cron interval).
  - Dramatically improve system scalability.

# Impact

- Batching (Phase 1): deployed, confirmed stable — server restarts significantly reduced.
- Phase 2 architecture: approved, ready for implementation.
- Extends the Bulkhead pattern from database connection pools (Sep 2025) to Kubernetes pod orchestration — consistent architectural philosophy.
- Prevents draw operations (mission-critical) from being affected by blockchain retry load.

# Evidence

- Solution Proposal: "Right-Sizing Microservices Solution Proposal" (Prepared 17 Mar 2026, Approved 24 Mar 2026 by Kar Wai Cheng)
- Related: Cascading Failure Prevention proposal (Sep 2025) — Bulkhead pattern precedent

# Related Projects

- [[National Lottery Platform]]

# Related Skills

- [[Solution Architecture]]
- [[Kubernetes DevOps]]
- [[Distributed Systems]]
- [[Distributed Systems]]
