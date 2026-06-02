# NestJS

## Definition
NestJS is a TypeScript-first Node.js backend framework using Angular-inspired architecture: decorators, dependency injection, modules, controllers, and services. It is the primary backend framework used in the Community Chat Application.

## Hands-On Experience

### Community Chat Application (2026)
**Role:** Architect and team technical lead
- Built the NestJS application foundation from scratch — module structure, controller/service separation, dependency injection wiring, guard configuration.
- Integrated WebSocket gateways for real-time messaging.
- Wired Valkey Pub/Sub and BullMQ queues into the NestJS service layer.
- Performed complex architectural changes directly in the codebase; not a hands-off reviewer.
- Applied Multi-Agent Audit workflow to validate architectural changes before production merge.
- [[2026-02-community-chat-nestjs-team-lead]] | [[Community Chat Application]]

## Patterns Applied
- **Modules**: Feature-based module organisation for clean separation of concerns
- **Controllers**: Route handling with TypeScript decorators
- **Services**: Business logic encapsulation; injected via DI
- **Guards**: Auth and access control via `@UseGuards`
- **WebSocket Gateways**: Real-time bidirectional communication integrated with Valkey Pub/Sub
- **Interceptors / Pipes**: Request validation and transformation

## Context
NestJS was selected for Community Chat because:
- TypeScript-first — aligns with team's existing TypeScript conventions
- Opinionated structure reduces architectural decision fatigue for a small team
- Well-documented DI system makes testing and maintainability straightforward
- Mature WebSocket support via `@nestjs/websockets`

## Related Skills
- [[NodeJS Fullstack]]
- [[Technical Leadership]]
- [[Solution Architecture]]

## Related Projects
- [[Community Chat Application]]
