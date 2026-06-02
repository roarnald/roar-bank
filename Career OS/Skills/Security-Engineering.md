# Security Engineering

## Definition
Identifying security vulnerabilities, designing preventive measures, applying cryptographic principles, and establishing security practices across a development organisation.

## Key Demonstrations

### Security Architecture Proposals
- **Digital Signature for Lottery Tickets (Apr 2025)**: Proposed RSA asymmetric cryptography to replace SHA-256 obfuscation — enables definitive fake ticket detection. Verified with architecture team. [[2025-04-ticket-security-digital-signature]]
- **Bot Prevention (Sep 2025)**: Hash Comparison proposal using session-bound MD5 to block scripted API abuse. [[2025-09-bot-prevention-proposal]]
- **Data Watermarking (Aug 2025)**: Proposed invisible whitespace steganography in replicated databases to identify data breach sources.

### Proactive Security Reviews
- **OWASP Security Checklist (2025)**: Self-initiated before penetration test; caught ~10 areas of improvement. [[2025-10-security-checklist-owasp]]
- **Steganographic QR Code POC (2025)**: Explored hiding messages within QR code error-correction capacity. Completed POC, presented findings, identified limitations (conversion breaks steganography).

### Infrastructure Security
- **HashiCorp Vault Integration (2024)**: First adoption in Merquri Frontend for secret management in fullstack application. [[2024-01-fullstack-new138-solo]]
- **AWS Role Assuming (2024)**: Implemented secure role-based access for AWS services.
- **Dependency Bot (2025)**: Automated security patch maintenance — 90% effort reduction, eliminates vulnerability backlog accumulation. [[2025-01-dependency-bot-90pct-reduction]]

### Authentication & Access
- Identified and documented weaknesses in existing fingerprint-based bot detection (client-side only, no server validation).
- Evaluated agent-level authentication mechanisms for NL platform (IP whitelisting, API unique fields, token authentication).

## Related Projects
- [[National Lottery Platform]]
- [[New138 Fullstack Application]]

## Related Skills
- [[Solution Architecture]]
- [[Distributed Systems]]
