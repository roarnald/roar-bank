---
title: UIUX Team Merger — Dissolved Legacy Team, Freed 4 Headcounts
date: 2023-01-01
role: Lead Software Engineer
organization: Merquri Pte Ltd
project: Team Restructuring
leadership_types:
  - organizational
  - people
  - stakeholder
skills:
  - Organizational Design
  - People Management
  - Change Management
  - Technical Leadership
  - Stakeholder Management
impact: very_high
source_documents:
  - raw/appraisals/2022.md
  - raw/appraisals/2023.md
---

# Context

The UIUX Team used a legacy HTML/CSS/JS stack and was responsible for setting up the skeleton and foundation of new projects. However, their code quality was consistently far below the Web (React) Team's standards. Projects set up by the UIUX team required React Team members to delete or rewrite significant portions before developing features.

# Problem

- UIUX developers used outdated tools and had little understanding of React or modern frontend.
- Their codebase setup created large amounts of technical debt immediately (unused dependencies, non-reusable components, manual build-and-upload workflows).
- Documented examples: header bar re-rendered on every page instead of being reused; half of dependencies were unused and uncommitted; Announcement Feature was broken for years due to a wrong ID mapping.
- The gap between UIUX and Web Team standards was widening exponentially.
- It was becoming impossible to hire developers who specialized in the vanilla HTML/CSS/JS stack, as modern developers typically know React.
- The team was over-reliant on a single lead who was becoming a single point of failure.

# Actions

- Researched, analyzed, and **presented a business case to Frontend Internal Management** arguing for dissolving the UIUX team and merging into a single Web Team.
- Before proceeding: **individually interviewed every UIUX developer** — committed that if even one person opposed, a custom team structure would be created for them. All approved.
- Personally undertook massive remediation effort across all UIUX repositories:
  - CASH Desktop Franchise: Added automated git diff script to identify and rebase SIT; eliminated error-prone Excel tracking sheet.
  - CDN-Shine: Split single production file into SIT/UAT/production environments.
  - Forked H5 Games repo (split CASH and API game codebases).
  - IPA Dashboard: Purged unused packages, rewrote legacy packages; performance score 60+ → 99.
  - DYH Desktop / DYH-VN Desktop: Rewrote legacy code, removed unused dependencies.
  - DSN Revamp Templates: Added Gulp HTML/CSS Hot Reload; rewrote to support more themes dynamically (3 templates supporting 7).
  - DYH Revamp: Complete architectural rewrite; introduced `<dialog>`, MDX, NextJS build-time rendering.
  - Rewrote all internal project sub-dependencies (Yu E Bao Graph/FAQ, Spin Wheel, Lucky Draw, DYH Subpages, Puzzle Swipe, Captcha, Payment Page).
- **Node Upgrade Orchestration**: Collaborated with Hau Cherng to upgrade Node across every single Jenkins-built repository; managed incompatibilities (Webpack 4 → 5 migrations) across 4-5 batches.
- Acted as mentor and overseer for ex-UIUX team members transitioning to React Team work; paired them with seasoned developers.

# Impact

- **Freed 4 additional headcounts** to serve as productive contributors to the Web Team.
- Eliminated the structural single point of failure (UIUX team's reliance on their lead).
- As of Q4 2023, team functioned as one unified Web Team.
- Appraiser (Joanne): *"Ronald is always seeking for breakthrough in Frontend daily operation, making the team more efficient and valuable on what they do every day."*
- Appraiser (Dominic): *"Consistently demonstrates exceptional productivity... significantly contributing to the enhancement of overall workflow and developer experience."*
- Joanne 2023 end note: *"Ronald is like the brain and heart of the Frontend team that couldn't live without."*

# Evidence

- 2022 Appraisal — Suggestion/Feedback section (proposal documented)
- 2023 Appraisal — Team Merger & Team Rename section
- 2023 Appraisal — Productivity & Solving Problem (rated 5/5)
- 2023 Appraisal — Technical Achievements section (10 of the listed items relate to this effort)
- Confluence artefacts page: listed in appraisal as evidence of UIUX repository issues

# Related Projects

- [[DYH-VN Next.js]]

# Related Skills

- [[Organizational Leadership]]
- [[People Leadership]]
- [[Technical Leadership]]
