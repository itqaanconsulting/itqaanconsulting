# Portfolio Presentation Guide

This guide provides a concise route through the portfolio for technical interviews, client meetings and short demo recordings.

## Recommended Order

1. **FreelanceFlow API** - secure business workflows and backend engineering
2. **OrderFlow Events** - event-driven architecture and delivery guarantees
3. **Camel Integration Hub** - system integration and operational recovery
4. **ServiceDesk Cloud Platform** - microservices, observability and cloud delivery
5. **LogScope Desktop** - local Java desktop development and usability

## Two-Minute Project Demos

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

> Built a five-project Java portfolio focused on realistic business and operational problems: secured workflow APIs, Kafka-based event processing with a transactional outbox, Apache Camel integrations with persistent recovery, observable cloud-native microservices, and a packaged JavaFX log-analysis desktop application. Each repository includes automated tests, CI and documented architecture and demo scenarios.

## CV Summary

**Selected engineering portfolio:** designed and implemented Java 21 and Spring Boot solutions covering OAuth2 security, workflow modelling, Kafka event processing, transactional outbox and idempotency, Apache Camel integration patterns, microservices, observability, Docker, Kubernetes, Terraform, Azure and JavaFX desktop packaging.

## Recording Checklist

- Record at 1080p with only the relevant application and terminal visible.
- Keep each recording between 90 seconds and 3 minutes.
- Start with the business problem, then demonstrate one normal flow and one failure or recovery flow.
- End on the architecture diagram, test result or observability view.
- Do not expose tokens, passwords, personal data or unrelated applications.
