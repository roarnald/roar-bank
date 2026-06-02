# Distributed Systems

## Definition
Designing and troubleshooting systems that operate across multiple services, nodes, or processes — including microservices, message queues, connection pooling, and resilience patterns.

## Key Demonstrations

### Resilience Patterns Applied
- **Bulkhead Pattern**: First applied to database connection pools (HikariCP) in the NL system cascading failure proposal (Sep 2025). Later extended to Kubernetes pod orchestration in Right-Sizing Microservices proposal (Mar 2026). [[2025-09-cascading-failure-proposal]] [[2026-03-right-sizing-microservices]]
- **Circuit Breaker Pattern**: Proposed resilience4j-based circuit breaking for NL report endpoints with time-based sliding window and slow call rate threshold. [[2025-09-cascading-failure-proposal]]
- **Request Batching**: Throttled blockchain retry requests (Kaleido) into batches of 10,000 — prevented pod exhaustion from 300k failed transaction backlog. Deployed March 2026, confirmed stable. [[2026-03-right-sizing-microservices]]

### Message Queues
- **Kafka**: Used in NL system for blockchain transaction throttling to Kaleido.
- **BullMQ**: Designed as database write queue for community chat application to throttle message persistence. [[2026-01-community-chat-architecture]]
- **Valkey Streams (Redis Pub/Sub)**: Designed as core of community chat message routing — offloads heavy lifting from NodeJS.

### Caching
- **Redis**: Implemented inter-pod caching for New138 fullstack application (2024). [[2024-01-fullstack-new138-solo]]
- **Valkey Elasticache**: Designed as distributed cache layer for community chat (2026). [[2026-01-community-chat-architecture]]

### Service Design
- Designed 3-pod isolation architecture for NL: customer-facing, backoffice operations, blockchain retry — each with dedicated resources. [[2026-03-right-sizing-microservices]]
- Identified single-point-of-failure risk in shared HikariCP connection pool during post-incident analysis (Sep 2025).

### Incident Investigation
- Root cause analysis of NLINCIDENT-261 (Sep 2025): traced full cascade from bot activity → long-running queries → connection pool exhaustion → `CannotGetJdbcConnectionException` → total system outage.
- Root cause analysis of pod restart incidents (Mar 2026): correlated Prometheus metrics spikes to Kafka cron job firing pattern.

## Related Projects
- [[National Lottery Platform]]
- [[New138 Fullstack Application]]
- [[Community Chat Application]]

## Related Skills
- [[Solution Architecture]]
- [[Performance Engineering]]
- [[Kubernetes DevOps]]
