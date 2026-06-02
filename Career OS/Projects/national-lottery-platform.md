---
title: National Lottery Platform (LottoMatik / NL)
start_date: 2025-03
end_date: present
role: Solutions Architect (Concurrent with Software Architect)
organization: Merquri Pte Ltd
technologies:
  - Java / Spring Boot (backend)
  - HikariCP (connection pool)
  - Kafka
  - Kubernetes (EKS)
  - AWS RDS
  - Prometheus / Grafana
  - JMeter
  - Kaleido (private blockchain)
  - React (frontend backoffice)
stakeholders:
  - Kar Wai Cheng (Head of Architecture / Ronald's SA superior)
  - Dominic Tan (Project Manager)
  - DFNN (Philippines client)
  - GOT (overseas team)
  - Backend and DevOps engineers
---

# Summary

The National Lottery (NL) platform — referred to as LottoMatik — is a Philippines national lottery system with blockchain integration (Kaleido). Ronald was appointed as interim Solutions Architect from March 2025, holding this concurrently with his Software Architect role. This is a mission-critical system handling bet placement, draw operations, blockchain transaction commits, and agent management.

# Architecture

- Microservice architecture with separate application pods on Kubernetes (EKS)
- HikariCP database connection pooling (discovered as single point of failure)
- Kafka queue for throttling blockchain API requests to Kaleido
- AWS RDS for database; S3 for failed transaction storage
- Horizontal Pod Autoscaling (HPA) configured and validated through load testing
- Blockchain integration: Kaleido private blockchain for bet immutability
- Multiple game types: 2D, 3D, 4D, 6D, Lotto 6/42, Mega Lotto 6/45, Super Lotto 6/49, Grand Lotto 6/55, Ultra Lotto 6/58

# Business Problem

A government-certified national lottery system requiring high reliability, security, and scalability. The system processes thousands of bets per minute and must guarantee data integrity on blockchain.

# Outcomes

- **Performance**: 60% response time improvement, throughput from <2000 to 3500+ bets/sec (Oct 2025 performance test)
- **Security**: Digital Signature proposal, Bot Prevention, OWASP security checklist (~10 vulnerabilities caught)
- **Reliability**: Cascading Failure Prevention proposal (Bulkhead + Circuit Breaker) approved; Right-Sizing Microservices approved
- **Documentation**: High Level Architecture Diagram, Incident Response Plan, Abnormal Traffic Runbook
- **Bot Prevention**: Hash comparison architecture proposed after Sep 2025 incident (NLINCIDENT-261)
- **Blockchain**: Batched API requests deployed — stabilized system with 300k failed transaction backlog

# Related Achievements

- [[2025-01-performance-testing-improvements]]
- [[2025-04-ticket-security-digital-signature]]
- [[2025-09-cascading-failure-proposal]]
- [[2025-09-bot-prevention-proposal]]
- [[2025-10-security-checklist-owasp]]
- [[2026-03-right-sizing-microservices]]

# Lessons Learned

- Stepping into a domain with better-informed experts requires humility, structured questions, and read-backs to validate understanding.
- Architectural patterns (Bulkhead, Circuit Breaker) that apply at connection pool level also apply at pod orchestration level — consistent thinking across layers.
- A single shared resource (one connection pool, one pod group) is always a latent single point of failure under scale.
- External client relationships (DFNN) require carefully calibrated technical communication — finding the right altitude for each stakeholder.
