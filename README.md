# Vishal Kumar Singh

Senior Software Developer, **MakeMyTrip**.

Backend engineer on **Java 21** and **Spring Boot 4.0** (Spring Framework 7, Jackson 3), shipping the B2B corporate-travel stack **Quest2Travel (Q2T)**: a multi-module BFF, **11 controllers / 80+ REST endpoints**, five verticals, enterprise bookings, **99.9% uptime** on the surfaces we own.

Platform migrations and NFRs sit in the same lane as features: framework jumps, secret-manager pluggability, observability, security posture, error contracts, CI hygiene, and releases that keep consumer contracts stable.

---

## Platform arc on Q2T (internal PR refs)

### Framework

| Cut | What landed | Evidence |
| --- | --- | --- |
| **Quarkus 3.7 → Spring Boot 3.5.8** | Spring MVC, SpringDoc OpenAPI, logging restored, HTTP-status correctness, Wiz transitive fixes; **CI ~20 min → ~8 min** | `Corp-Q2T-CBackend#520` |
| **Spring Boot 3.5.8 → 4.0.4 + SF7 + Jackson 3** | Modular starters (`webmvc`, `jackson`, `webmvc-test`), Kotlin **2.2.20**, SpringDoc **3.0.2**, virtual threads on, **RFC 9457 Problem Details**, JDK `HttpClient` where OkHttp3 left the stack in SF7, `JaxRsResponseConverter` removed, Jersey stack out; **218 tests** green | `Corp-Q2T-CBackend#604` |

The Boot 4 cut landed net **−587 lines** while adding migration work: Phase 9 alone removed a **124-line** bridge and shed **~15** transitive JARs from the JAX-RS / Jersey path.

### Cloud / secrets

| Change | What it brings | Evidence |
| --- | --- | --- |
| **GCP Secret Manager** module behind `ISecretManager` | Google as a peer to AWS without leaking SDK types at call sites | `Corp-Q2T-Common#24` *(merged)* |
| **`gcpConfig.enabled` toggle with hot-reload** in CBackend | Flip provider per environment from Consul without redeploy; kill-switch back to AWS | `Corp-Q2T-CBackend#632` *(in flight)* |
| **AWS Secrets Manager `EnvironmentPostProcessor`** in `q2t-app-common-revamp` | Secrets resolve before any `@Value`; any Boot app on the starter gets the same ordering | `q2t-app-common-revamp#3` |

### Observability

**DataDog APM** (`Q2T-2533`): first-class traces / metrics / logs alongside Boot 4 actuator probes. `Corp-Q2T-CBackend#614`.

### Security posture (NFR as routine)

| Theme | Shipped | Evidence |
| --- | --- | --- |
| **Wiz CVE clean-up** | High-severity transitives closed (Netty, Commons Lang3, Guava, Kotlin) | `#577`, `#601`, `#603` |
| **Cookie hardening** | `SameSite=Lax` via Spring `ResponseCookie`; redirection-cookie correctness | `#605` / `#609` / `#611` / `#612` / `#613`, `#635` |
| **Bridge & dependency removal** | JAX-RS / Jersey JARs out (~**15** transitives gone); smaller artifact, fewer CVE surfaces | `#604` (Phase 9) |

### Document Management Service (Quest2Travel org)

BFF bootstrapped end to end:

- Multi-module Maven reactor, **`q2t-common-s3` Spring Boot starter** (full S3 surface + auto-configuration), DBA-owned DDL, **presigned URL upload/download**, `group=schema + corp=column` model, **PENDING / UPLOADED** lifecycle with `confirm-upload`, structured object keys.
- Phase 2–3: audit, scan, events, search, expiry, retention, tags, plus a client SDK.
- PRs: `q2t-app-common-revamp#1`–`#8`, `q2t-app-dms#1`–`#3` (**Q2T-2555**).

### Recent product features (sampler, merged)

