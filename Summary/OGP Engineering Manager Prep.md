# OGP Engineering Manager Prep — ScamShield

**Role:** Software Engineering Manager, ScamShield
**Company:** Open Government Products (OGP), Singapore
**JD:** https://careers.open.gov.sg/o/software-engineering-manager-scamshield

---

## Role at a Glance

ScamShield is Singapore's national anti-scam platform. S$1.1 billion was lost to scams in 2024. The team is small and cross-functional: 4 engineers, 1 PM, 1 UX designer, operations partners. The EM leads technical direction, hires and manages the engineers, partners with the PM on strategy, and builds relationships with Singapore Police Force and the Anti-Scam Centre.

**Key distinction from a typical EM role:** OGP explicitly requires hands-on production code shipped in the last 12 months. This is a player-coach role, not a people manager who left the code behind.

**Primary stack:** TypeScript, React, NestJS, AWS, PostgreSQL
**Plus:** OpenSearch, ML classifiers, anti-fraud / trust and safety domain

---

## Fit Assessment

### Strong Fit

| JD Requirement | Your Evidence | Why not 5★ | Strength |
|---------------|--------------|------------|---------|
| Lead engineering team, set technical direction | SA Review process, Coin rewrite, 6 SA proposals, Vite solutions | — | ★★★★★ |
| Hands-on production code (last 12 months) | **Community Chat NestJS architecture shipped to production last month (May 2026). App going live this week.** Also: Licensing/translation feature (5 repos, 2025), Dependency Bot, Project Fortuna | — | ★★★★★ |
| NestJS + Node.js backend | **Built NestJS architecture for Community Chat (2026)** — module structure, DI, WebSocket gateways, Valkey Pub/Sub. Created and led dedicated Fullstack JS team. | — | ★★★★★ |
| Hire, onboard, manage engineers | Team grown 5→30; Buddy System; IC roles; Mid-year appraisals; UIUX transition coaching | No documented formal hiring loop ownership (sourcing, panel design, offer). All leadership was people development, not structured recruiting. | ★★★★☆ |
| React + TypeScript + AWS | Deep React expertise; AWS (RDS, EKS, S3, CloudFront) on New138 + NL; TypeScript in NodeJS templates | AWS depth is architect-level awareness, not hands-on DevOps. TypeScript used in templates and Astro, but not the dominant language across all listed work. | ★★★★☆ |
| Partner with PM on strategy and metrics | 6 years working with Joanne + Dominic; Action Plan group; perf test objectives designed | All PM partnership is within a single company and known colleagues. No evidence of navigating ambiguous product strategy with a new PM in a new organisation. | ★★★★☆ |
| Cross-functional stakeholder management | DFNN Manila; Aquarix; Kar Wai; CTO group; UIUX merger cross-team influence | Government/police stakeholder relationship (SPF, ASC) is new territory. Prior external experience is a government-contracted client, not a government partner agency you need to co-build with. | ★★★★☆ |
| PostgreSQL | New138 (migration scripts, schema design); **Community Chat production schema live** — going live this week | Schema design and migrations are solid. No documented deep query optimisation, query planning, or performance tuning at high data volume. | ★★★★☆ |
| Deliver difficult feedback, own hard conversations | UIUX merger individual consultations; conflict mediation; Urgency Tagging | Self-identified conflict-avoidance flaw documented in 2025 appraisal. Most listed examples are process changes or de-escalation, not direct one-on-one performance conversations with a clear negative message. | ★★★☆☆ |

### Gaps to Acknowledge and Address

