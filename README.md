### Hi, I'm Thiago

Senior Java / Spring Boot engineer based in Rio de Janeiro. I work on backend systems for payments and fintech — the kind of code where a duplicate request costs real money and a silent failure turns into a reconciliation ticket at 3am.

### What I'm building in the open

- **[pix-payload](https://github.com/thgrcarvalho/pix-payload)** — A zero-dependency Java library for encoding and decoding Pix QR Code payloads (EMV-QRCPS-MPM). Handles the CRC16/CCITT-FALSE computation, EMV TLV structure, and BCB Pix extensions. Built because the existing options were either heavyweight or got the CRC wrong.

- **[spring-boot-starter-idempotency](https://github.com/thgrcarvalho/spring-boot-starter-idempotency)** — A Spring Boot starter that adds idempotency to any controller method with a single `@Idempotent` annotation. Caches responses keyed by `Idempotency-Key` header, never caches 5xx, pluggable storage backend (in-memory default, bring your own Redis).

- **[pix-subscriptions](https://github.com/thgrcarvalho/pix-subscriptions)** — A recurring-billing service on top of Pix, built in Spring Boot with a hexagonal architecture. Models trainers, students, plans, subscriptions, and payments. WIP, but it's the larger canvas where I explore the domain.

### What I care about

- **Correctness over cleverness.** Payment code fails on the edges: expired tokens, concurrent retries, partial writes. I'd rather have a boring, well-tested integration than a smart one that's hard to reason about at 2am.
- **Hexagonal architecture and ports-and-adapters.** Keeping domain logic independent of Spring, JPA, HTTP, and whatever's trendy next quarter.
- **Tests that mirror production.** Testcontainers, real Postgres, integration tests over mocks. I've been burned by mock/prod divergence enough times.

### Tech

Java 21 · Spring Boot 3 · Gradle · PostgreSQL · Flyway · Testcontainers · JUnit 5

### Elsewhere

- Email: thgrcarvalho@gmail.com
