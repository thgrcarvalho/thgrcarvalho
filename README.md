### Hi, I'm Thiago

Senior Java / Spring Boot engineer based in Rio de Janeiro. I work on backend systems for payments and fintech — the kind of code where a duplicate request costs real money and a silent failure turns into a reconciliation ticket at 3am.

### What I'm building in the open

- **[pix-payload](https://github.com/thgrcarvalho/pix-payload)** — A zero-dependency Java library for encoding and decoding Pix QR Code payloads (EMV-QRCPS-MPM). Handles the CRC16/CCITT-FALSE computation, EMV TLV structure, and BCB Pix extensions. Built because the existing options were either heavyweight or got the CRC wrong.

- **[pix-key-validator](https://github.com/thgrcarvalho/pix-key-validator)** — Zero-dependency Java library for validating all five Pix key types: CPF (with check digits), CNPJ (with check digits), email (BCB 77-char limit), phone (E.164), and EVP (UUID v4). Auto-detects the type from the input format.

- **[pix-webhook-validator](https://github.com/thgrcarvalho/pix-webhook-validator)** — Zero-dependency Java library for securing incoming Pix webhook requests. Combines HMAC-SHA256 signature verification, IP allowlist with full CIDR matching, and timestamp replay protection. Builder API, works with any HTTP framework.

- **[spring-boot-starter-outbox](https://github.com/thgrcarvalho/spring-boot-starter-outbox)** — Spring Boot starter implementing the transactional outbox pattern. Writes events to a DB table in the same transaction as business data, then a background poller delivers them. Uses `SELECT FOR UPDATE SKIP LOCKED` for safe multi-instance polling. At-least-once delivery.

- **[spring-boot-starter-idempotency](https://github.com/thgrcarvalho/spring-boot-starter-idempotency)** — A Spring Boot starter that adds idempotency to any controller method with a single `@Idempotent` annotation. Caches responses keyed by `Idempotency-Key` header, never caches 5xx, pluggable storage backend (in-memory default, bring your own Redis).

- **[spring-boot-starter-rate-limit](https://github.com/thgrcarvalho/spring-boot-starter-rate-limit)** — A Spring Boot starter that adds token-bucket rate limiting to any controller method with a single `@RateLimit` annotation. Per-IP or per-IP+path key strategies, configurable window, pluggable backend.

- **[pix-subscriptions](https://github.com/thgrcarvalho/pix-subscriptions)** — A recurring-billing service on top of Pix, built in Spring Boot with a hexagonal architecture. JWT auth, daily billing scheduler, EfiBank gateway adapter, webhook receiver for payment confirmation.

- **[spring-boot-starters-examples](https://github.com/thgrcarvalho/spring-boot-starters-examples)** — A runnable service showing all four starters working together: `@Idempotent` prevents duplicate payments, `@RateLimit` guards the auth endpoint, outbox publishes events atomically, webhook validator secures Pix callbacks. One command to run.

### What I care about

- **Correctness over cleverness.** Payment code fails on the edges: expired tokens, concurrent retries, partial writes. I'd rather have a boring, well-tested integration than a smart one that's hard to reason about at 2am.
- **Hexagonal architecture and ports-and-adapters.** Keeping domain logic independent of Spring, JPA, HTTP, and whatever's trendy next quarter.
- **Tests that mirror production.** Testcontainers, real Postgres, integration tests over mocks. I've been burned by mock/prod divergence enough times.

### Tech

Java 21 · Spring Boot 3 · Gradle · PostgreSQL · Flyway · Testcontainers · JUnit 5

### Elsewhere

- Email: thgrcarvalho@gmail.com
