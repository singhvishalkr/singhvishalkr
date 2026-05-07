# Vishal Kumar Singh

Senior software developer at **MakeMyTrip**. I work on the B2B corporate-travel backend **Quest2Travel (Q2T)** in Java 21 and Spring Boot 4: a multi-module BFF, REST surface across several verticals, and the operational work that keeps releases boring for callers (correct HTTP semantics, stable contracts, observable failures).

---

## Current focus

Platform work sits next to product delivery: framework upgrades, secret-manager abstraction, tracing and metrics, security hygiene (cookies, dependency surfaces), and CI time. The recurring goal is the same release shape after each jump: callers keep their contracts; operators get clearer signals.

---

## Q2T platform arc (internal refs)

**Framework**

| Cut | Summary |
| --- | --- |
| Quarkus 3.7 → Spring Boot 3.5.8 | Spring MVC, SpringDoc OpenAPI, logging and status-code behaviour aligned with expectations; CI runtime improved materially on the pipeline path we owned. `Corp-Q2T-CBackend#520` |
| Spring Boot 3.5.8 → 4.0.x (Spring Framework 7, Jackson 3) | Modular starters (`webmvc`, `jackson`, `webmvc-test`), Kotlin 2.2.x, SpringDoc 3.0.x, virtual threads, RFC 9457 Problem Details, JDK `HttpClient` where OkHttp left the supported path, JAX-RS bridge removed with Jersey stack out; test suite held green through the cut. `Corp-Q2T-CBackend#604` |

**Cloud and secrets**

| Piece | Idea |
| --- | --- |
| GCP Secret Manager behind `ISecretManager` | Same interface as AWS callers already used; provider becomes a deployment concern, not an API fork. `Corp-Q2T-Common#24` (merged) |
| `gcpConfig.enabled` toggle + reload path | Flip provider per environment without rewriting call sites. `Corp-Q2T-CBackend#632` |
| AWS Secrets Manager `EnvironmentPostProcessor` in shared starter | Secrets resolve before `@Value` hydration for any Boot app on that starter. `q2t-app-common-revamp#3` |

**Observability**

DataDog APM wired with actuator probes so traces, metrics, and logs line up with runtime health. `Corp-Q2T-CBackend#614` (Q2T-2533).

**Security and dependency posture**

Wiz-driven cleanup on high-severity transitives; cookie handling hardened with Spring `ResponseCookie` (SameSite and redirect flows); JAX-RS / Jersey removals shrink the classpath and remove a long-lived adapter layer. Cross-refs: `#577`, `#601`–`#604`, `#605`–`#613`, `#635`, and related cookie PRs.

**Document Management Service**

Greenfield BFF in the same org: Maven reactor, `q2t-common-s3` starter (S3 surface + auto-config), presigned upload/download, tenant model (`group` / `corp`), lifecycle states, later phases for audit, scanning, events, search, retention, tags, and a client SDK. PRs span `q2t-app-common-revamp` and `q2t-app-dms` (e.g. Q2T-2555).

**Recent product-facing work (sampler)**

Cookie redirection, CDRI destination search, approval flows, trip-extension flows, personal-booking nudge, room pax distribution, partner markup rollout; each landed as scoped PRs with the usual review and regression gates.

---

## Before MakeMyTrip  -  Comviva (Tech Mahindra), fintech

High-volume API gateway work across many regions: Java 8 / Spring Boot 2 carried forward to Java 21 / Spring Boot 3.3 with controlled cutovers; Redis on a hot path pulled latency down on measured percentiles; Kafka replaced synchronous fan-out where events were the clearer boundary.

---

## Stack

Java 21 · Spring Boot 4 · Spring Framework 7 · Jackson 3 · Kafka · Redis · PostgreSQL · MongoDB · Elasticsearch · Kubernetes · Docker · AWS (Secrets Manager, ECR, S3) · GCP Secret Manager · Consul · Jenkins · GitHub Actions · Testcontainers · OpenAPI 3 · Datadog · Prometheus · Grafana · Jaeger · JUnit 5 · Mockito

---

## How I prefer to ship

- **RFC-first** for cross-cutting behaviour (error payloads, cookie semantics, retries) so the code change has a short spec to argue with.
- **Behaviour-preserving migrations** where the external API is the constraint; internal package moves are fair game once tests and contracts say yes.
- **Thin boundaries at integration points** so cloud providers and HTTP stacks can move without rewriting domain code.

---

## Open source

Contributions are spread across JVM infrastructure, CNCF-adjacent docs and tooling, and product docs where accuracy matters for developers integrating the project. Examples include Apache Pulsar (including a broker logging fix carried across release branches), Quarkus guides, Spring Security docs, Camunda Zeebe, Apache Pinot, LlamaIndex, Confluent Parallel Consumer, Kubernetes website, Lima, Linkerd website, Meshery, and sustained documentation work on projects such as Strapi and others in the integration ecosystem.

I keep a curated index in **[singhvishalkr/oss-contributions](https://github.com/singhvishalkr/oss-contributions)** for anyone tracing PR history across repos.

---

## Writing

Technical notes on [Medium](https://medium.com/@vishal.kr.singh), including a long-form walkthrough of Java 21→25 and Spring Boot 3.5→4.0 migration tradeoffs that attracted a wide readership; I treat articles as a place to pin decisions that would otherwise live only in chat logs.

---

## Featured repo

[**Teapot-as-a-Service**](https://github.com/singhvishalkr/teapot-as-a-service)  -  Spring Boot microservice that implements HTTP 418 per RFC 2324. [DEV April Fools 2026 write-up](https://dev.to/singhvishalkr/i-built-a-production-grade-microservice-that-does-absolutely-nothing-8fb).

---

## Contact

| | |
| --- | --- |
| **Open to** | Senior SDE / SDE-II / staff-track roles in NL · DE · IE · UK · SG · SE; strong India roles |
| **Time zone** | IST (UTC+5:30), overlap-friendly with EU and UK |
| **Languages** | English (professional), Hindi (native) |
| **Work authorization** | Indian citizen; open to relocation and visa sponsorship where offered |
| **Email** | vishal.kr.singh2021@gmail.com |

**Links:** [LinkedIn](https://www.linkedin.com/in/singhvishalkr/) · [Medium](https://medium.com/@vishal.kr.singh)