| Gap | Mitigation |
|-----|-----------|
| **ML classifiers / OpenSearch** | No direct production ML experience. Frame via: (a) POC mindset (Steganographic QR POC, Mixpanel integration with Data Science team), (b) architectural thinking for data pipelines, (c) *willingness to work alongside engineers with deeper domain expertise* — which OGP explicitly values. |
| **Anti-fraud / trust & safety domain** | Closest: Bot Prevention proposal (preventing scripted API abuse); Digital Signature for ticket fraud detection; OWASP security checklist. The domain is adjacent; the security-first thinking transfers. |
| **Public sector / government context** | NL (LottoMatik) is a government-contracted national lottery — closest you have. DFNN is a government client. Frame as: experience delivering to government stakeholders with high reliability and compliance requirements. |
| **Small team EM (3-8)** | ~~Concern~~ **Not a gap.** Leading a small Fullstack JS team right now; shipped to production last month; going live this week. Say: "I'm not moving toward this model — I'm in it." |
| **Conflict avoidance (self-identified 2025)** | This is a growth area you've documented. Don't hide it — OGP values honesty. Frame as: "I've identified it, sought counseling, and actively worked on it. Here's a specific example of how I handled a hard conversation this year." |

---

## What OGP Will Probe — Prepared Answers

### Probe 1: Technical Leadership

*"Tell me about a time you defined the architecture direction for a team."*

**Best answer:** Coin Backoffice Rewrite (2021) → SA Review Process (2024)

Use the arc: junior engineer who challenged a PM decision on architecture (Coin) → Lead who instituted an architecture review gate for all new projects → Architect who designs system-wide solutions approved at CTO level.

**Specific talking points:**
- Coin: Overrode PM's "minimal fork" directive. Full rewrite from scratch. First monorepo at Merquri. Near-instant vs. seconds load time.
- SA Review: Proposed in 2023 appraisal, implemented in 2024. Applied to 3 projects before a line of feature code was written.
- NL: Cascading failure root cause analysis → Bulkhead + Circuit Breaker proposal approved. Then extended the same pattern to Kubernetes pod orchestration (Right-Sizing Microservices, also approved).

*"Tell me about a technical migration you led."*

**Best answers (pick one):**
- **UIUX Team merger + repo remediation (2023):** Migrated 10+ legacy repositories from a manual-build, single-branch, Webpack 4 workflow into modern CI/CD, proper branching, Webpack 5 — across 4-5 batches, with a team member. The technical migration was the prerequisite for the org change.
- **Node.js version upgrade orchestration (2023):** Worked with Hau Cherng to upgrade every single Jenkins-built repository. Many needed Webpack 4 → 5 rewrites due to config syntax incompatibilities.
- **WeChat Redirect legacy migration (2024):** Used the NodeJS Server Templates from New138 to guide a developer in rewriting a legacy service into a modern Kubernetes-deployed NodeJS application.

*"Tell me about a time you established engineering standards."*

**Best answers:**
- Unit testing: First in team; 86% coverage; GitLab CI; 3 test types; guided adoption across repos. Before this — zero automated testing in Frontend.
- Code review culture: Championed from early career; set standards; designed Urgency Tagging when tension arose.
- NodeJS Server Templates (2024): Created reference implementations (TypeScript + plain JS) for future full-stack developers. Immediately used on WeChat Redirect.
- Package manager workflow (2025): Standardised across 30-person team with many conflicting legacy configurations.
- **NestJS standards + Multi-Agent Audit (2026)**: Set up NestJS architecture and patterns for the Community Chat team. Developed a Multi-Agent Audit workflow — coordinating multiple AI agents in sequence to audit architectural changes across correctness, security, scalability, and pattern dimensions — enabling production-grade delivery without a dedicated senior reviewer in the stack. *This is a distinctive, modern answer to an engineering standards question.*

---

### Probe 2: People Leadership

*"Walk me through how you've grown an engineer."*

**Best answer:** Jacky / Lotto6D NodeJS (2025)

