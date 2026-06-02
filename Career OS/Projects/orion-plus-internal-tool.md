---
title: Orion+ (Internal Frontend Tool)
start_date: 2021-01
end_date: present
role: Lead Software Engineer → Software Architect
organization: Merquri Pte Ltd
technologies:
  - React
  - Node.js
  - Techfi Calendar integration
  - HashiCorp Vault (password migration)
  - GitLab integration
stakeholders:
  - All Merquri Frontend members
  - QA Team
  - PM Team
  - APP Support Team
---

# Summary

Orion+ started as a Jira ticket updater and evolved into a critical internal tool used across Merquri for deployment management, effort tracking, and workspace operations. By 2025, it powers weekly deployments, timesheets, and ticket management for the entire company.

# Architecture

- React frontend
- Node.js backend
- GitLab integration for weekly deployment workflows
- Techfi Calendar integration (added 2023)
- HashiCorp Vault for password management (migrated from plaintext)
- Sub Ticket Machine for prefixed ticket creation ([DYH][BO], [DYH][Web], etc.)

# Business Problem

Manual and fragmented tooling for deployment management, incident tracking, and workflow coordination created overhead and error risk. Orion+ centralised these into one internal product.

# Outcomes

- Deeply embedded in Merquri's product delivery workflow
- Weekly Deployment management
- Effort tracking / Timesheets
- Workspace resetting
- APP Support team relies on it for metadata management

# Related Achievements

- [[2022-01-frontend-sharing-program]] (State of Merquri covered Orion+ changes)

# Lessons Learned

- Internal tools grow beyond their original scope and become critical infrastructure — plan for maintenance from the start.
- A well-designed internal tool can multiply team productivity at negligible marginal cost.
- Proposed 2025: Orion+ 2.0 overhaul to make it portable and replicable for sister companies.
