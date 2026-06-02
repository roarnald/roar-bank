# Solution Proposals — Index

All formal solution proposals authored by Ronald Thian as Solutions Architect.

---

## Approved Proposals

| Title | Date | Approved By | Status |
|-------|------|-------------|--------|
| Cascading Failure Prevention (Bulkhead + Circuit Breaker) | 12 Sep 2025 | Kar Wai Cheng (17 Sep 2025) | Approved |
| Right-Sizing Microservices (Bulkhead for Application Pods) | 17 Mar 2026 | Kar Wai Cheng (24 Mar 2026) | Approved; Phase 1 deployed |

## Proposed / In Review

| Title | Date | Status |
|-------|------|--------|
| Ticket Security — Digital Signature | 21 Apr 2025 | Proposed; verified with Kar Wai, Seng Kai, Jazz |
| Bot Prevention — Hash Comparison | 23 Sep 2025 | Proposed |
| Data Watermarking | 4 Aug 2025 | Proposed |
| Community Chat Application (NodeJS + Valkey) | 19 Jan 2026 | Proposed |
| API Monetisation (Apigee / AWS Marketplace) | 2025 | Pending business requirement |

## Source Documents
- [[2025-09-cascading-failure-proposal]]
- [[2025-09-bot-prevention-proposal]]
- [[2025-04-ticket-security-digital-signature]]
- [[2026-01-community-chat-architecture]]
- [[2026-03-right-sizing-microservices]]

---

## Architecture Patterns Referenced

### Bulkhead Pattern
Applied at two levels:
1. **Database Connection Pool** (Sep 2025): Dedicated HikariCP pools per service group → prevents connection exhaustion from cascading
2. **Kubernetes Application Pods** (Mar 2026): Dedicated pod groups per function → isolates draw operations from blockchain retry load

### Circuit Breaker (resilience4j)
- Time-based sliding window with slow call rate threshold
- Fail-fast for long-running database queries
- Self-healing: CLOSED → OPEN → HALF_OPEN state machine

### Bulkhead + Circuit Breaker Together
- Bulkhead: isolates failure blast radius
- Circuit Breaker: fails fast before pool exhaustion occurs
- Recommended as complementary pair for NL system

### Hash Comparison (Bot Prevention)
- Session-bound MD5 hash (userId + user-agent + loginTime + ...)
- Server independently computes and compares
- Similar to digital certificate verification without asymmetric keys

### Digital Signature (Ticket Security)
- SHA-256 hash of ticket payload
- Encrypted with server's RSA private key → Signature
- POS decrypts with public key → compare with stored hash
- Fake tickets definitively identified (only server can generate valid Signature)

### NodeJS + Valkey Streams (Chat Architecture)
- NodeJS handles API and WebSocket connections
- Valkey Pub/Sub and Streams handle message routing (offloads NodeJS)
- BullMQ throttles database writes
- Estimated capacity: 100,000 active users vs 1,000 target
