# STAR Interview Stories

*All stories sourced from verified appraisals and solution proposals — no fabrication.*
*Format: Situation · Task · Action · Result*

---

## 1. "Tell me about a time you disagreed with a stakeholder and pushed back."
**Source:** Coin Backoffice Rewrite (2021) | [[2021-01-coin-backoffice-rewrite]]
**Best for:** Technical leadership, conviction, ownership

**S** — I was appointed as the sole frontend developer for CASH-V2 (Coin), the company's new cash management backoffice. The Product Manager's directive was clear: fork the existing legacy repository and make minimal changes to hit production as fast as possible.

**T** — My task was to lead and deliver the back-office portion of this product. But having reviewed the legacy codebase, I assessed that following the PM's direction would produce an unscalable foundation that would accumulate debt faster than we could address it — pages on the original system took seconds to register a state change.

**A** — I made the decision to scrap 95% of the forked repository and rewrite it from scratch, which I then communicated clearly with the reasoning: an updated, well-written foundation was non-negotiable for any future scaling. I designed the team's first Lerna monorepo, upgraded all major packages, built dynamically shared components (e.g., Company Settings reused as Product Settings — cutting future development time by half), and implemented performance-optimised state management. I delivered the full feature set including Role Management, Company Settings, VIP Management, and more.

**R** — Pages that previously took several seconds to respond became near-instant. Coin Backoffice became the benchmark quality codebase in Merquri Frontend. The monorepo pattern was adopted on subsequent projects. My co-appraiser wrote: *"He has displayed outstanding leadership skills during the COIN project, proving to us that he has the potential and is ready to take up more responsibility in leading the team."*

---

## 2. "Tell me about a time you delivered under extreme pressure."
**Source:** Safepay Phase 1 — 36 hours (2022) | [[2022-06-safepay-36hr-delivery]]
**Best for:** Execution under pressure, stakeholder management, resilience

**S** — Safepay was a new payment and withdrawal system I was building as the sole frontend developer. During the planning phase, Frontend was given a 2-week window for Phase 1. However, due to compounding delays from backend and other upstream teams, when Frontend's turn came, approximately 36 hours remained before the client deadline.

**T** — Deliver all Phase 1 requirements for Safepay on time, as the sole developer, without compromising quality or cutting corners that would hurt maintainability.

**A** — Tsai Yu (our Frontend Lead) joined to assist with a few features. Together, we worked extended overtime. Rather than cutting scope, I maintained the architecture I had designed from scratch — pnpm monorepo, React 18, React Router v6, CSS-in-JS with custom animations, mobile-responsive single-component design (no desktop/mobile duplication), and a modal built from scratch. I also coordinated feature alignment across 8+ backend developers in parallel. I had pre-implemented developer experience tooling (API auto-called on dev server start; `.http` files for manual API calls) that paid off during the crunch.

**R** — All Phase 1 features were delivered within the 36-hour window. The client deadline was met. Joanne (PM, appraiser) said: *"This has also shown that you are able to perform when under tremendous pressure."* Safepay became one of the most modern and well-architected codebases in the team's portfolio.

---

## 3. "Tell me about a time you drove significant organisational change."
**Source:** UIUX Team Merger (2023) | [[2023-01-uiux-team-merger]]
**Best for:** Org design, influence without authority, change management

**S** — For years, Merquri ran two parallel frontend teams: the React/Web Team and a UIUX Team using a legacy HTML/CSS/JS stack. The UIUX Team was responsible for setting up the skeleton of new projects, but their code quality was consistently far below standard. React Team developers had to delete and rewrite significant portions before building features. The gap was widening every year, and it was becoming impossible to find candidates willing to specialise in the legacy UIUX stack.

**T** — I recognised this as a structural problem that, if left unaddressed, would become a permanent drag on productivity, morale, and scalability. I had no formal authority over the UIUX Team.

