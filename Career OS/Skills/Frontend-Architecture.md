# Frontend Architecture

## Definition
Designing scalable, maintainable frontend systems — including build tooling, monorepos, rendering strategies, state management, and cross-platform delivery.

## Key Demonstrations

### Monorepo Design
- First monorepo at Merquri using **Lerna** (Coin Backoffice, 2021). [[2021-01-coin-backoffice-rewrite]]
- Monorepo using **pnpm** (Safepay, 2022). [[safepay]]
- Combined mobile + desktop repos into a single Next.js monorepo (DYH-VN, 2022). [[dyh-vn-nextjs]]

### Rendering Strategy
- **SSG + ISR** via Next.js for DYH-VN — first in team; deliberate decision to avoid pure SSR for DDoS risk mitigation (2022).
- **Build-time rendering** with React 18 + Next 13 in DYH Revamp mobile/subpages (2023).
- **Astro JS** — used for full-stack dual-mode application (Member + Admin from single codebase, 2024). [[new138-fullstack-application]]

### Build Tooling
- Webpack setup of new repositories (2021).
- Webpack major version upgrades (4 → 5) across multiple repositories (2023).
- **Vite**: Early adopter; solved two year-old Vite-specific issues (dynamic import hash collision, chunking bloat) that no other developer could solve (2024). [[2024-01-vite-solutions-year-old-problem]]
- GitLab runner CI pipeline for automated testing (2022). [[2022-09-frontend-unit-testing]]
- GitLab CI migration from Jenkins (2023).

### State Management
- Contributed to `@frontend/service` — Merquri's internal state management library; added dynamic key watching for optimization (2022); contributed to its third iteration (2023).
- Applied render-optimization state management patterns in Coin Backoffice — dramatically reduced state change latency.

### Framework Diversity
- **React** (primary, deep expertise)
- **Next.js** (SSG, ISR, App Router)
- **Astro JS** (full-stack, SSR, SPA conversion)
- **Svelte** (introduced as team's first non-React framework, 2023)
- **MDX** (long-form content; achieved 90% productivity improvement for content pages)

### Performance & DX
- Dependency Bot — automated security patch maintenance (90% effort reduction). [[2025-01-dependency-bot-90pct-reduction]]
- Barrel Import Removal via Golang automation tool (90% effort reduction, 2025).
- Package manager workflow standardization across large team with many repositories.
- Node.js version upgrade orchestration across entire portfolio (2023, 2025).

## Related Projects
- [[Coin Backoffice]]
- [[Safepay]]
- [[DYH-VN Next.js]]
- [[New138 Fullstack Application]]

## Related Skills
- [[Technical Leadership]]
- [[NodeJS Fullstack]]
