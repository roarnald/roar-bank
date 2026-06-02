---
title: Frontend Unit Testing — Pioneered Automated Testing Culture
date: 2022-09-01
role: Lead Software Engineer
organization: Merquri Pte Ltd
project: CASH Backoffice / Coin
leadership_types:
  - technical
  - organizational
skills:
  - Jest
  - Unit Testing
  - GitLab CI/CD
  - Test Automation
  - Technical Leadership
impact: high
source_documents:
  - raw/appraisals/2022.md
---

# Context

Prior to 2022, Merquri Frontend had no automated testing in place. All validation relied on manual QA. Ronald identified this as a systemic gap that contributed to recurring incidents.

# Problem

Repeated incidents in frontend could not be caught before production. There was no mechanism to enforce code correctness automatically, and no culture or precedent for frontend testing in the team.

# Actions

- **Pioneered the implementation of Frontend Unit Testing** for CASH Backoffice, achieving **86% coverage for utility files**.
- Implemented three test types: **Functional, Non-Functional, and Snapshot testing** — providing examples to the team for all three.
- Added a **GitLab runner** configured to run the test suite on every push and merge request.
- Set up automated **repository coverage badge** on GitLab, providing live visibility of coverage metrics.
- Trialled unit testing on the Coin repository as a proof of concept.
- **Guided junior developers** on implementing unit tests for other repositories — extended the practice across the team.

# Impact

- Established the first automated test infrastructure in Merquri Frontend.
- Appraiser (Joanne): *"Well done for initiating and implementing the unit test which brought great benefits to the team. This process is important for making the testing and troubleshooting more efficient and agile, greatly improved the productivity of our team."*
- Co-Appraiser (Tsai Yu): *"單元測試也讓代碼更加可靠"* (Unit tests make code more reliable)
- Created a lasting cultural shift: testing became part of the development workflow for multiple repos.

# Evidence

- 2022 Annual Appraisal — Productivity & Solving Problem (rated 5/5)
- Listed under Technical Achievements in 2022 appraisal
- 86% test coverage metric is documented

# Related Projects

- [[Coin Backoffice]]
- [[CASH Backoffice]]

# Related Skills

- [[Test Automation]]
- [[Technical Leadership]]
- [[Frontend Architecture]]