**A** — I built a business case: the real issue was a market and skills mismatch — modern developers learn React, not vanilla HTML/CSS. I presented this analysis to Frontend Internal Management and proposed dissolving the UIUX Team and merging into a single Web Team. Before proceeding, I committed publicly to one condition: I would individually interview every UIUX developer, and if even one person objected, I would design a custom team structure accommodating them. I interviewed all of them — all approved. I then personally remediated every UIUX repository (10+ codebases): automated workflows that required manual steps, upgraded Node.js and Webpack versions across 4-5 upgrade batches, rewrote all internal dependency sub-projects, and mentored each transitioning developer by pairing them with a seasoned React engineer.

**R** — By Q4 2023, the team operated as a single unified Web Team. **4 additional headcounts** were freed to work on meaningful output instead of legacy maintenance. A structural single point of failure (one UIUX team lead dependency) was eliminated. Joanne: *"Ronald is like the brain and heart of the Frontend team that couldn't live without."* Dominic: *"Consistently demonstrates exceptional productivity... significantly contributing to the enhancement of overall workflow and developer experience."*

---

## 4. "Tell me about a time you solved a technical problem no one else could."
**Source:** Vite Dynamic Import & Chunking Solutions (2024) | [[2024-01-vite-solutions-year-old-problem]]
**Best for:** Technical depth, problem solving, impact as an IC

**S** — As we migrated from Webpack to Vite on two key projects (PNL and Rollball) for faster build speeds, two deep technical issues had been unresolved for approximately a year. No frontend developers, seniors, or leads in the company had found solutions, and no relevant fixes existed online.

**T** — As Software Architect, my role was to unblock the team on issues they couldn't resolve themselves. These two Vite issues were causing production page crashes and performance problems.

**A** — I deep-dived independently into Vite's internal documentation and source code. For the **hash collision issue**: Vite calculates content hashes for built files; I traced the root cause — under certain conditions, a page's hash in Build #5 was identical to Build #6, causing browser caches to serve incorrect files and crash pages. For the **chunking bloat issue**: I identified that Vite's code-splitting mechanism, designed for small-to-medium apps, was bloating the library JS chunk and hurting first-load performance. I designed targeted solutions for both, explained the root cause clearly to the team so they understood rather than just applied the fix, and guided each team to production deployment.

**R** — Both solutions were shipped to production on PNL and Rollball. End-user page crashes were eliminated. First-load performance improved. Joanne (appraiser): *"Ronald is undoubtedly the go-to guru for problem-solving, especially in unique or complex situations."* Dominic: *"If you're facing a niche issue, he's always the go-to person."*

---

## 5. "Tell me about a time you identified and fixed a systemic process problem."
**Source:** Urgency Tagging (2021) | [[2021-11-urgency-tagging-workflow]]
**Best for:** Process improvement, systems thinking, people-first leadership

**S** — During code reviews, a recurring tension was building on our Frontend team. Reviewers would ask leading questions to coach the developer — which was the culture we had built deliberately. But when a developer had an urgent fix, this coaching approach felt obstructive and created mounting pressure.

**T** — Two high-tension incidents occurred. My task as a Senior Software Engineer (not a formal lead) was to investigate and address the root cause before it damaged the team's learning culture.

**A** — I individually interviewed each affected developer to understand the emotional dynamics rather than just the surface complaint. I identified the core problem: a mismatch in information — reviewers couldn't tell if a request was urgent or routine, so they always defaulted to teaching mode. I brought the findings to the Frontend Leads (Tsai Yu, Joanne) and proposed a solution: **Urgency Tagging** — developers could label Merge Requests with an `[Urgent]` tag when genuinely time-pressured. When tagged, reviewers would provide an immediate fix; coaching would be deferred. We strongly encouraged not overusing the tag, to preserve the learning culture. I then conducted a **follow-up feedback session 2 months later**.

**R** — The tag was rarely used — by design. Its existence alone resolved the tension by giving developers a known safety valve. At the follow-up session, most developers reported feeling more at ease with the workflow. The appraiser noted: *"能即時的提出流程的上改進…展現出你能看出流程的瑕疵，並思考改善"* (Able to promptly propose process improvements, demonstrating the ability to identify workflow flaws and think through improvements).

---

## 6. "Tell me about a time you developed someone and they exceeded expectations."
**Source:** Lotto6D NodeJS Mentoring (2025) | [[2025-01-lotto6d-nodejs-mentoring]]
**Best for:** Coaching, talent development, multiplying impact

