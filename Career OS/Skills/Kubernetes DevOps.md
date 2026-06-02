# Kubernetes & DevOps

## Definition
Container orchestration, CI/CD pipeline setup, infrastructure automation, and cloud deployment management.

## Key Demonstrations

### Kubernetes (K8s)
- **Horizontal Pod Autoscaling (HPA)**: Configured and load-tested HPA for NL betting system; confirmed scaling behaviour triggers correctly under ramp-up load — [[2025-01-performance-testing-improvements]]
- **Pod Right-Sizing**: Proposed 3-pod isolation architecture (customer-facing / backoffice / blockchain retry) for NL platform to eliminate cascading failures — [[2026-03-right-sizing-microservices]]
- **Deployment**: Containerised New138 fullstack application for Kubernetes deployment — [[2024-01-fullstack-new138-solo]]
- **Monitoring**: Used Prometheus and Kubernetes Dashboard to diagnose CPU/memory spikes during incidents — [[2026-03-right-sizing-microservices]]

### Docker
- Dockerised production full-stack application (New138) for K8s deployment
- Dockerised local development infrastructure — single command to spin up full local stack — [[2024-01-fullstack-new138-solo]]
- Code Push Server: helped APP Team with dockerisation and testing

### CI/CD Pipelines
- **GitLab CI**: Set up automated frontend test runner; coverage badge updates on every push/MR (2022) — [[2022-09-frontend-unit-testing]]
- **GitLab Pipeline Migration**: Migrated from Jenkins git polling to GitLab runner curling Jenkins build URL (2023) — easier to identify which Jenkins each codebase is linked to
- **Jenkins (Groovy)**: Built new frontend Jenkins pipeline; migrated older DevOps features (2021) — [[2021-01-coin-backoffice-rewrite]]
- **Dependency Bot**: Automated GitLab workflow for security patch maintenance (2025) — [[2025-01-dependency-bot-90pct-reduction]]
- **Node Version Upgrade**: Orchestrated upgrade of all Jenkins-built repositories across team (2023)

### Cloud Infrastructure
- **AWS RDS**: Production database setup and configuration for NL platform and New138
- **AWS EKS**: Kubernetes cluster for NL platform
- **AWS S3**: Used in NL blockchain failure storage design
- **Elastic Beanstalk**: Replaced hundreds of instances with single full-stack app — [[2024-01-fullstack-new138-solo]]
- **HashiCorp Vault**: Integrated for secret management in production fullstack app (2024)

## Related Projects
- [[National Lottery Platform]]
- [[New138 Fullstack Application]]

## Related Skills
- [[Distributed Systems]]
- [[Performance Engineering]]
- [[NodeJS Fullstack]]
