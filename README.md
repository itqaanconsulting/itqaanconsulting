![Hani El Amam - Senior Java Software Engineer](assets/hani-el-amam-banner.png)

**Senior Java Integration Engineer | Apache Camel & Red Hat Fuse | Amsterdam**

I am a freelance Java developer and technical consultant with more than 11 years of experience in complex enterprise environments. I specialise in **system integration with Apache Camel and Red Hat Fuse**, Spring Boot and Quarkus backends, and **migrating Fuse 7 integrations to Camel 4 on OpenShift**.

Fuse 7 is out of support since June 2026. I help teams move their integrations to the Red Hat build of Apache Camel without changing behaviour: freeze what the integration does in automated scenarios first, then migrate, and prove the result passes the same scenarios.

I also connect legacy systems to AI agents safely: an integration layer that exposes an existing SOAP system through MCP, with authorisation per agent, purpose binding, PII redaction and an audit trail enforced in the gateway rather than in the prompt.

Available for freelance assignments in Java integration, Fuse-to-Camel migration, backend modernization and AI-agent integration.

## Expertise

| Area | Technologies and skills |
| --- | --- |
| Integration | Apache Camel 2/3/4, Red Hat Fuse 7, Camel Quarkus, enterprise integration patterns, Kafka, ActiveMQ Artemis / AMQ, JMS |
| Migration | Fuse 7 (Karaf, Blueprint) to Camel 4 on Quarkus or Spring Boot, javax to jakarta, OpenShift |
| Messages and contracts | SOAP / CXF, WSDL, XSD, XSLT (Saxon), XML, JSON, SFTP |
| Backend development | Java 21, Spring Boot, Quarkus, REST APIs, microservices, JPA, Hibernate |
| AI integration | Model Context Protocol (MCP) servers with Spring AI, agent governance, data minimisation for LLMs |
| Security and privacy | OAuth2, OpenID Connect, JWT, Keycloak, GDPR purpose binding, NIS2 / Cyberbeveiligingswet, SBOM and dependency scanning |
| Data | PostgreSQL, Microsoft SQL Server, MongoDB, Flyway |
| Cloud and delivery | Docker, Kubernetes, OpenShift, Terraform, Azure, CI/CD |
| Engineering | Domain modelling, automated testing, observability, resilience |
| Consultancy | Requirements analysis, impact analysis, technical design, process optimization |

## Portfolio

### [Fuse 7 to Camel 4 Migration](https://github.com/itqaanconsulting/fuse7-to-camel4-migration)

A logistics integration as it runs on Red Hat Fuse 7 (Camel 2.23, Blueprint, Karaf), migrated to Camel 4 on Quarkus for OpenShift. Both versions run the same golden-file scenarios; the build fails if they differ.

