---
title: Coin Backoffice (CASH-V2)
start_date: 2021-01
end_date: 2022-12
role: Senior Software Engineer → Lead Software Engineer
organization: Merquri Pte Ltd
technologies:
  - React
  - Lerna (Monorepo)
  - AntD 4.0
  - BlueprintJS
  - Jenkins (Groovy CI/CD)
  - JavaScript
stakeholders:
  - Tsai Yu (Technical Lead / Mentor)
  - Joanne Lee (PM)
  - PM Team
  - QA Team
---

# Summary

Coin Backoffice was the full rewrite of the legacy CASH (wind2cash-backend-3) backoffice system. Ronald was the sole frontend developer appointed to lead the back office portion. Despite PM direction to fork and minimally change the legacy repo, Ronald made the decision to scrap 95% and rewrite from scratch — setting a new standard for frontend quality at Merquri.

# Architecture

- First monorepo setup in Merquri Frontend using **Lerna**
- Combined multiple repositories into one with shared `@frontend/core` packages
- Dynamic, recursive role management with API-driven UI generation
- Shared dynamic components (e.g., Company Settings reused as Product Settings)
- Optimised state management patterns prepared for scale
- Major package version upgrades throughout

# Business Problem

The existing CASH backoffice was slow (seconds to register state changes), contained massive amounts of legacy and copy-pasted code, and was not scalable. Any new features added to the old codebase would worsen the problem.

# Outcomes

- Pages that took multiple seconds to respond now respond near-instantly
- Established the cleanest and most maintainable frontend codebase in Merquri at the time
- Monorepo approach adopted as a template for future projects (Safepay, etc.)
- 2022 listing in appraisal: completed all major features including 交易管理, 用户管理, 公司/系统设置, VIP管理, 转账管理, 黑名单/白名单管理, and more

# Related Achievements

- [[2021-01-coin-backoffice-rewrite]]
- [[2022-09-frontend-unit-testing]]

# Lessons Learned

- Rewrites from scratch are painful but sometimes necessary — the compounding cost of legacy debt is real.
- Taking ownership of architecture decisions (even against initial direction) is part of leadership.
- Monorepos reduce context-switching and enable code reuse at the expense of initial setup complexity.
