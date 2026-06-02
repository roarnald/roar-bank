---
title: Community Chat Application — Architecture Proposal (NodeJS + Valkey Streams)
date: 2026-01-19
role: Solutions Architect
organization: Merquri Pte Ltd
project: Community Chat Application
leadership_types:
  - technical
  - stakeholder
skills:
  - Solution Architecture
  - Node.js
  - Valkey (Redis)
  - WebSockets
  - PostgreSQL
  - AWS
  - Kubernetes
  - Distributed Systems
impact: medium
source_documents:
  - raw/solution-proposals/Community Chat Application - Solution Proposal.pdf
---

# Context

In January 2026, a community chat application was requested. The application's purpose: allow community leaders to manage group communications, control information flow, and reduce reliance on the System Administrator — targeting approximately 1,000 users.

# Problem

- Business team proposed open-source chat frameworks (e.g., OpenIM) that use Golang/Rust, technologies outside the team's capability stack.
- These frameworks are designed for millions of concurrent users — overengineered for 1,000 users — and carry high operational risk since the team cannot debug or modify them.
- Tencent RTC was evaluated but rejected: required direct client-to-server connections, allowing peer-to-peer messaging which was specifically forbidden by business requirements.
- Required unique features: no peer-to-peer chat, configurable message deletion times per community, blocking repeated rejected join requests — not available in off-the-shelf solutions.

# Actions

- Prepared Project Inception Solution Proposal (19 January 2026).
- Evaluated three solution paths:
  - **Solution 1**: Open-source frameworks (OpenIM, etc.) — rejected (language mismatch, overengineered)
  - **Solution 2a**: NodeJS — viable but max throughput ~1,000–5,000 users (too close for comfort at 1,000 target)
  - **Solution 2b**: **NodeJS + Valkey Streams + BullMQ Database Queue** — recommended
- Designed a full AWS-based architecture for Solution 2b:
  - CloudFlare + CloudFront CDN
  - EKS with auto-scaling application pods
  - Application Load Balancer
  - Valkey Elasticache for Pub/Sub and stream-based message routing
  - BullMQ queue to throttle database writes
  - RDS PostgreSQL for persistence
  - Vault for secrets management
  - App Push Notification Service (external managed)
- Estimated throughput with Valkey offloading: **up to 100,000 active users** — 100x headroom over target.
- Evaluated and documented Bun runtime (dropped: library compatibility risks) and Tencent RTC (dropped: P2P security issue).

# Impact

- Provided a clear, cost-effective, and team-maintainable architecture for a chat product.
- Solution leverages familiar technologies (NodeJS, PostgreSQL), reducing operational risk.
- Architecture headroom of 100x provides long-term scalability without rearchitecting.
- Demonstrates cross-domain SA capability: messaging systems, real-time infrastructure, AWS architecture.

# Evidence

- Solution Proposal: "Community Chat Application Solution Proposal" (19 January 2026)

# Related Projects

- [[Community Chat Application]]
- [[National Lottery Platform]]

# Related Skills

- [[Solution Architecture]]
- [[Distributed Systems]]
- [[NodeJS Fullstack]]
