# NodeJS / Full Stack Development

## Definition
Building server-side JavaScript applications, fullstack services, microservices, and establishing backend development practices within a frontend-first organisation.

## Key Demonstrations

### Production Applications Built
- **Community Chat Application (2026)** — NestJS + Valkey Streams + BullMQ + PostgreSQL. Created and led dedicated Fullstack JS team. Built architecture, not feature code. Applied Multi-Agent Audit workflow. [[2026-02-community-chat-nestjs-team-lead]]
- **New138 Fullstack (138DHW)** — Astro JS + Node.js, Docker, Redis, Vault, Kubernetes (2024). Solo. Replaced hundreds of Elastic Beanstalk instances. [[2024-01-fullstack-new138-solo]]
- **Lotto6D KJW NodeJS Microservice (2025)** — Mentored Jacky to delivery. Custom API server, lifted overseas team dependency. [[2025-01-lotto6d-nodejs-mentoring]]
- **WeChat Redirect Migration (2024)** — Guided developer to rewrite legacy application using NodeJS Server Templates. [[2024-01-fullstack-new138-solo]]

### Reference Templates Created
- NodeJS Server Template Foundation (TypeScript + plain JS variants):
  - Proper parameter validation
  - File-based routing
  - Best practices baseline for future developers
- Templates directly enabled and accelerated WeChat Redirect rewrite.

### Multi-Agent Audit Workflow
A novel technique developed and applied on the Community Chat Application (2026):
- Uses multiple AI agents in coordinated sequence to audit architectural changes before merging.
- Each agent evaluates a distinct quality dimension: correctness, security posture, scalability implications, NestJS pattern adherence.
- Enables production-grade quality control on complex architectural changes without a dedicated senior reviewer.
- Transferable to any team working in an unfamiliar or rapidly-evolving stack.

### Technologies
- **NestJS** — backend framework; module/controller/service architecture, DI, guards, WebSocket gateways
- **Astro JS** — full-stack SSR framework; converted to dual-mode (Member + Admin) from single codebase
- **Redis / Valkey** — caching between Kubernetes pods; Pub/Sub and Streams for real-time message routing (Community Chat)
- **HashiCorp Vault** — secrets management
- **Docker** — containerisation of production app and local development environment
- **Kubernetes** — deployment; HPA configuration and validation
- **BullMQ** — message queue throttling database writes (Community Chat)
- **PostgreSQL / RDS** — database; migration scripting; schema design
- **Kafka** — message queue (NL system blockchain throttling)
- **DB Migration Scripts** — schema evolution process

## Related Projects
- [[Community Chat Application]]
- [[New138 Fullstack Application]]
- [[National Lottery Platform]]
- [[Lotto6D NodeJS Service]]

## Related Skills
- [[Frontend Architecture]]
- [[Solution Architecture]]
- [[Kubernetes DevOps]]
