# Vishal Kumar Singh

Backend and platform engineer at **MakeMyTrip**. Primary ownership is **Quest2Travel (Q2T)**, a B2B corporate-travel **Java** stack: **Spring Boot 4** on **Spring Framework 7**, **Jackson 3**, **Java 21**, a multi-module BFF, **11 controllers**, **80+ REST endpoints**, **five verticals**, enterprise booking flows, and **99.9% uptime** on the surfaces we run.

Those numbers are the fixed footprint: API breadth and reliability targets do not reshuffle when product priorities change. What changes is how much of the week goes to **net-new behaviour** versus **keeping the platform honest** (versions, CVEs, secrets, traces, HTTP semantics, CI).

## What the day job actually is

**Platform work is recurring, not a one-off migration story.** Spring/Jackson generation moves, dependency and scanner hygiene, AWS and GCP secret resolution behind one interface, Datadog APM next to actuator probes, RFC 9457-shaped errors, cookie and redirect correctness, build pipeline time. That sits beside feature delivery on the same services. If your mental model is “migration is something you touch once and reflect on,” this role is the opposite: the stack moves continuously and the job is to ship upgrades **without** breaking consumer contracts.

## Earlier: Comviva (Tech Mahindra), fintech

**3.5M+** API requests per day, **100+** countries. Carried **Java 8 / Spring Boot 2** forward to **Java 21 / Spring Boot 3.3** with controlled cutovers. **Redis** on a hot path for a large **p95** drop on measured endpoints. **Kafka** where synchronous fan-out stopped scaling.

## Stack

Java 21 · Spring Boot 4 · Spring Framework 7 · Jackson 3 · Kafka · Redis · PostgreSQL · MongoDB · Elasticsearch · Kubernetes · Docker · AWS (Secrets Manager, ECR, S3) · GCP Secret Manager · Consul · Jenkins · GitHub Actions · Testcontainers · OpenAPI 3 · Datadog · Prometheus · Grafana · Jaeger · JUnit 5 · Mockito

## Open source

**100+** author-visible PRs across **25+** upstream repositories (cumulative). Representative work:

- **Apache Pulsar** — broker logging **#25558** carried across **4.0 / 4.1 / 4.2** release lines; **#25556** and related; **10** merged PRs on **`apache/pulsar-site`**
- **Quarkus** — **`quarkusio/quarkus#53988`** merged (OIDC providers guide)
- **Spring Security** — **`#19143`** open (CORS Javadoc clarification)
- **Camunda / Zeebe**, **Apache Pinot**, **Confluent Parallel Consumer**, **LlamaIndex** (**`run-llama/llama_index#21431`** merged)
- **CNCF / platform** — **`kubernetes/website`**, **`lima-vm/lima`**, **`linkerd/website`**, **`meshery/meshery`**
- **Docs and product surfaces** — **Strapi** (documentation + core fixes), **Bagisto**, **Kilo-Org/kilocode**, **PostHog**, **Mattermost**, **Appwrite**, **Gatsby**, **Promptfoo**, **DagsHub**, and others

Full cross-repo listing (repos, themes, representative PRs): **[singhvishalkr/oss-contributions](https://github.com/singhvishalkr/oss-contributions)**.

## Writing

**7** articles on [Medium](https://medium.com/@vishal.kr.singh). The pinned migration piece (**Java 21 → 25**, **Spring Boot 3.5 → 4.0**) has on the order of **12K+ views**, **7K+ reads**, **290+ claps** (reach metrics only).

## Side project

[**Teapot-as-a-Service**](https://github.com/singhvishalkr/teapot-as-a-service) — HTTP **418**, RFC 2324. [Write-up on DEV](https://dev.to/singhvishalkr/i-built-a-production-grade-microservice-that-does-absolutely-nothing-8fb).

---

**Reach:** [vishal.kr.singh2021@gmail.com](mailto:vishal.kr.singh2021@gmail.com) | [LinkedIn](https://www.linkedin.com/in/singhvishalkr/) | IST (EU / UK overlap works)

Open to senior backend / platform-heavy roles in India and selective **NL · DE · IE · UK · SG · SE** hubs; relocation and sponsorship when the fit is real.
