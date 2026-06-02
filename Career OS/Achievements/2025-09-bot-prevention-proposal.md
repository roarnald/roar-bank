---
title: Bot Prevention — Hash Comparison Security Architecture Proposal
date: 2025-09-23
role: Solutions Architect
organization: Merquri Pte Ltd
project: National Lottery Platform (LottoMatik)
leadership_types:
  - technical
skills:
  - Security Engineering
  - Solution Architecture
  - Cryptography
  - System Design
impact: medium
source_documents:
  - raw/appraisals/2025.md
  - raw/solution-proposals/Bot Prevention - Solution Proposal.pdf
---

# Context

The 9 September 2025 incident (NLINCIDENT-261) was triggered by internal DFNN staff running scripts/bots to mass-query report pages, bypassing the need to build a proper optimized endpoint. The existing fingerprint-based bot detection (`fingerprintjs`) only verified the existence of a fingerprint ID header — not its validity. Anyone could sniff the site, copy a fingerprint ID, and reuse it in a script.

# Problem

- The existing client-side fingerprint check provided only superficial protection.
- Users could trivially bypass it by copying headers from a real browser session into a script.
- No server-side validation of request authenticity existed.

# Actions

- Prepared "Bot Prevention Solution Proposal" (23 September 2025).
- Evaluated two solutions:

**Solution 1 — Hash Comparison (Recommended):**
- Frontend computes an MD5 hash of a uniquely-formed string containing `userId`, `user-agent`, `loginTime`, and other session-bound values.
- Hash is passed as a request header.
- Server independently computes the same hash from request session data and compares.
- Requests whose hash doesn't match are blocked — scripts copying headers from browsers cannot forge a valid hash because they lack access to all the session state used to compute it.

**Solution 2 — Fingerprint Pro (SaaS):**
- Fingerprint's Smart Signals product provides bot detection as a managed service.
- Dropped: adds subscription cost; most features not required.

- Recommended Solution 1 as the pragmatic choice: more control, no ongoing cost, negligible compute overhead (MD5 is fast).

# Impact

- Adds meaningful friction against layman bot/scripts without requiring third-party procurement.
- Part of a two-pronged response (with Cascading Failure proposal) to the September 2025 incident.
- Complements the Digital Signature ticket security work — demonstrates a pattern of layered security thinking.

# Evidence

- Solution Proposal document: "Bot Prevention Solution Proposal" (23 September 2025)
- 2025 Appraisal — Bot Prevention section

# Related Projects

- [[National Lottery Platform]]

# Related Skills

- [[Security Engineering]]
- [[Solution Architecture]]
