---
title: Dependency Bot Automation — 90% Reduction in Security Patch Effort
date: 2025-01-01
role: Software Architect
organization: Merquri Pte Ltd
project: Security Patch Automation
leadership_types:
  - technical
  - organizational
skills:
  - DevOps
  - GitLab CI/CD
  - Security Engineering
  - Process Automation
  - Systems Thinking
impact: high
source_documents:
  - raw/appraisals/2025.md
---

# Context

The newly established Security Team began pushing for fixes from code scanning tool reports across many repositories. Ronald and the team spent significant time chasing security patches one-by-one across a large codebase portfolio.

# Problem

- Merquri Frontend manages a large number of repositories — each requiring regular security dependency updates.
- Manual patching is labour-intensive: once a full round was completed, new vulnerabilities would appear and the cycle would restart.
- The sheer volume of codebases meant that no single dedicated resource could keep pace.

# Actions

- Recognized the systemic inefficiency: the cycle of manual patching was inherently unsustainable as codebases scaled.
- Designed and implemented a **Dependency Bot** integrated into the GitLab workflow.
- Updated the **deployment workflow** to incorporate automatic security patching on every deployment cycle — making security updates a standard part of the release process, not a separate remediation effort.
- A secondary benefit: used the security patch upgrade process as an **intentional training opportunity** — exposing team members to complex merge conflicts in areas they rarely touched, building their package manager and dependency management skills.
- Proposed and taught a standardized **package manager workflow** with the least path of resistance, easily understood, and scalable to a large team.

# Impact

- **Reduced the effort to maintain security patches by up to 90%** — no dedicated resource required.
- Security Team pressure on the frontend team diminished significantly.
- Team members gained stronger proficiency in dependency management as an indirect benefit.
- Appraiser (Joanne, 2025): *"The great success of this implementation significantly reduced the cost needed to maintain these security patches."*

# Evidence

- 2025 Appraisal — Security Patch Automation via Dependency Bot section
- 2025 Appraisal — Misc Workflow Enhancement section
- Quantified impact: 90% reduction in effort

# Related Projects

- [[National Lottery Platform]]

# Related Skills

- [[Security Engineering]]
- [[Kubernetes DevOps]]
- [[Technical Leadership]]
