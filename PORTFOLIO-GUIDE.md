# Portfolio Presentation Guide

This guide provides a concise route through the portfolio for technical interviews, client meetings and short demo recordings.

## Recommended Order

1. **Fuse 7 to Camel 4 Migration** - the migration approach and the evidence that behaviour did not change
2. **Camel Integration Hub** - system integration and operational recovery
3. **OrderFlow Events** - event-driven architecture and delivery guarantees
4. **ServiceDesk Cloud Platform** - microservices, observability and cloud delivery
5. **FreelanceFlow API** - secure business workflows and backend engineering
6. **LogScope Desktop** - local Java desktop development and usability

## Two-Minute Project Demos

### Fuse 7 to Camel 4 Migration

**Show:** the Blueprint route next to the Camel 4 XML route, one golden-file scenario, and the CI run where the legacy and the modern implementation pass the same eight scenarios.

**Explain:** behaviour is frozen in scenarios before anything is migrated. The contracts and XSLT mappings move unchanged; only what Camel 3/4 and Quarkus force is changed, and each change is listed in the migration guide.

**Technical choice:** the equivalence scenarios are the point. They caught a regression a code review would miss: Apache HttpClient 5 retries `503` by itself, doubling the calls to a failing downstream system on top of Camel's redelivery policy.

### FreelanceFlow API

**Show:** sign in, create a customer and project, register time, approve entries and generate an invoice.

**Explain:** this is not only CRUD. The value is in the workflow, role-based authorization, audit trail and generated invoice document.

**Technical choice:** Keycloak keeps identity concerns outside the application while Spring Security enforces permissions at the API boundary.

### OrderFlow Events

**Show:** submit an order, follow its event history, trigger a recoverable failure and inspect the outbox or dead-letter state.

**Explain:** the database update and outbox record are committed together. A scheduled publisher sends the event to Kafka, while idempotent consumers protect against duplicate delivery.

**Technical choice:** at-least-once delivery with idempotency is explicit and testable; claiming exactly-once processing across every boundary would be misleading.

### Camel Integration Hub

**Show:** import REST or CSV data, display the canonical order, trigger a failed downstream delivery and reprocess it from the dashboard.

**Explain:** different input formats enter reusable Camel routes and are normalized before delivery. Failed messages remain available after restart and can be reprocessed operationally.

**Technical choice:** Apache Camel is appropriate because routing, transformation and error handling are the central problem rather than incidental HTTP plumbing.

### ServiceDesk Cloud Platform

**Show:** create a technician and ticket, run automatic assignment, inspect the notification and open the Grafana dashboard or distributed trace.

**Explain:** the services own separate data and communicate through resilient clients. Metrics and traces make both successful and degraded behavior visible.

**Technical choice:** the project includes Docker Compose for local use, Kubernetes manifests for orchestration and Terraform for repeatable Azure infrastructure.

### LogScope Desktop

**Show:** open a log file, filter by level and time, inspect a stacktrace, save a filter and export the result.

**Explain:** logs remain local, large files are processed asynchronously and the application can be packaged as a Windows desktop application.

**Technical choice:** JavaFX fits an offline, privacy-sensitive tool that needs native file access without a backend service.

## Interview Structure

Use the same four-part explanation for each project:

1. **Problem:** what operational or business issue does this solve?
2. **Design:** what are the important boundaries and data flows?
3. **Failure:** what happens when a dependency, broker or message fails?
4. **Trade-off:** what would change in a production implementation?

Avoid listing frameworks without context. Connect each technology to a requirement or risk.

## LinkedIn Project Summary

> Built a Java integration portfolio around realistic operational problems, led by a Red Hat Fuse 7 to Camel 4 on Quarkus migration in which the old and the new implementation pass the same golden-file scenarios. Further projects cover Apache Camel integrations with persistent recovery, Kafka event processing with a transactional outbox, resilient cloud-native microservices and secured workflow APIs. Each repository includes automated tests, CI and documented architecture.

## CV Summary

**Selected engineering portfolio:** migrated a Fuse 7 (Camel 2, Blueprint, Karaf) integration to Camel 4 on Quarkus and OpenShift with equivalence tests; designed and implemented Java 21 and Spring Boot solutions covering OAuth2 security, workflow modelling, Kafka event processing, transactional outbox and idempotency, Apache Camel integration patterns, microservices, observability, Docker, Kubernetes, Terraform, Azure and JavaFX desktop packaging.

## Recording Checklist

- Record at 1080p with only the relevant application and terminal visible.
- Keep each recording between 90 seconds and 3 minutes.
- Start with the business problem, then demonstrate one normal flow and one failure or recovery flow.
- End on the architecture diagram, test result or observability view.
- Do not expose tokens, passwords, personal data or unrelated applications.
