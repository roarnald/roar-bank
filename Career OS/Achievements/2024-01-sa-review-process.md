---
title: SA Review Process — Architecture Gate for New Frontend Projects
date: 2024-01-01
role: Software Architect
organization: Merquri Pte Ltd
project: Team Workflow
leadership_types:
  - technical
  - organizational
  - stakeholder
skills:
  - Solution Architecture
  - Technical Leadership
  - Stakeholder Management
  - Organizational Leadership
impact: high
source_documents:
  - raw/appraisals/2023.md
  - raw/appraisals/2024.md
---

# Context

In 2023, Ronald observed that new frontend projects were often started by copying past codebases without thought for maintainability, scalability, or modern tooling. Developers would reach for whatever was familiar, often resulting in outdated dependencies and technical debt from day one. Ronald proposed an "Architecture Review" gate as an improvement measure.

# Problem

New projects were set up without any architectural review:
- Copied from past (sometimes legacy) projects
- Used outdated or wrong dependencies
- Missed opportunities to leverage better tools
- Accumulated technical debt before the first feature was written
- No lead/architect input during the critical setup phase

# Actions

- **Proposed the Architecture Review process in the 2022 appraisal suggestion/feedback section** — advocating for an SA Review at the early stages of new project setup.
- In 2024, as the newly appointed Software Architect, implemented the proposal:
  - Conducted SA Reviews for **Rollball**, **PNL**, and **credit draw results** — the first three projects to go through the new gate.
  - Reviewed project foundations before significant code was written.
  - Provided direction on dependency selection, build tooling, architecture patterns.
  - Worked closely with PMs and developers during these reviews.
- Also used the SA Review to debug **project-level issues** that individual developers couldn't resolve (e.g., Rollball sluggishness, Lottie animation performance, Vite dynamic import issues). — [[2024-01-vite-solutions-year-old-problem]]

# Impact

- New projects starting with SA Review are better architected from day one.
- Developers exposed to architectural thinking earlier in the project lifecycle.
- Provided senior developers with richer challenges beyond daily Change Requests.
- Joanne (2024): *"With a new Architect role, we as a Team decided to implement my suggestion from 2023, to have a Software Architecture (SA) Review for new projects, just like how code reviews are for Change Requests (CRs). We managed to conduct SA Reviews for Rollball, PNL, and credit draw results and I found it to be very beneficial for helping steer some decisions and guide our developers in project setup."*

# Evidence

- 2023 Appraisal — Suggestion/Feedback section (proposal documented)
- 2024 Appraisal — "New workflow for New Frontend Projects (SA Review, Debugging of project level issues)" section

# Related Projects

- Rollball
- PNL

# Related Skills

- [[Solution Architecture]]
- [[Technical Leadership]]
- [[Organizational Leadership]]
