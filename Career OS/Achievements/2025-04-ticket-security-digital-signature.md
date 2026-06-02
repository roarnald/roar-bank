---
title: Ticket Security — Digital Signature Proposal for Lottery Ticket Authenticity
date: 2025-04-21
role: Solutions Architect
organization: Merquri Pte Ltd
project: National Lottery Platform (LottoMatik)
leadership_types:
  - technical
  - stakeholder
skills:
  - Security Engineering
  - Cryptography
  - Solution Architecture
  - Stakeholder Communication
  - Systems Design
impact: high
source_documents:
  - raw/appraisals/2025.md
  - raw/solution-proposals/Tech Proposal on Strengthen Ticket Security.pdf
---

# Context

Following a business trip to DFNN (the client in Manila), a need was identified to strengthen ticket authenticity and mitigate fraud in the National Lottery system. The existing system used SHA-256 hashing as an obfuscation method, but this could not confidently identify fake tickets because SHA-256 is an open algorithm — anyone with knowledge of the hashing scheme could theoretically generate a valid-looking hash.

# Problem

- SHA-256 as implemented was only an obfuscation, not a verification mechanism.
- The system could not distinguish a maliciously faked ticket from a legitimate system issue.
- A forged ticket could potentially pass through the POS system's only verification check (database hash lookup).

# Actions

- Prepared "Tech Proposal on Strengthen Ticket Security and Prevent Fake Ticket Claims" (SA Proposal, 21 April 2025).
- **Verified with architecture team** (Kar Wai), and developers (Seng Kai, Jazz) for feasibility.
- Proposed replacing SHA-256 hashing with **RSA Digital Signatures** (asymmetric cryptography):
  - During ticket sale: Server computes SHA-256 hash of ticket payload, then encrypts it with a private key to generate a Signature.
  - The Signature (not the hash) is embedded into the QR code alongside the ticketId.
  - During claiming: POS System decrypts the Signature using a public key to obtain the hash. Server queries database by ticketId, retrieves the stored precalculated hash, and compares the two.
  - If they don't match → ticket is definitively fake (only the server can generate a valid Signature using its private key).
- Also evaluated and provided status/recommendations on Proposed Enhancements #3, #4, and #5 (transaction context binding, agent-level authentication, out-of-band claim tokens).
- **Received praise from DFNN** during Manila visit for the MFA multi-device key holding proposal.

# Impact

- Proposed a system where fake tickets can be **definitively identified** rather than just suspected.
- Distinguishes system errors from malicious fraud — critical for dispute resolution in a government lottery context.
- Solution leverages existing cryptographic principles (used widely in digital certificates and blockchain) without requiring expensive third-party services.
- Verified technically feasible with minimal developer changes (2 modification points).

# Evidence

- Solution Proposal document: "Tech Proposal on Strengthen Ticket Security and Prevent Fake Ticket Claims" (21 April 2025)
- 2025 Appraisal — SA section, Ticket Strengthening with Digital Certification
- Referenced in 2025 Appraisal: *"I was able to propose a technically sound solution like leveraging MFA to allow multiple devices to hold a single key, and had received praise from DFNN during my trip to Manila."*

# Related Projects

- [[National Lottery Platform]]

# Related Skills

- [[Security Engineering]]
- [[Solution Architecture]]
- [[Stakeholder Management]]