Full story in [[STAR Interview Stories]] (Story #6). Key points for OGP context:
- Made a deliberate choice to not build it myself — to extend team capability.
- Broke delivery into sequenced steps; provided working samples; never took over ownership.
- Result: production delivery, public presentation, overseas dependency lifted.
- **OGP angle:** "OGP values engineers who take ownership. I try to create the conditions where my engineers can take that ownership — not by being absent, but by designing the right structure and being present for the hard parts."

*"Tell me about a performance conversation you found difficult."*

**What to say:** Be honest about the conflict-avoidance flaw you identified in 2025. Frame it as a growth example, not a confession:

> "I've been aware for a while that I default to de-escalation over direct confrontation. In 2025, I acknowledged this formally in my appraisal, sought counseling to understand where it came from, and began actively changing the pattern. One concrete thing I changed: I started publicly standing behind my leads in team tensions rather than stepping back and letting them be the bad cop alone. I also worked through a significant inter-developer conflict rather than delegating it. The work isn't done, but I know what I'm working on."

*"How do you run performance management with a small team?"*

- Mid-Year Appraisal cycle (ongoing feedback, not just annual review).
- Anonymous Internal Feedback so team members can give candid input on each other.
- 1:1 coaching check-ins — IC roles gave seniors structured growth with accountability.
- Tracked progress explicitly: *"I kept a Frontend Component Team excel throughout the year, listing all tasks I was doing and going to do."*
- **OGP angle for a 4-person team:** "With a team this small, performance management is mostly real-time coaching, not formal cycles. The leverage is in daily pairing, code reviews with intent, and making sure every engineer has a meaningful technical challenge. I'd also be thinking about what each engineer needs to grow into their next role — retention in government tech is earned, not assumed."

---

### Probe 3: Stakeholder Management

*"Tell me about managing a difficult external stakeholder."*

**Best answer:** DFNN Manila relationship (2025)

Context: DFNN is the Philippine government client for the LottoMatik national lottery. Ronald travelled to Manila, presented Digital Signature and MFA proposals, and received explicit client commendation.

**OGP angle:** ScamShield has SPF (Singapore Police Force) and Anti-Scam Centre as key external partners. Frame your Manila experience as: "I understand what it's like to work with a government agency that has compliance requirements, legacy processes, and non-technical decision-makers. The job is to translate technical proposals into business outcomes they can evaluate."

*"Tell me about a time you had to present a technical tradeoff to non-technical stakeholders."*

**Best answers (pick one):**
- SA proposals: Each formal proposal (Bot Prevention, Cascading Failure, Digital Signature) included a Recommendation section that explained the tradeoff in plain terms — why Solution 1 was chosen over Solution 2, at what cost and what benefit. Approved by Head of Architecture and presented to CTO group.
- UIUX merger: Presented the technical case to Frontend Internal Management — translating "legacy stack technical debt" into "headcount efficiency and hiring risk" for a non-technical audience.
- Community Chat proposal: Evaluated OpenIM (Golang, built for millions) vs NodeJS (familiar stack, sufficient for 1,000 users). Recommended NodeJS not because it's "better" but because it's right for the scale and team capability — framed as a pragmatic decision, not a technical one.

*"Tell me about managing competing priorities across teams."*

**Best answer:** Dual SA + SwA role (2025)

> "In 2025, I held two architect roles concurrently — Software Architect for the frontend team, and interim Solutions Architect for the NL platform. Both had real deliverables with real timelines. The way I handled it was: first, I automated or delegated everything repeatable in the SwA role (dependency bot, IC event ownership, NodeJS templates). That created bandwidth for the SA work. I also made both sets of work visible — I maintained the Action Plan group documentation and kept both PMs informed of my capacity and any risks. The result was measurable outcomes in both roles in the same year."

---

### Probe 4: Operating in Ambiguity

*"Tell me about a time you had to create direction where none existed."*

**Best answer:** Software Architect role creation (2024)

> "When I was appointed as Merquri Frontend's first Software Architect, there was no playbook. No predecessor, no documented scope. The questions I had to answer from scratch: What does this role look like? What value does it add that the Lead doesn't already provide? How should the team dynamics change? I wrote down two mottos to guide myself: 'leader of our leaders' — I'd focus on growing the leads rather than leading directly — and 'sharpest tool in the toolbox' — I'd be the person who solves the problems no one else can. I then built the SA Review process, established myself as the debugging escalation point, and started the first full-stack application. By year-end, the role had a shape that was clearly valued by the team and visible to the CTO."

**Second strong answer:** NL Solutions Architect appointment

> "When I stepped into the SA role for the National Lottery platform, I had limited backend and infrastructure domain knowledge. The system was already in production, the team had better codebase expertise than me, and there were multiple ongoing changes in the early planning phase. Rather than trying to fake domain authority, I was explicit about what I knew and didn't know — I used read-backs to validate my understanding, built relationships with backend and DevOps engineers to fill gaps quickly, and focused on adding value in the areas where I had genuine expertise: system design thinking, stakeholder communication, and architectural pattern selection. Within months I had authored a root-cause analysis of a major production incident and had two architecture proposals approved."

*"Tell me about a time you challenged an assumption."*

**Best answer:** Vite dynamic import issue (2024)

> "The whole team had accepted that the Vite hash collision problem was unsolvable — it had been open for a year. I didn't accept that. I went into Vite's internals myself, traced the hash calculation algorithm, and identified the specific condition that caused the collision. The assumption everyone had was 'this is a Vite bug, we have to wait for them to fix it.' The reality was: it was a deterministic behavior we could work around once we understood it. Shipped to production."

---

### Probe 5: Organisational Impact

OGP is mission-driven. For each major achievement, connect it to *what the organisation gained* — not just what you built.

| Achievement | Org Impact |
|------------|-----------|
| UIUX merger (2023) | **Reduced onboarding complexity** — 4 developers moved from dead-end legacy stack to modern React/Web. Removed single point of failure (UIUX lead dependency). **Freed 4 headcounts** for higher-value work. |
| Dependency Bot (2025) | **Reduced operational overhead by 90%** — eliminated the need for a dedicated security patch resource. Security posture maintained continuously rather than reactively. |
| New138 fullstack (2024) | **Reduced cloud spend** — hundreds of Elastic Beanstalk instances replaced by one application. Reduced maintenance overhead for NOC/DevOps. |
| Unit testing pioneer (2022) | **Reduced production incidents** — automated test suite on every push and MR catches regressions before they ship. |
| NodeJS Server Templates (2024) | **Reduced developer ramp-up time** — WeChat Redirect migration used templates to cut delivery time significantly. Jacky (Lotto6D) used templates to deliver first production Node.js service. |
| Frontend Sharing (2022–2025) | **Improved knowledge sharing** — 4-year programme archived on Notion. Reduced knowledge silos. Blockchain team participated cross-functionally. Extended to Aquarix. |
| SA Review process (2024) | **Reduced technical debt accumulation** — architecture reviewed before significant code written. Prevented the "copy old codebase" pattern. |
| Cascading failure prevention (2025) | **Reduced operational incidents** — proposed structural fix after NLINCIDENT-261. If implemented, prevents recurrence of full system outage. |
| OWASP checklist (2025) | **Improved security posture** — ~10 vulnerabilities identified and patched before external pen test. |
| Barrel import automation (2025) | **Improved developer productivity** — weeks of manual work reduced to hours (90% effort reduction). |

**Framing tip for OGP:** ScamShield's org impact is citizen-level. When you talk about what you've built, connect it to the people it serves — not just the engineering metrics. OGP thinks in terms of *outcomes for Singapore*. Practice connecting your work to end users.

---

## Stack Fit Deep Dive

### TypeScript
- NodeJS Server Template Foundation: explicitly built TypeScript variant (2024).
- Used TypeScript in full-stack Astro JS application (New138).
- All modern JavaScript work at Merquri uses TypeScript; introduced it into team conventions.
- **Claim confidently.**

### React
- 6+ years, deep expertise, multiple production applications.
- Introduced React 18 API patterns, wrote in-house state management service, built complex dynamic UIs.
- **Strongest item on the stack.**

### NestJS
- **Hands-on, production architecture experience.** Built the NestJS application foundation for Community Chat (2026): module structure, controller/service patterns, DI, guard configuration, WebSocket gateways integrated with Valkey Pub/Sub, BullMQ queue wiring.
- Created and led the Fullstack JS team building on this stack.
- Applied Multi-Agent Audit workflow to validate complex architectural changes before merge.
- **Claim this confidently — it is no longer a gap.**

### AWS
- Production experience: RDS, EKS, S3, CloudFront, Elastic Beanstalk (replaced), Kafka (NL platform).
- Designed infrastructure for New138 (Docker + Kubernetes + Redis + Vault on AWS).
- **Solid, but depth is architect-level awareness rather than DevOps hands-on.**

### PostgreSQL
- Used in New138 (DB migration scripts, data migration from old product).
- Designed Community Chat architecture with PostgreSQL/RDS.
- Added indexing optimisations for NL system (draw_date filter).
- **Claim confidently for schema design and migration; less so for deep query optimisation.**

### OpenSearch / ML classifiers
- **Gaps.** Closest experience: Mixpanel integration with Data Science team (2025) — coordinated with data scientists on user behaviour tracking. Steganographic QR Code POC — applied signal/data manipulation concepts.
- **How to address:** "I don't have production OpenSearch or ML classifier experience. What I bring is: the architectural thinking to deploy and operate these systems, a track record of getting productive in new domains quickly (I built a full production fullstack app solo in a domain I'd never worked in), and the humility to work alongside engineers who have deeper domain expertise — which I understand OGP specifically values."

---

## Questions to Ask OGP

### On the Role
1. ScamShield is described as 4 engineers — what does technical growth look like for the team over the next 12-18 months? Are there plans to expand the engineering headcount?
2. What does the current on-call and incident response process look like? How mature is the observability/alerting setup?
3. How technical is the EM expected to be day-to-day — what's the rough split between code/architecture work and people/stakeholder work?

### On the Product and Mission
4. The JD mentions AI-powered detection — can you share more about the ML architecture? Is the classifier in-house or a third-party API, and where is the team looking to invest next?
5. How does the team navigate the tension between moving fast on new features and maintaining the reliability that SPF and ASC depend on?
6. ScamShield deals with sensitive citizen data and SPF coordination — what compliance or regulatory constraints shape your engineering decisions most heavily?

### On OGP Culture
7. For engineers coming from the private sector, what's the biggest adjustment to working within a government product team?
8. OGP emphasises autonomy and testing ideas over debating them — what does that look like concretely for an EM? Are there examples of product or technical bets that failed fast and what happened next?
9. What does success look like in the first 6 months for this role?

---

## STAR Stories Ranked for OGP Fit

| Story | Probe It Answers | OGP Fit |
|-------|----------------|---------|
| **UIUX Merger** | Org change, influence without authority, difficult conversations, org impact | ★★★★★ Best story overall |
| **Dual SA + SwA role** | Ambiguity, competing priorities, working with incomplete info | ★★★★★ Most unique to your profile |
| **Community Chat NestJS team** | Engineering standards, small team EM, hands-on architecture, AI-assisted tooling | ★★★★★ Most relevant to this specific JD |
| **Coin rewrite** | Technical conviction, pushing back, architecture ownership | ★★★★☆ |
| **Jacky / Lotto6D** | Coaching, talent development, multiplying impact | ★★★★☆ |
| **Cascading failure** | Incident management, root cause, systems thinking | ★★★★☆ |
| **New138 fullstack** | Ambiguity, learning agility, hands-on | ★★★★☆ (proves you can still code) |
| **Safepay 36 hours** | Execution under pressure, delivery planning | ★★★☆☆ (shows execution, less EM) |
| **Urgency Tagging** | Systems thinking, process improvement, listening | ★★★☆☆ |
| **Vite solutions** | Technical depth, challenging assumptions | ★★★☆☆ (strong IC story, less EM) |

---

## How to Frame Your Career Narrative for OGP

OGP wants someone who is:
- A **genuine player-coach** (still in the code, not removed from it)
- **Mission-driven**, not purely commercially motivated
- Comfortable in **a small, high-trust, high-ownership team** (very different from leading 30)
- **Humble about domain gaps** but confident about transferable skills

**Your narrative in 90 seconds:**

> "I've been building and leading engineering at Merquri for 6 years — starting as an engineer, growing into a Lead, then a Software Architect, and now concurrently a Solutions Architect. Right now I'm leading a small Fullstack JS team building a NestJS-based community chat application — writing the architecture, making the hard calls on module design and real-time infrastructure, and applying a multi-agent audit process I developed to ensure production quality. Before that I built a full-stack application solo in a domain I'd never touched, which replaced hundreds of cloud instances and shipped ahead of schedule. I've also led a 30-person team, but I've come to find that the small, high-ownership model is where I do my best work. ScamShield caught my attention because the problem is urgent and the stakes are real — S$1.1 billion lost to scams in 2024. I want to build something that protects people, not grows a revenue metric. The stack is familiar, the team model is what I'm already operating in, and the mission is something I can actually care about."

---

## Pre-Interview Preparation Checklist

### Do before the interview
- [ ] Read about ScamShield's public-facing work: scamshield.gov.sg, SPF partnership, recent news
- [ ] Look up OGP engineering blog / talks — understand their engineering culture in their own words
- [ ] Review your PostgreSQL knowledge: migration strategies, indexing, query planning basics
- [ ] Prepare a 2-minute "why OGP and why ScamShield" statement — make it personal and specific
- [ ] Read about OpenSearch and how it's used for document search/similarity — 1 hour of reading is enough to speak to it intelligently

### Know cold (no hesitation)
- [ ] UIUX merger story (full STAR, 3 minutes)
- [ ] Community Chat NestJS team story (engineering standards, small team lead, hands-on architecture)
- [ ] Dual architect role story (competing priorities, ambiguity)
- [ ] Jacky / Lotto6D story (talent development)
- [ ] New138 fullstack story (hands-on, learning agility)
- [ ] Cascading failure incident story
- [ ] Your honest answer on the conflict-avoidance growth area
- [ ] Your "why OGP" statement

### Strengths to emphasise unprompted
- **Still writing production code as an Architect** — NestJS architecture for Community Chat is recent, hands-on, and in a stack directly on the JD. This is your strongest proof point for OGP's player-coach requirement.
- **Multi-Agent Audit workflow** — a modern, distinctive approach to engineering quality. OGP values testing ideas; this is a concrete example of applying AI tooling to a real engineering problem (not just using Copilot for autocomplete).
- **Created a small Fullstack JS team** — directly analogous to ScamShield's 4-engineer model. You have done this recently, not just managed large teams.
- Track record of working in new domains and delivering (SA role, fullstack, security, NestJS)
- Culture systems that outlasted you — Frontend Sharing ran 4 years, extended to external companies without your involvement.

---

## Gap Mitigation Summary

| Gap | What to Say | What to Do |
|-----|------------|-----------|
| NestJS | ~~Gap~~ **Not a gap.** Built NestJS architecture in production. Claim confidently. | Nothing |
| Hands-on code (12 months) | ~~Gap~~ **Not a gap.** Shipped last month; architectural updates lined up; going live this week. | Nothing |
| Small team EM | ~~Gap~~ **Not a gap.** Leading small Fullstack JS team right now, shipping. | Prepare to describe team structure + what "going live" involves |
| ML / OpenSearch | "I work alongside engineers with deeper domain expertise; I bring architectural thinking and a fast ramp-up track record." | 1-hour read on OpenSearch; be able to discuss its role in search/classification |
| Anti-fraud domain | "Adjacent: Bot Prevention, Digital Signature, OWASP checklist. Security-first thinking transfers." | Read 1-2 articles on trust and safety engineering |
| Public sector | "NL platform = government client (DFNN); I understand compliance constraints and high-reliability requirements." | Read about OGP values and past products |
| Conflict avoidance | "I've named it, worked on it, and here's what changed." | Have one concrete example of a hard conversation you did handle well ready |
