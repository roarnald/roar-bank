---
title: New138 Fullstack Application (138DHW / 导航网)
start_date: 2024-01
end_date: 2024-12
role: Software Architect (Solo Full Stack Developer)
organization: Merquri Pte Ltd
technologies:
  - Astro JS
  - Node.js
  - Docker
  - Redis
  - Kubernetes
  - HashiCorp Vault
  - GitLab CI/CD
  - PostgreSQL / RDS
stakeholders:
  - Tsai Yu (interim Fullstack/NodeJS Lead — voluntary)
  - Dominic Tan (PM)
  - CTO (direction alignment)
  - NOC/DevOps Team
---

# Summary

New138导航网 was Merquri Frontend's first ever full-stack production application. Ronald was the sole full-stack developer. The project replaced hundreds of Elastic Beanstalk instances with a single unified application, significantly reducing infrastructure cost and maintenance overhead.

# Architecture

- **Astro JS** as full-stack framework with dual-mode serving: single codebase for Member and Admin views
- **Dockerized** production application for Kubernetes deployment
- **Dockerized local development** environment — single command to spin up full local stack
- **Redis caching** shared between pods for distributed state
- **HashiCorp Vault** integration for all sensitive keys and secrets
- **Database migration** process and scripts established from scratch
- **R-Deployment** workflow for full-stack Change Requests
- Custom Captcha service written from scratch — validated against load testing
- Monitoring and load testing procedures set up

# Business Problem

The navigation site was served by hundreds of individual Elastic Beanstalk instances (one per domain variant). This was expensive, operationally complex, and hard to maintain. A unified full-stack application aligned with the CTO's vision for JavaScript full-stack capability.

# Outcomes

- **Hundreds of Elastic Beanstalk instances replaced by a single application**
- Shipped **ahead of schedule**
- Established full-stack engineering capability in Merquri Frontend
- NodeJS Server Template Foundation created from learnings — reused on WeChat Redirect legacy migration
- Directly enabled Ronald's elevation to Solutions Architect role in 2025

# Related Achievements

- [[2024-01-fullstack-new138-solo]]
- [[2025-01-lotto6d-nodejs-mentoring]]

# Lessons Learned

- Solo full-stack development requires discipline in documentation and DevOps practices (others need to maintain it).
- Redis across pods introduces complexity — connection pooling and cache invalidation must be thought through.
- Vault integration is non-trivial but essential for production secret management.
- First-time full-stack gives invaluable system-level perspective that accelerated SA readiness.
