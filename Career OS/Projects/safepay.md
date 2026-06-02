---
title: Safepay
start_date: 2022-01
end_date: 2022-12
role: Lead Software Engineer
organization: Merquri Pte Ltd
technologies:
  - React 18
  - React Router v6
  - pnpm (Monorepo)
  - CSS-in-JS
  - GitLab CI/CD
stakeholders:
  - Tsai Yu (co-delivered Phase 1)
  - Joanne Lee (PM)
  - 8+ Backend Developers
  - Client
---

# Summary

Safepay was a brand new payment and withdrawal system written entirely from scratch. Ronald was the sole frontend developer for the entire project. Designed with the latest technologies and practices, it became one of the most modern codebases in the Frontend portfolio.

# Architecture

- Monorepo using **pnpm** — split into backoffice, payment, and withdrawal sub-packages with a shared core package
- Payment and withdrawal sub-modules built individually, sharing core components
- CSS-in-JS for maximum portability and minimum dependency footprint
- Custom modal built from scratch — no third-party library
- Mobile responsive design via single component (no duplicate mobile/desktop components)
- Developer experience: API auto-called on dev server start; `.http` files for manual API calls
- Safepay CI/CD pipeline setup in GitLab

# Business Problem

Required a modern, scalable payment and withdrawal system separate from the older cash management backoffice systems.

# Outcomes

- Phase 1 delivered in approximately **36 hours** despite originally planned for 2 weeks — due to upstream delays.
- Established as a modern architecture reference for future projects.
- Demonstrated ability to perform under extreme pressure and time constraints.

# Related Achievements

- [[2022-06-safepay-36hr-delivery]]

# Lessons Learned

- Frontend being the last stage in the pipeline absorbs upstream delays — better inter-team timeline communication is needed at the PM level.
- Under-promise, over-deliver is a sound strategy, but the pipeline must be protected.
- A well-set-up developer experience (auto API, .http files) pays off during crunch time.
