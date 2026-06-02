# Solution Architecture

## Definition
Evaluating system-wide risks, designing scalable and resilient architectures, translating business requirements into technical solutions, and communicating recommendations to engineering and business stakeholders.

## Key Demonstrations

### System Design & Proposals
All proposals below were prepared as formal Solution Proposal documents:

| Proposal | Date | Status |
|----------|------|--------|
| Bot Prevention (Hash Comparison) | Sep 2025 | Proposed |
| Cascading Failure Prevention (Bulkhead + Circuit Breaker) | Sep 2025 | Approved |
| Ticket Security / Digital Signature | Apr 2025 | Proposed |
| Data Watermarking | Aug 2025 | Proposed |
| API Monetisation (Apigee / AWS Marketplace) | 2025 | In progress |
| Community Chat Application (NodeJS + Valkey) | Jan 2026 | Proposed |
| Right-Sizing Microservices (Bulkhead for Pods) | Mar 2026 | Approved |

- [[2025-09-cascading-failure-proposal]]
- [[2025-09-bot-prevention-proposal]]
- [[2025-04-ticket-security-digital-signature]]
- [[2026-01-community-chat-architecture]]
- [[2026-03-right-sizing-microservices]]

### Architecture Patterns Applied
- **Bulkhead Pattern**: Connection pools (Sep 2025 proposal) → Kubernetes pod isolation (Mar 2026 proposal) — consistent application of the pattern across stack layers.
- **Circuit Breaker**: Resilience4j-based fail-fast for database-heavy endpoints.
- **Batching**: Throttled Kafka-to-blockchain requests to prevent pod exhaustion.
- **Digital Signatures / Asymmetric Cryptography**: Applied to lottery ticket authenticity.
- **Full-Stack SSR/SSG**: Astro JS + Node.js replacing hundreds of Elastic Beanstalk instances.
- **Redis Caching**: Distributed state across Kubernetes pods.

### Documentation & Governance
- **High Level Architecture Diagram** for NL platform — stakeholder communication artifact.
- **Incident Response Plan** with swim lane diagrams.
- **Abnormal Traffic Runbook**.
- **OWASP Security Checklist** (adapted for business context) — caught ~10 vulnerabilities before pen test. [[2025-10-security-checklist-owasp]]
- **Performance Test Plan** (Oct 2025) — designed test strategy, defined objectives, analysed results. [[2025-01-performance-testing-improvements]]

### Stakeholder Communication
- Presented solutions to CTO for approval.
- Received praise from DFNN (Philippine client) for MFA multi-device key proposal during Manila business trip.
- Works across hierarchy: developers, leads, PMs, Head of Architecture (Kar Wai), external clients.

## Related Projects
- [[National Lottery Platform]]
- [[New138 Fullstack Application]]
- [[Community Chat Application]]

## Related Skills
- [[Distributed Systems]]
- [[Security Engineering]]
- [[Stakeholder Management]]
- [[Performance Engineering]]
