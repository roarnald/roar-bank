# Technical Leadership Evidence

*Use this for Staff Engineer resumes, technical leadership interviews, and IC promotion packets.*

---

## Scope of Technical Influence

Ronald has progressively expanded his technical influence from individual contributor → team technical standard-setter → cross-org architecture authority:

| Level | Year | Evidence |
|-------|------|---------|
| Individual expertise | 2020–2021 | Coin rewrite; optimisation expertise; mentoring |
| Team standards | 2022–2023 | Unit testing, CI/CD, monorepo patterns, code review culture |
| Org-wide direction | 2023–2024 | UIUX merger, Architecture Review process, SA Review |
| Cross-system architecture | 2025–2026 | NL platform, solution proposals, performance testing |

---

## Hardest Technical Problems Solved

### 1. Vite Dynamic Import Hash Collision (2024)
- **Scope**: Production-impacting page crashes across multiple projects
- **Duration unresolved**: ~1 year, by multiple developers
- **Method**: Deep-dive into Vite internals; identified hash algorithm behavior; designed workaround
- **Outcome**: Shipped to production on PNL and Rollball
- [[2024-01-vite-solutions-year-old-problem]]

### 2. Cascading Failure Root Cause Analysis (2025)
- **Scope**: Full system outage (NLINCIDENT-261), all endpoints unresponsive
- **Method**: Traced full cascade: bot scripts → long-running queries → HikariCP exhaustion → `CannotGetJdbcConnectionException` → outage
- **Outcome**: Two approved proposals (Bulkhead, Batching) stabilised the system
- [[2025-09-cascading-failure-proposal]] | [[2026-03-right-sizing-microservices]]

### 3. Coin Backoffice Architecture Decision (2021)
- **Scope**: New core backend platform (CASH-V2)
- **Ambiguity**: PM said minimal fork; Ronald identified long-term scalability risk
- **Method**: Full rewrite from scratch; first monorepo; all packages upgraded
- **Outcome**: Became the benchmark quality codebase in Merquri FE
- [[2021-01-coin-backoffice-rewrite]]

### 4. Full-Stack Application Architecture (2024)
- **Scope**: First full-stack production app; no prior internal expertise
- **Method**: Self-led with guidance from Tsai Yu (NodeJS); designed dual-mode Astro app with distributed Redis, Vault secrets, containerised infra
- **Outcome**: Replaced hundreds of AWS instances; shipped ahead of schedule
- [[2024-01-fullstack-new138-solo]]

---

## Cross-Domain Technical Range

| Domain | Evidence |
|--------|---------|
| Frontend (React, Next.js, Svelte, Astro) | Primary domain, 6+ years |
| Build tooling (Webpack, Vite, Lerna, pnpm) | Deep expertise; solved year-old Vite issues |
| CI/CD (Jenkins, GitLab, Groovy, Docker) | Pipeline setup on multiple projects |
| Backend / Full Stack (Node.js, Astro) | Production fullstack app (2024) |
| Infra (Kubernetes, AWS RDS, Redis, Kafka) | NL platform + New138 |
| Security (OWASP, cryptography, Vault) | 3 security proposals + OWASP audit |
| Testing (Jest, JMeter) | Unit testing pioneer; load testing for NL |
| Distributed Systems (Bulkhead, Circuit Breaker, Batching) | 3 approved proposals |

---

## Technical Mentoring
- Junior developers developed into mid-level engineers under Ronald's code review and coaching
- Jacky: delivered first production NodeJS service — [[2025-01-lotto6d-nodejs-mentoring]]
- UIUX developers: transitioned to React team standards — [[2023-01-uiux-team-merger]]
- Team as a whole: introduced to Next.js, Svelte, Astro, MDX, monorepos, unit testing — [[Technical-Leadership]]

---

## Appraiser Quotes
> *"Ronald consistently spends time learning about new trends and continuously enhancing his skills... Ronald plays a key role in driving innovation and improvement for the FE team."* — Dominic, 2023

> *"He is always motivated and taking initiative to implement new elements into our projects."* — Dominic, 2024

> *"Ronald always stays up-to-date with the latest trends, striving to incorporate new technology into our current and upcoming projects."* — Dominic, 2024