**Demonstrates:** Fuse 7 to Camel 4 migration, Blueprint to XML IO DSL and CDI, Config Admin to MicroProfile Config, AMQ/JMS, SOAP via CXF, XSD validation, XSLT 3 mapping, idempotent consumer, retries and dead letter queues, health probes, Prometheus metrics, Kustomize manifests and a written [migration guide](https://github.com/itqaanconsulting/fuse7-to-camel4-migration/blob/main/docs/MIGRATION.md). The equivalence scenarios caught a real regression: HttpClient 5 retrying on its own and doubling the calls to a failing downstream system.

[![Migration build](https://github.com/itqaanconsulting/fuse7-to-camel4-migration/actions/workflows/build.yml/badge.svg)](https://github.com/itqaanconsulting/fuse7-to-camel4-migration/actions/workflows/build.yml)

### [Agent-ready Legacy](https://github.com/itqaanconsulting/agent-ready-legacy)

A Java gateway that lets AI agents use a legacy municipal case system (SOAP) safely, through MCP for agents and REST for internal applications. The rules are enforced in the gateway: an agent only gets the tools and purposes it is registered for, never sees personal data, is rate limited, and every call lands in an audit trail without case content.

**Demonstrates:** Spring Boot 4 and the Spring AI MCP server, OAuth2 scopes per agent, deny-by-default agent registry, purpose binding, PII redaction, audit trail on PostgreSQL with Flyway, hardened SOAP client (timeouts, XXE-safe parsing), Bucket4j rate limiting, end-to-end tests with a real MCP client, a Python demo agent, Docker Compose, a [threat model](https://github.com/itqaanconsulting/agent-ready-legacy/blob/main/docs/threat-model.md) mapped to NIS2, and an SBOM scanned in CI.

[![Agent-ready Legacy build](https://github.com/itqaanconsulting/agent-ready-legacy/actions/workflows/build.yml/badge.svg)](https://github.com/itqaanconsulting/agent-ready-legacy/actions/workflows/build.yml)

### [Camel Integration Hub](https://github.com/itqaanconsulting/camel-integration-hub)

Integration hub that accepts REST, CSV and SFTP input, normalizes it to a canonical model and delivers it to an external HTTP API.

**Demonstrates:** Apache Camel, enterprise integration patterns, canonical data transformation, idempotent receiver, retries for HTTP and transport failures, persistent dead-letter handling, manual reprocessing and WireMock integration tests.

[![Camel build](https://github.com/itqaanconsulting/camel-integration-hub/actions/workflows/build.yml/badge.svg)](https://github.com/itqaanconsulting/camel-integration-hub/actions/workflows/build.yml)

[![Camel Integration Hub dashboard](https://raw.githubusercontent.com/itqaanconsulting/camel-integration-hub/main/docs/dashboard.png)](https://github.com/itqaanconsulting/camel-integration-hub)

### [OrderFlow Events](https://github.com/itqaanconsulting/orderflow-events)

Event-driven order processing platform using Kafka for asynchronous lifecycle execution.

**Demonstrates:** Kafka producers and consumers, transactional outbox with `SKIP LOCKED` for multiple instances, idempotency, retries, dead-letter topics, Testcontainers and failure recovery.

[![OrderFlow CI](https://github.com/itqaanconsulting/orderflow-events/actions/workflows/ci.yml/badge.svg)](https://github.com/itqaanconsulting/orderflow-events/actions/workflows/ci.yml)

[![OrderFlow Events demo](https://raw.githubusercontent.com/itqaanconsulting/orderflow-events/main/docs/images/orderflow-demo.png)](https://github.com/itqaanconsulting/orderflow-events)

### [ServiceDesk Cloud Platform](https://github.com/itqaanconsulting/servicedesk-cloud-platform)

Cloud-native service desk implemented as three independently deployable Spring Boot microservices.

**Demonstrates:** microservice boundaries, resilient service communication with idempotency keys for safe retries, assignment notifications, PostgreSQL, distributed tracing, Prometheus, Grafana, Docker, Kubernetes, Terraform and Azure Container Apps.

[![ServiceDesk build](https://github.com/itqaanconsulting/servicedesk-cloud-platform/actions/workflows/build.yml/badge.svg)](https://github.com/itqaanconsulting/servicedesk-cloud-platform/actions/workflows/build.yml)
[![Terraform](https://github.com/itqaanconsulting/servicedesk-cloud-platform/actions/workflows/terraform.yml/badge.svg)](https://github.com/itqaanconsulting/servicedesk-cloud-platform/actions/workflows/terraform.yml)

### [FreelanceFlow API](https://github.com/itqaanconsulting/freelanceflow-api)

Secured administration platform for customers, projects, time entries, approvals and invoice generation.

**Demonstrates:** REST API design, workflow-oriented domain modelling, Keycloak security, role-based authorization with segregation of duties, audit logging with the acting user, concurrency-safe invoice numbering, PDF generation, PostgreSQL and Flyway.

[![FreelanceFlow CI](https://github.com/itqaanconsulting/freelanceflow-api/actions/workflows/ci.yml/badge.svg)](https://github.com/itqaanconsulting/freelanceflow-api/actions/workflows/ci.yml)

## Professional Approach

- Build maintainable solutions around clear domain and service boundaries.
- Treat validation, security, observability and failure handling as part of the design.
- Communicate technical trade-offs clearly to developers and non-technical stakeholders.
- Improve existing systems pragmatically instead of rewriting without a business reason.
- Migrate with evidence: capture current behaviour in tests before changing the runtime.

## Background

- MSc Econometrics, University of Amsterdam
- Experience in government and commercial enterprise environments
- Languages: Dutch, English and Arabic
- Based in Amsterdam, the Netherlands

## Contact

For freelance Java integration, Camel or Fuse migration assignments: [itqaan.consulting.nl@gmail.com](mailto:itqaan.consulting.nl@gmail.com)

For a guided overview, see the [portfolio presentation guide](PORTFOLIO-GUIDE.md).
