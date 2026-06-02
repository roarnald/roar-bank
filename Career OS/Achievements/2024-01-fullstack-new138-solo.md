---
title: New138 Full-Stack Application — Solo Developer, Shipped Ahead of Schedule
date: 2024-01-01
role: Software Architect
organization: Merquri Pte Ltd
project: New138 Fullstack Application (138DHW)
leadership_types:
  - technical
  - stakeholder
skills:
  - Astro JS
  - Node.js
  - Docker
  - Redis
  - Kubernetes
  - Vault
  - Full Stack Development
  - DevOps
  - Database Migration
  - Load Testing
impact: very_high
source_documents:
  - raw/appraisals/2024.md
  - raw/appraisals/2025.md
---

# Context

In 2023–2024, discussions between PMs and Ronald were ongoing about building a full-stack JavaScript application. A navigation site requirement (New138导航网 / 138DHW) presented the perfect use case, aligning with the CTO's vision for full-stack JS. This was also the first official full-stack application in Merquri Frontend's history.

# Problem

The existing setup used hundreds of Elastic Beanstalk instances (one per domain/region variant) to serve what was essentially a navigation/portal site. This was enormously expensive, operationally heavy, and hard to maintain. A unified full-stack application could replace all of these instances.

# Actions

Worked solo as the full-stack developer with guidance from Tsai Yu (interim Fullstack/NodeJS Lead) and PM Dominic:

- **Set up Astro JS as a full-stack service** with dual mode: serving Member and Admin requirements from a single codebase.
- **Dockerized the production full-stack application** for Kubernetes deployment.
- **Dockerized local development infrastructure** so developers can run the full environment locally with one command.
- Implemented **Redis caching** between pods for data sharing in a horizontally scaled environment.
- Integrated **HashiCorp Vault** for secure secret/key management — avoided hardcoded secrets.
- Wrote a **custom Captcha service** resilient to load testing.
- Established **monitoring and load testing** procedures.
- Wrote **database migration scripts** and used R-Deployment for full-stack Change Requests.
- Wrote **data migration DB script** from the old product to the new system.
- Set up **DB Migration process** for ongoing schema evolution.
- After project stabilized: created **NodeJS Server Template Foundation** (TypeScript + plain JS variants) as reusable reference for future fullstack projects.

# Impact

- **Replaced hundreds of Elastic Beanstalk instances with a single full-stack application** — significantly reduced infrastructure cost and maintenance effort.
- Shipped **ahead of schedule**.
- NodeJS templates were immediately applied: guided a developer to rewrite the WeChat Redirect legacy application using the templates, speeding up the process.
- Established full-stack capability within Merquri Frontend for the first time.
- Appraiser (Joanne, 2024): *"Setting up the full-stack application was an impressive breakthrough, and I foresee it bringing tremendous value to both the team and company business."*
- Appraiser (Dominic, 2024): *"He always manages to deliver, which impresses me greatly."*
- Experience directly enabled Ronald's elevation to Solutions Architect role in 2025: *"the sole developer for our Fullstack Application, 138DHW, which paved the way for me to understand the overarching picture from a system perspective."*

# Evidence

- 2024 Appraisal — Full Stack Application section
- 2024 Appraisal — NodeJS Server Template Foundation section
- 2024 Appraisal — Innovation (rated 5/5)
- 2025 Appraisal — referenced as experience foundation for SA role

# Related Projects

- [[New138 Fullstack Application]]

# Related Skills

- [[NodeJS Fullstack]]
- [[Kubernetes DevOps]]
- [[Solution Architecture]]
- [[Technical Leadership]]
