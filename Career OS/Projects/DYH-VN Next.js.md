---
title: DYH-VN Next.js (Wind2DYH-Member-VN)
start_date: 2022-01
end_date: 2022-12
role: Lead Software Engineer
organization: Merquri Pte Ltd
technologies:
  - Next.js
  - React
  - SSG (Static Site Generation)
  - ISR (Incremental Static Regeneration)
  - Vercel (explored)
  - MDX
stakeholders:
  - Tsai Yu
  - Joanne Lee (PM)
  - DevOps / NOC Team
---

# Summary

Combined the separate Mobile (React Team) and Desktop (UIUX Team) repositories for DYH Vietnam into a single Next.js application. First significant Next.js implementation in Merquri Frontend, featuring comprehensive optimisation for performance and hosting.

# Architecture

- **Combined Mobile + Desktop** repos into a single unified Next.js codebase
- Replaced react-router with Next.js framework routing
- **SSG (Static Site Generation)** for all possible pages — avoids SSR-only pages which were at risk of DDoS
- **ISR (Incremental Static Regeneration)** for pages that cannot use SSG (dynamic content)
- Zero pages left as pure SSR — explicit security decision
- Worked with Vercel team to trial enterprise hosting (ultimately not adopted due to cost)

# Business Problem

Maintaining separate mobile and desktop repositories for the same product doubled the development and maintenance overhead. Each had different codebases, different deployment processes, and different quality levels.

# Outcomes

- Single codebase serving both mobile and desktop
- Static site generation dramatically reduced server load
- Pioneered Next.js knowledge in the team — later applied in DYH Revamp (build-time rendering)
- DYH Revamp 2023: used MDX for long-form content pages (90% productivity improvement for content-heavy pages)

# Related Achievements

- [[2023-01-uiux-team-merger]]

# Lessons Learned

- DevOps readiness is as important as frontend implementation: NoC team unfamiliarity with Next.js hosting delayed adoption of SSR features.
- SSG should be the default; SSR should require explicit justification due to DDoS surface.
- MDX is a transformative tool for content-heavy applications — worth evangelizing.