**S** — The Lotto6D KJW product needed a custom NodeJS microservice to handle API requirements and eliminate reliance on an overseas team. The company had only one person (myself) who had built a production NodeJS application before. I had the option to build it myself — the safest, fastest path.

**T** — Instead, I made the deliberate choice to appoint Jacky, a developer who had never built a server-side application, as the primary developer. My goal was to extend the team's full-stack capability to a second engineer rather than keeping it concentrated in one person.

**A** — I broke the entire feature into bite-sized, sequenced actionable steps that Jacky could follow and study independently. I provided working code samples from my own experience (from the New138 fullstack application), and set up the delivery process to minimise surprises. I was available for blockers and we collaborated to resolve them — but I never took over or solved problems for him. I kept the ownership firmly with Jacky throughout.

**R** — Jacky delivered a production NodeJS microservice independently — his first time in the domain. The overseas team dependency for that product was lifted. After delivery, Jacky voluntarily presented all his learnings to the wider Frontend team during Frontend Sharing, publicly crediting me in the session. I wrote in my appraisal: *"I felt that this provided a huge sense of accomplishment for Jacky as he was able to pick up and deliver in a domain that he has never stepped foot into."*

---

## 7. "Tell me about a time you had to navigate competing priorities and still deliver."
**Source:** Software Architect + Solutions Architect Dual Role (2025) | [[2024-01-fullstack-new138-solo]]
**Best for:** Prioritisation, strategic thinking, operating at altitude

**S** — In March 2025, I was asked to take on the Solutions Architect role for the National Lottery platform concurrently with my Software Architect role for the Frontend team. This meant managing two completely different problem domains simultaneously: one requiring deep frontend architecture knowledge, the other requiring backend infrastructure, security, and system reliability expertise I was still building.

**T** — Deliver value in both roles without dropping either. The SA role brought immediate pressure: system incidents (NLINCIDENT-261 in September 2025), a business trip to Manila, performance testing leadership, and 6 formal solution proposals to draft. The SwA role still required: SA Reviews for new projects, mentoring, security automation, and team leadership.

**A** — I recognised immediately that holding both roles required automating and delegating the repeatable. For SwA: implemented the Dependency Bot (90% reduction in security patching effort), delegated Frontend Sharing and events to senior ICs, created NodeJS Server Templates so others could work independently. This freed bandwidth for SA work. For SA: built relationships with backend and DevOps experts quickly to fill domain gaps; used structured read-backs to validate my understanding; produced all deliverables (proposals, runbooks, test plans, architecture diagrams) in a documented format accessible to the team.

**R** — Both roles delivered measurable outcomes in the same year: 60% response time improvement on NL system; 2 proposals approved at architecture level; team events became self-sustaining; Jacky delivered a production microservice; security patch effort reduced 90%. Joanne: *"Despite having his hands full, he still makes time to take on side quests, helping and guiding others through complex issues, incidents, and architectural design discussions. Whenever there's a problem and we go to Ronald, he never leaves me with any worries."*

---

## 8. "Tell me about a time you handled a production incident."
**Source:** Cascading Failure (NL System, Sep 2025) | [[2025-09-cascading-failure-proposal]]
**Best for:** Incident management, root cause analysis, systemic thinking

**S** — On 9 September 2025, the National Lottery system experienced NLINCIDENT-261: a complete system outage. The Admin Backoffice could not query data, and the Agent Application could not process ticket purchases. All endpoints were unresponsive. Business operations were fully disrupted.

**T** — As Solutions Architect, I was responsible for understanding the root cause and proposing a structural fix to prevent recurrence — not just recovering from the incident.

**A** — I conducted a deep-dive root cause investigation. I traced the full failure cascade: internal DFNN staff were running bots to mass-query report pages → this generated a burst of long-running database queries → the HikariCP database connection pool was fully exhausted → new requests threw `CannotGetJdbcConnectionException` → the error cascaded across all services → full outage. The hotfix (database index on `bet_group_id`) addressed the immediate query but left the architectural vulnerability open. I prepared two proposals: (1) **Cascading Failure Prevention** (Bulkhead + Circuit Breaker, approved 17 September); (2) **Bot Prevention** (hash comparison architecture, 23 September). I also separately identified that the bot activity was the upstream human cause, and proposed that as a second prevention layer.

