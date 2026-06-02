---
title: Community Chat Application
start_date: 2026-01
end_date: in-progress
role: Solutions Architect / Fullstack Team Lead
organization: Merquri Pte Ltd
technologies:
  - NestJS
  - Node.js
  - TypeScript
  - Valkey (Redis fork)
  - BullMQ
  - WebSockets
  - PostgreSQL
  - AWS EKS
  - AWS S3
  - Vault
stakeholders:
  - Project Manager
  - Kar Wai Cheng (Architecture)
  - Business Team
  - Fullstack JS Engineering Team
---

# Summary

A community chat application designed to empower community leaders to manage and disseminate information within groups, reducing reliance on a central System Administrator. Target scale: ~1,000 users, designed for up to 100,000.

# Architecture

Ronald's recommended architecture (Solution 2b):
- **NodeJS** application server handling WebSocket connections and API layer
- **Valkey (Redis fork)** Pub/Sub and Valkey Streams for real-time message routing — offloads heavy lifting from NodeJS
- **BullMQ** as a database write queue to throttle message persistence in batches
- **PostgreSQL (RDS)** for persistent message storage
- **AWS EKS** with auto-scaling application pods
- **AWS CloudFront + CloudFlare** for CDN
- Estimated capacity: 100,000 active users (100x headroom over target)

Alternatives evaluated and dropped:
- **OpenIM** (open-source framework): Uses Golang/Rust — outside team capabilities; overengineered for 1,000 users
- **Tencent RTC**: Requires direct client-to-Tencent connection — allows peer-to-peer messaging, a hard requirement violation
- **Bun runtime**: Library compatibility risks; dropped despite 3-5x performance advantage

# Business Problem

Community leaders needed a way to group members into communities, control information dissemination, and reduce administrator overhead. Existing generic chat frameworks (Discord-style) didn't support unique requirements: no P2P chat, configurable message deletion per community, blocked repeated join requests.

# Outcomes

- Solution Proposal submitted January 2026; architecture approved.
- **NestJS backend built** — module structure, controller/service patterns, DI, guard configuration, WebSocket integration, Valkey Pub/Sub wiring, BullMQ queue, DB schema.
- **Fullstack JS team created and operational** — first dedicated fullstack JS team at Merquri.
- **Multi-Agent Audit workflow** developed and applied — AI agents used in coordinated sequence to audit architectural changes across multiple quality dimensions (correctness, security, scalability, pattern adherence) before production merge.
- Complex architectural changes delivered to production-grade standard.

# Related Achievements

- [[2026-01-community-chat-architecture]]
- [[2026-02-community-chat-nestjs-team-lead]]

# Lessons Learned

- Matching architecture to actual scale requirements matters — OpenIM is built for millions; overkill for 1,000 users adds operational risk without benefit.
- Valkey/Redis Streams enable a 20x+ throughput increase over basic NodeJS for real-time messaging at marginal cost.
