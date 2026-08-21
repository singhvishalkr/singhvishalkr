## Vishal Singh

Backend engineer working on high-throughput distributed systems — Java, Spring Boot, Kafka.
Currently architecting B2B travel platform services at **MakeMyTrip (Quest2Travel)**.

Most of my work is the unglamorous kind: removing single points of failure, making p95 behave,
and moving live platforms between major framework versions without taking them down.

### Open source — 108 merged pull requests

Merged into 45 upstream repositories: **45 code changes and 63 documentation changes** — the
split is worth stating plainly.

The ones I would point at:

| Project | What I changed |
|---|---|
| **[Camunda](https://github.com/camunda/camunda)** (6) | Zeebe broker internals — removed a heap copy from the Raft [snapshot-chunk read path](https://github.com/camunda/camunda/pull/55371), stopped [wrapping broker responses as exceptions](https://github.com/camunda/camunda/pull/55373), added [component health details to the broker health indicator](https://github.com/camunda/camunda/pull/50440), and made [GCS manifest listing retry transient failures](https://github.com/camunda/camunda/pull/55424) |
| **[Apache Pulsar](https://github.com/apache/pulsar)** | [Lowered a broker log level](https://github.com/apache/pulsar/pull/25558) on a not-found path in `DrainingHashesTracker` |
| **[HashiCorp Nomad](https://github.com/hashicorp/nomad)** | [Added `-json` and `-t` output](https://github.com/hashicorp/nomad/pull/27991) to `operator autopilot get-config` |
| **[Flux Flagger](https://github.com/fluxcd/flagger)** | [Run post-rollout hooks when `skipAnalysis` is true](https://github.com/fluxcd/flagger/pull/1918) — progressive-delivery correctness |
| **[OpenTelemetry Collector](https://github.com/open-telemetry/opentelemetry-collector-contrib)** | [Feature gate for the routing connector's default `error_mode`](https://github.com/open-telemetry/opentelemetry-collector-contrib/pull/48433) |
| **[Keycloak](https://github.com/keycloak/keycloak)** | [Linked authentication-flow `UsedBy` clients to client settings](https://github.com/keycloak/keycloak/pull/48841) |
| **[Liquibase](https://github.com/liquibase/liquibase)** | [Treat `'NULL'` as null for MySQL/MariaDB enum column defaults](https://github.com/liquibase/liquibase/pull/7725) |
| **[Dapr](https://github.com/dapr/cli)** | [`--redis-stack` flag on `dapr init`](https://github.com/dapr/cli/pull/1644) for RediSearch support |
| **[Mattermost](https://github.com/mattermost/mattermost)** | [Stopped a message body leaking via the Notifications API tag](https://github.com/mattermost/mattermost/pull/36364) |
| **[Bitwarden](https://github.com/bitwarden/server)** | [Fixed double HTML encoding in emergency-access emails](https://github.com/bitwarden/server/pull/7652) |
| **[Sinon](https://github.com/sinonjs/sinon)** | [Isolated the `callId` counter per sandbox](https://github.com/sinonjs/sinon/pull/2715) so parallel tests don't interfere |
| **[Strapi](https://github.com/strapi/strapi)** (5) | Admin and i18n fixes, including [avoiding buffering large uploads for MIME detection](https://github.com/strapi/strapi/pull/26678) |

Plus documentation volume: Strapi docs (28), the Apache Pulsar site (9), and Kilo Code (10).
Full map, every PR linked: **[oss-contributions](https://github.com/singhvishalkr/oss-contributions)**.

### Day job

- Architected a greenfield **Document Management Service** (Java 21, Spring Boot 4) using
  direct-to-S3 presigned uploads, keeping the application server out of the data path
- Migrated **6 production modules and 80+ endpoints** from Quarkus 3.7 to Spring Boot 4 with zero
  downtime, remediating 7 high-severity CVEs
- Replaced a synchronous fan-out with a **Kafka pipeline across 4 downstream consumers** for 20+
  fintech operators, holding per-entity ordering
- Migrated a legacy service from Java 8 / Spring Boot 2 to Java 21 / Spring Boot 3.3 using
  **OpenRewrite** — code migration in a day, production in a week
- Built a provider-agnostic **secret-management layer** (hexagonal ports and adapters) over AWS
  Secrets Manager and GCP Secret Manager with Consul-driven failover and hot reload

### Writing

Seven architect-level guides on Java and Spring Boot platform work, on
[Medium](https://medium.com/@vishal.kr.singh):

- [Hexagonal Architecture in Spring Boot Microservices: A Practical Guide](https://medium.com/@vishal.kr.singh/hexagonal-architecture-in-spring-boot-microservices-a-practical-guide-with-example-95480050ef08)
- [Spring Boot Anti-Patterns That Cost You Performance, Scale & Credibility](https://medium.com/@vishal.kr.singh/spring-boot-anti-patterns-that-cost-you-performance-scale-credibility-db23d2e8db8c)
- [Java 21 → 25 and Spring Boot 3.5 → 4.0: An Architect's Guide to a Safe Platform Upgrade](https://medium.com/@vishal.kr.singh/java-21-25-and-spring-boot-3-5-4-0-an-architects-guide-to-a-safe-platform-upgrade-c0a206d49034)
- [Spring Boot 4.0 — An Architect's Guide to the Future of Enterprise Java](https://medium.com/@vishal.kr.singh/spring-boot-4-0-an-architects-guide-to-the-future-of-enterprise-java-abd67575f64d)
- [Modernizing Legacy Microservices: Java 8 & Spring Boot 2 → Java 21 & Spring Boot 3.3](https://medium.com/@vishal.kr.singh/modernizing-legacy-microservices-upgrading-from-java-8-spring-boot-2-to-java-21-spring-boot-3-3-c38a2abe728d)

### Mine

- **[oss-contributions](https://github.com/singhvishalkr/oss-contributions)** — map of every merged upstream PR
- **[event-system](https://github.com/singhvishalkr/event-system)** — event-driven service, Spring Boot 3 / Java
- **[e-commerce](https://github.com/singhvishalkr/e-commerce)** — Spring Boot service
- **[sangeet](https://github.com/singhvishalkr/sangeet)** — Python / FastAPI

### Stack

`Java 21` `Spring Boot 3/4` `Quarkus` `Apache Kafka` `Redis` `PostgreSQL` `MongoDB` `MySQL`
`Oracle` `AWS` `GCP` `Consul` `Docker` `Maven` `JUnit 5` `Testcontainers` `Micrometer`
`Prometheus` `Grafana` `ELK` `OpenRewrite`

### Contact

[LinkedIn](https://linkedin.com/in/singhvishalkr) · [Medium](https://medium.com/@vishal.kr.singh) · vishal.kr.singh2021@gmail.com