**R** — The Cascading Failure proposal was formally approved by the Head of Architecture within 5 days. The bot prevention proposal added a technical deterrent layer. The Bulkhead pattern was later extended to Kubernetes pod isolation in the Right-Sizing Microservices proposal (March 2026, also approved). The system remained stable after the hotfix and index optimisation. Kar Wai (co-appraiser): *"Ronald consistently evaluates a wide range of client requirements and assesses multiple potential solutions. He selects and proposes the most appropriate or optimal option."*

---

## 9. "Tell me about a time you led a small engineering team through a technically complex delivery."
**Source:** Community Chat Application — NestJS Team Lead (2026) | [[2026-02-community-chat-nestjs-team-lead]]
**Best for:** Small team EM, engineering standards, hands-on architecture, AI-assisted tooling
**Especially relevant for:** OGP ScamShield (4-engineer team, NestJS stack)

**S** — In early 2026, the Community Chat Application moved from architecture proposal into build. The stack we had designed — NestJS, Valkey Streams, BullMQ, PostgreSQL — was entirely new territory for the team. No one on the team had meaningful NestJS production experience, and there was no dedicated senior reviewer with deep expertise in the framework available.

**T** — Create and lead a small Fullstack JS team to build the application. My role was architectural: set the foundation, make the hard structural calls, and ensure production-grade quality on all architectural changes — without being in day-to-day feature delivery.

**A** — I created the dedicated Fullstack JS team — the first fullstack-specific engineering team at Merquri. I built the NestJS application foundation from scratch: module structure, controller/service patterns, dependency injection configuration, guard setup, WebSocket gateway integration with Valkey Pub/Sub, and BullMQ queue wiring into the service layer. For architectural changes going forward, I developed a **Multi-Agent Audit workflow** — using multiple AI agents in coordinated sequence to evaluate each significant architectural change across four dimensions: correctness, security posture, scalability implications, and NestJS pattern adherence. This replaced what would traditionally require a dedicated senior reviewer in the stack.

**R** — The Fullstack JS team is operational and delivering features on the NestJS foundation. Complex architectural changes are landing in production with confidence. The Multi-Agent Audit process is a repeatable workflow that can be applied to any team working in a new or unfamiliar stack. The team has a clear architecture, clear standards, and can move independently on feature work.

---

## 10. "Tell me about a time you built something from scratch with no prior expertise."
**Source:** New138 Full-Stack Application (2024) | [[2024-01-fullstack-new138-solo]]
**Best for:** Learning agility, ownership, solo delivery

**S** — In 2024, I was asked to build Merquri Frontend's first-ever full-stack production application — a navigation site (New138/138DHW) that would replace hundreds of Elastic Beanstalk instances across different domain variants. The company had no prior full-stack JavaScript experience in the frontend team. I had never built a production server-side Node.js application.

**T** — Design and deliver the full-stack application solo, with some guidance from Tsai Yu (who volunteered as interim NodeJS advisor) and PM Dominic. The system needed to handle real production traffic, be containerised for Kubernetes, manage secrets securely, and be maintainable by others after delivery.

**A** — I chose Astro JS as the framework for its dual-mode capability — one codebase serving both Member and Admin use cases. I taught myself containerisation by Dockerising both the production application and the local development environment. I integrated Redis for inter-pod caching, HashiCorp Vault for secrets management, and built a DB migration process and data migration scripts from scratch. I wrote a custom captcha service resilient to load testing, and established monitoring. Throughout, I documented patterns and best practices so that future developers could build on them. After delivery, I formalised these into a NodeJS Server Template Foundation.

**R** — Delivered ahead of schedule. Replaced hundreds of Elastic Beanstalk instances with a single application — significant infrastructure cost and maintenance reduction. The templates built from the experience were immediately used to accelerate the WeChat Redirect migration. The project directly enabled my promotion to Solutions Architect. Joanne: *"Setting up the full-stack application was an impressive breakthrough."*
