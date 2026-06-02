---
title: Safepay Phase 1 — Delivered in 36 Hours Under Extreme Time Crunch
date: 2022-06-01
role: Lead Software Engineer
organization: Merquri Pte Ltd
project: Safepay
leadership_types:
  - technical
  - stakeholder
skills:
  - React
  - React 18
  - React Router v6
  - CSS-in-JS
  - Monorepo
  - pnpm
  - Docker
  - CI/CD
  - Performance Under Pressure
impact: high
source_documents:
  - raw/appraisals/2022.md
---

# Context

Safepay was a new payment and withdrawal system written from scratch using modern best practices. During planning, Frontend was given a reasonable 2-week window for Phase 1. Due to delays from upstream teams (backend, etc.), the actual time available when Frontend could start was approximately 36 hours.

# Problem

- Frontend is always the last stage in the development pipeline; upstream delays compressed their window from 14 days to 1.5 days.
- Ronald was the sole developer for Safepay.
- The client-facing deadline could not be moved.

# Actions

- Ronald and Tsai Yu worked extended overtime through nights and weekends to deliver all Phase 1 features.
- Set up the project from scratch with the newest architecture:
  - Monorepo using **pnpm**
  - Split backoffice, payment, and withdrawal into separate sub-packages with a shared core package
  - Used **React 18** and **React Router v6**
  - Custom CSS-in-JS for lightweight, animation-rich payment and withdrawal UIs
  - Minimised third-party libraries — modal built from scratch
  - Mobile responsive single component instead of duplicate components per viewport
- Implemented **developer experience improvements**:
  - API auto-called on dev server start to create SIT transactions automatically
  - `.http` files for manual API calls without running the dev server
  - CI/CD setup for Safepay
- Coordinated with 8+ backend developers to implement and align features.

# Impact

- Delivered all Phase 1 requirements on time despite 93% compression of the planned timeline.
- Client deadline was met.
- PM appraiser noted: *"Your effort and dedication for rushing out the Safepay within such tight schedule is well recognized."*
- Project established Safepay as one of the most modern and well-architected frontend codebases.

# Evidence

- 2022 Annual Appraisal — Productivity & Solving Problem section (rated 5/5)
- 2022 Annual Appraisal — Time Management and Planning section (rated 5/5)
- Appraiser: *"This has also shown that you are able to perform when under tremendous pressure."*

# Related Projects

- [[Safepay]]

# Related Skills

- [[Frontend Architecture]]
- [[Frontend Architecture]]
- [[Stakeholder Management]]
- [[Technical Leadership]]
