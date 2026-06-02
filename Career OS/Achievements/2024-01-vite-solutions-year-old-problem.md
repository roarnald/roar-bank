---
title: Vite Dynamic Import & Chunking Solutions — Resolved Year-Old Blockers
date: 2024-01-01
role: Software Architect
organization: Merquri Pte Ltd
project: PNL / Rollball
leadership_types:
  - technical
skills:
  - Vite
  - Webpack
  - Frontend Build Tools
  - Performance Optimization
  - Debugging
  - Solution Architecture
impact: high
source_documents:
  - raw/appraisals/2024.md
---

# Context

As Merquri Frontend migrated away from Webpack to Vite (for dramatically faster build speeds and developer experience), two deep technical issues emerged on the PNL and Rollball projects that had been unresolved for approximately a year. No frontend developers, seniors, or leads had found solutions.

# Problem

**Problem 1 — Vite Dynamic Import / Cache Hash Collision:**
Vite calculates content hashes for built files. Under certain conditions, the hash for a page in Build #5 was identical to Build #6. When browsers cached these files, they pointed to incorrect hash versions, causing page crashes for end users.

**Problem 2 — Vite Chunking / Library Bundle Bloat:**
Vite's code-splitting mechanism was designed for small-to-medium applications. The only straightforward method to code-split was to separate third-party libraries from local files, which caused unnecessary bloat in the library JS chunk and hurt first-load performance — a real issue for production applications at scale.

# Actions

- Deep-dived independently into Vite's internal documentation and source code.
- Researched hash calculation mechanisms and identified the collision condition.
- Designed and proposed solutions for both problems.
- Provided detailed explanations to team members so they understood the root cause, not just the fix.
- Guided teams on PNL and Rollball to resolution and shipped the solutions to production.

# Impact

- Both solutions were shipped to production on PNL and Rollball.
- Unblocked teams that had been stalled on these issues for a year.
- Prevented recurring page crashes for end users.
- Improved first-load performance by reducing library chunk bloat.
- Appraiser (Joanne, 2024): *"The best display of my problem solving skills comes from the instances where a year old issue would be brought up again where no other developers had any solutions to — vite dynamic imports and vite chunking problem."*
- Established Ronald as the go-to expert for complex build tooling issues: *"Ronald is undoubtedly the go-to guru for problem-solving, especially in unique or complex situations."* (Joanne, 2024)

# Evidence

- 2024 Appraisal — Problem Solving section (rated 5/5)
- 2024 Appraisal — "New workflow for New Frontend Projects" section
- Appraiser quote explicitly calling out these two problems as best examples of problem-solving

# Related Projects

- [[2024-01-sa-review-process]]
- [[2024-01-sa-review-process]]

# Related Skills

- [[Frontend Architecture]]
- [[Performance Engineering]]
- [[Solution Architecture]]
