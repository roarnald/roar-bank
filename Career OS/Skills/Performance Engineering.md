# Performance Engineering

## Definition
Designing, measuring, and improving system performance — including frontend rendering, backend throughput, database query efficiency, and infrastructure scaling.

## Key Demonstrations

### Load & Performance Testing
- **NL Betting System Performance Test Plan (Oct 2025)**: Designed and executed a comprehensive performance test plan as Solutions Architect. [[2025-01-performance-testing-improvements]]
  - Tools: JMeter (load generator), Kubernetes Dashboard, Prometheus metrics
  - Methodology: Ramp-up-and-hold, burst testing, stress testing
  - Test cases: BR-V2-001 (600 TPS target), BR-001/002, HR-A-001 through HR-A-006
  - Total bets processed: 150,879 in 24-minute ramp test
  - Verified HPA triggering and horizontal scaling behavior

### Performance Improvements Achieved
- **NL Betting System (2025)**: 20–60% response time improvement; throughput from <2000 to 3500+ bets/sec (+75%)
  - Merged 4 pre-call APIs into 1 placeBet endpoint (75% API call reduction)
  - Database indexing on draw_date filter
- **IPA Dashboard (2023)**: Lighthouse performance score 60+ → 99 (removed unused packages, rewrote legacy code)
- **Coin Backoffice (2021)**: State change latency from several seconds → near-instant
- **Safepay/DYH-VN**: Eliminated SSR-only pages; SSG reduced server load significantly
- **Vite Chunking Solution (2024)**: Reduced first-load JS bundle by resolving library chunk bloat [[2024-01-vite-solutions-year-old-problem]]

### Frontend Performance Patterns
- Unnecessary render reduction (state management optimization)
- Code splitting via Vite/Webpack
- SSG/ISR rendering strategy selection
- MDX for content pages (reduced development time, no runtime overhead)
- Dependency bot to maintain library currency (security + performance)

### Infrastructure Scaling
- **Horizontal Pod Autoscaling (HPA)**: Configured and validated for NL system; confirmed scaling behavior under load
- **Batched API Requests (2026)**: Throttled Kaleido blockchain requests to prevent pod exhaustion [[2026-03-right-sizing-microservices]]
- **Redis caching**: Pod-to-pod state sharing without database round-trips [[New138 Fullstack Application]]

## Related Projects
- [[National Lottery Platform]]
- [[New138 Fullstack Application]]
- [[Coin Backoffice]]

## Related Skills
- [[Solution Architecture]]
- [[Kubernetes DevOps]]
- [[Frontend Architecture]]