Cookie redirection (`#635`) · CDRI destination search (`#621`) · Approval flow (`#587` / `#588`) · Trip extension (travel dates / time / destination) (`#551`–`#574`, `#592` / `#593`) · Personal booking nudge (`#529` / `#538`) · `roomPaxDistribution` (`#607` / `#608`) · Maruti asterisk-mark rollout (`#619`).

---

## Before MakeMyTrip — Comviva (Tech Mahindra), fintech

- **3.5 M+** API requests / day, **100+** countries.
- **Java 8 / Spring Boot 2 → Java 21 / Spring Boot 3.3** zero-downtime upgrade.
- **~40%** lower **p95** after a **Redis** hot-path cache on the measured endpoints.
- **Kafka** event pipeline replacing synchronous fan-out where events were the better boundary.

---

## Stack

Java 21 · Spring Boot 4 · Spring Framework 7 · Jackson 3 · Kafka · Redis · PostgreSQL · MongoDB · Elasticsearch · Kubernetes · Docker · **AWS** (Secrets Manager, ECR, S3) · **GCP** (Secret Manager) · Consul · Jenkins · GitHub Actions · Testcontainers · OpenAPI 3 · **Datadog** · Prometheus · Grafana · Jaeger · JUnit 5 · Mockito

---

## How I work

- **RFC-first** for cross-cutting choices (RFC 9457 errors, cookie semantics, retry policy).
- **Behaviour-preserving migrations:** framework jumps ship without changing the public API contract for downstream consumers when that is the bar.
- **Pluggable boundaries:** GCP Secret Manager landed behind the same `ISecretManager` surface AWS already used; flip a flag, no caller rewrite.
- **Lean diffs:** the Boot 4 migration removed adapter layers and classpath noise while keeping the suite green (figures above).

---

## Writing

**7** articles on [Medium](https://medium.com/@vishal.kr.singh). The pinned piece walks **Java 21 → 25** and **Spring Boot 3.5 → 4.0** migration; reach on that order of **12K+ views / 7K+ reads / 290+ claps** (a crude signal of who clicked, not a verdict on depth).

---

## Open source

**100+** author-visible PRs across **25+** projects. Samples that have stable public URLs:

- **Apache Pulsar** — broker log-level fix `#25558` cherry-picked to **4.0 / 4.1 / 4.2** release lines; doc/admin `#25556`; **10** merged on `pulsar-site`.
- **Quarkus** — `quarkusio/quarkus#53988` merged (OIDC providers guide).
- **Spring Security** — `#19143` open (CORS Javadoc clarification).
- **Camunda Zeebe**, **Apache Pinot**, **LlamaIndex** (`#21431` merged, `lgtm`), **Confluent Parallel Consumer**.
- **CNCF** — `kubernetes/website`, `lima-vm/lima`, `linkerd/website`, `meshery/meshery`.
- **Docs / product surfaces** — Strapi (Documentation Contribution Program), Directus, Bagisto, Kilo-Org/kilocode, DagsHub, Appwrite, PostHog, Mattermost, Gatsby, Promptfoo.

Full curated index: **[singhvishalkr/oss-contributions](https://github.com/singhvishalkr/oss-contributions)**.

---

## Featured repo

[**Teapot-as-a-Service**](https://github.com/singhvishalkr/teapot-as-a-service) — Spring Boot microservice that serves HTTP **418** per RFC 2324. [DEV April Fools 2026](https://dev.to/singhvishalkr/i-built-a-production-grade-microservice-that-does-absolutely-nothing-8fb).

---

## Talk to me

| | |
| --- | --- |
| **Open to** | Senior SDE / SDE-II / staff-track in **NL · DE · IE · UK · SG · SE**; MAANG-tier and similar in **India** |
| **Time zone** | IST (UTC+5:30), EU / UK-flexible overlap |
| **Languages** | English (professional), Hindi (native) |
| **Authorization** | Indian citizen; open to relocation and visa sponsorship |
| **Email** | vishal.kr.singh2021@gmail.com |

**Links:** [LinkedIn](https://www.linkedin.com/in/singhvishalkr/) · [Medium](https://medium.com/@vishal.kr.singh) · [GitHub](https://github.com/singhvishalkr)
