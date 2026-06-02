---
title: CASH-V2 (Coin) Backoffice — Solo Rewrite from Scratch
date: 2021-01-01
role: Senior Software Engineer
organization: Merquri Pte Ltd
project: Coin Backoffice
leadership_types:
  - technical
  - organizational
skills:
  - React
  - JavaScript
  - Monorepo
  - Lerna
  - AntD
  - BlueprintJS
  - State Management
  - Architecture
impact: high
source_documents:
  - raw/appraisals/2021.md
  - raw/appraisals/2022.md
---

# Context

The existing CASH backoffice (wind2cash-backend-3) was a legacy repository containing years of accumulated technical debt. The PM's original instruction was to fork it and make minimal changes for the fastest time to production. Ronald was the sole developer appointed to lead the back office portion of CASH-V2, internally called "Coin."

# Problem

The legacy codebase was of poor quality and contained enormous amounts of legacy code. Blindly forking it would have produced an unscalable foundation, perpetuating problems for years. Pages on the old system took several full seconds to register a state change. Code was often copied-and-pasted with no abstraction, and the Company Settings page alone was thousands of lines of incomprehensible code.

# Actions

- Made the unilateral decision to **scrap 95% of the forked repository** and rewrite from scratch — overriding the PM's initial "minimal changes" directive after understanding the long-term risk.
- **Set up the first monorepo** in Merquri Frontend using Lerna, combining multiple repositories into one, sharing packages and code across sub-projects.
- Upgraded most packages to latest versions.
- Implemented **dynamically rendered and shared components**: e.g., Company Settings page became a shareable dynamic component reused as Product Settings — cutting development time by half.
- **Role Management** feature added scroll helper, made fully dynamic, with automatic category grouping.
- Applied state management choices that optimised page performance for scale.
- Rewrote all core pages: 交易管理, 用户管理, 公司/系统设置, 产品管理, 收款设置, 权限管理, 角色管理 (recursive rendering with dynamic UI from API), VIP管理, 转账管理, 黑名单/白名单管理 and many more.
- Developed new Jenkins CI/CD pipeline in Groovy; migrated older DevOps features.
- Mentored junior developers during the project via code reviews.

# Impact

- Pages that previously took **several seconds** to register a state change now responded near-instantly.
- Established Coin as "one of the easiest to maintain and best quality frontend projects" (Tsai Yu appraiser comment).
- Monorepo setup became a template adopted by subsequent projects.
- Delivered while also completing regular team Change Requests and resolving incident tickets (noted by appraiser).
- Received **Outstanding (5/5)** ratings across all assessment criteria for 2021.
- Appraiser (Tsai Yu): *"使得coin backoffice是目前frontend較容易維護與良好的project之一"*
- Co-Appraiser (Joanne): *"He has displayed outstanding leadership skills during the COIN project, proving to us that he has the potential and is ready to take up more responsibility in leading the team."*

# Evidence

- 2021 Annual Appraisal — Productivity & Quality section (rated 5/5)
- 2021 Annual Appraisal — Creativity & Problem Solving (rated 5/5)
- 2022 Annual Appraisal — listed under Technical Achievements

# Related Projects

- [[Coin Backoffice]]
- [[Safepay]]

# Related Skills

- [[Frontend Architecture]]
- [[Frontend Architecture]]
- [[Frontend Architecture]]
- [[Technical Leadership]]
