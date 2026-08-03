# Canonical Blueprint 033

## The Application Architecture

| Record | Details |
|---|---|
| Blueprint number | 033 |
| Status | Canonical |
| Date established | August 3, 2026 |
| Authority | Project Genesis |
| Steward | Merchay Global Vision |
| Scope | LearningOS application composition, module boundaries, dependency direction, use cases, ports, adapters, cross-cutting capabilities, delivery surfaces, and evolution |
| Purpose | Define how LearningOS domain capabilities, events, interfaces, data, and infrastructure compose into an evolvable application. |

---

## Purpose and Authority

The Application Architecture defines the structural bridge between LearningOS domain and event models and the specialized frontend, backend, database, API, AI, and workflow architectures that implement them.

This reconstruction restores the missing canonical position after Domain-Driven Architecture and Event-Driven Architecture and before the frontend and backend blueprints. It establishes application-wide boundaries and dependency rules; Blueprints 034 and 035 provide the detailed client and service architectures.

> "A coherent application is built from explicit boundaries, stable contracts, and purposeful composition."

---

## 1. Why Application Architecture Matters

LearningOS combines identity, learning journeys, knowledge, projects, assessment, evidence, mentorship, AI, analytics, organizations, governance, and ecosystem capabilities. Without an application architecture, those capabilities can become tightly coupled through shared tables, framework conventions, implicit state, and direct calls that make every change risky.

Application architecture matters because it:

- Turns bounded contexts into composable application modules
- Keeps business rules independent of delivery frameworks
- Defines where orchestration belongs
- Makes dependencies visible and enforceable
- Supports web, API, agent, workflow, and administrative surfaces
- Preserves tenant, authorization, privacy, and audit boundaries
- Allows asynchronous collaboration without hiding outcomes
- Supports modular-monolith delivery and responsible extraction
- Makes testing, observability, migration, and recovery architectural concerns

---

## 2. Canonical Application Model

```text
Delivery Surfaces
        ↓
Interface Adapters
        ↓
Application Use Cases
        ↓
Domain Modules
        ↓
Ports and Contracts
        ↓
Infrastructure Adapters
        ↓
Data, Events, AI, and External Systems
```

Delivery surfaces receive intent. Interface adapters translate transport-specific input. Application use cases coordinate authorized work. Domain modules enforce business meaning and invariants. Ports declare required capabilities without binding the core to implementations. Infrastructure adapters connect those ports to persistence, events, models, files, queues, and external services.

Dependencies point inward toward application and domain contracts. Infrastructure may implement a core port; the core must not depend on a vendor adapter.

---

## 3. Architectural Layers

### Delivery Layer

Web routes, APIs, commands, scheduled triggers, workflows, and agent tools authenticate requests, validate transport shape, establish execution context, and invoke application use cases. They do not own domain policy.

### Application Layer

Application services express use cases, coordinate transactions, load domain state, invoke authorized domain behavior, publish outcomes, and return stable results. They should remain thin enough that domain rules are not duplicated across interfaces.

### Domain Layer

Domain entities, value objects, policies, services, and events express business meaning. A domain owns its invariants and vocabulary and does not reach directly into another domain's storage.

### Contract Layer

Commands, queries, events, ports, schemas, and error models define explicit interaction boundaries. Contracts are versioned and governed according to their audience and compatibility commitments.

### Infrastructure Layer

Repositories, databases, queues, caches, model providers, search engines, file stores, notification systems, and third-party integrations implement ports. They are replaceable details with observable failure behavior.

---

## 4. Module Boundaries

Each application module should have a named owner, public entry points, private implementation, owned data, emitted events, consumed contracts, authorization rules, operational objectives, and tests that protect its boundary.

Modules may collaborate through:

- Synchronous commands when an immediate authoritative result is required
- Queries when reading an approved projection or public view
- Domain events inside an owned consistency boundary
- Integration events across bounded contexts
- Workflows for long-running, multi-step, recoverable coordination

Direct access to another module's private tables, internal classes, or mutable state is prohibited.

---

## 5. Use Cases and Execution Context

Every use case should make the actor, tenant, purpose, authorization, inputs, idempotency expectation, transaction boundary, outputs, emitted events, and audit consequences explicit.

The execution context carries authenticated identity, active tenant, delegated authority, correlation identifiers, locale, privacy constraints, and request provenance. Context must be established at a trusted boundary and must not be reconstructed from untrusted payload fields deeper in the application.

---

## 6. Commands, Queries, and Events

Commands request an authorized change and may be rejected. Queries retrieve state without changing domain meaning. Events state facts that have occurred. Keeping these roles distinct improves naming, authorization, caching, retries, testing, and observability.

Command handlers must not disguise unbounded workflows. Query paths must not bypass privacy and tenancy. Event consumers must be idempotent where delivery can repeat and must expose retries, dead letters, and recovery state.

---

## 7. Data and Transaction Boundaries

A module owns its write model and protects invariants within an explicit transaction boundary. Cross-domain atomic transactions should be avoided. When work spans domains, the initiating module commits its authoritative state and uses durable events or workflows to coordinate subsequent outcomes.

Read models may combine approved data for a user experience, but they do not become alternate authorities. Derived projections must identify freshness, source, tenant scope, and rebuild strategy.

---

## 8. Cross-Cutting Capabilities

Identity, authorization, tenant context, policy enforcement, validation, audit, observability, localization, feature control, privacy, rate limits, and resilience apply across modules. They should be delivered through shared contracts and platform services without allowing a universal utility layer to absorb domain decisions.

Cross-cutting enforcement should occur at deliberate boundaries and remain visible in tests and telemetry.

---

## 9. Deployment Topology

LearningOS should begin with a modular monolith where that topology provides speed and operational clarity. Modular does not mean unstructured: boundaries, contracts, data ownership, and dependency rules apply from the beginning.

A module may be extracted into a service when evidence shows a need for independent scale, reliability, security isolation, data residency, release cadence, or team ownership. Extraction must preserve contracts and observability and must not be used to repair boundaries that were never defined.

---

## 10. Reliability and Failure Semantics

Every boundary must define timeout, retry, idempotency, cancellation, compensation, fallback, and user-visible failure behavior. Optional downstream work must not invalidate a completed authoritative transaction. Critical incomplete work must remain discoverable and recoverable.

Correlation and causation identifiers should connect interface requests, use cases, domain changes, events, workflows, and external calls without exposing sensitive data.

---

## 11. Security and Privacy

The application architecture enforces least privilege, deny-by-default authorization, tenant isolation, input validation, secret isolation, safe output handling, auditability, and data minimization. Authorization must be checked at the use-case and resource boundary, not inferred from interface visibility.

AI and extension execution are untrusted capabilities until constrained by explicit permissions, tools, budgets, data scopes, and approval requirements.

---

## 12. Testing Strategy

Testing should include:

- Domain tests for invariants and policies
- Use-case tests for orchestration and authorization
- Contract tests for ports, APIs, and events
- Adapter integration tests with real protocol behavior
- Boundary tests that prevent forbidden dependencies
- Tenant and privacy isolation tests
- Workflow recovery and idempotency tests
- End-to-end tests for critical learner outcomes
- Migration and backward-compatibility tests
- Performance and failure-injection tests at material boundaries

The test portfolio should make architectural erosion visible before deployment.

---

## 13. Observability

Observability should follow business operations across layers. Logs, metrics, traces, audit records, and domain outcome measures must share stable correlation while respecting privacy. Teams should be able to distinguish user error, policy denial, domain conflict, dependency failure, capacity pressure, and unknown fault.

Operational dashboards should align with module ownership and critical journeys rather than only infrastructure components.

---

## 14. Evolution Rules

Application evolution must preserve:

1. Domain ownership and vocabulary
2. Inward dependency direction
3. Explicit public contracts
4. Tenant and authorization context
5. Auditable state transitions
6. Compatibility during migration
7. Recoverable data and event changes
8. Historical evidence and provenance

Framework changes should be isolated to delivery or infrastructure wherever possible. Breaking contracts require explicit versioning, migration, communication, and retirement plans.

---

## 15. Recommended Repository Shape

```text
src/
├── application/
│   ├── modules/
│   ├── contracts/
│   └── shared-kernel/
├── interfaces/
│   ├── web/
│   ├── api/
│   ├── agents/
│   └── workflows/
├── infrastructure/
│   ├── persistence/
│   ├── events/
│   ├── ai/
│   └── integrations/
└── tests/
    ├── architecture/
    ├── contracts/
    └── journeys/
```

The exact directories may evolve. Separation of responsibilities and enforceable dependency direction are permanent.

---

## Permanent Principles

> "A coherent application is built from explicit boundaries, stable contracts, and purposeful composition."

> "Business meaning belongs in the domain, not in the framework."

> "Modules own their rules and data; contracts connect them."

> "Topology may evolve without dissolving boundaries."

> "Every critical operation must be authorized, observable, and recoverable."

---

## Canonical Status

Canonical Blueprint 033 is the authoritative Project Genesis reference for LearningOS application composition. Frontend, backend, service, database, API, workflow, AI, kernel, and deployment architectures must preserve its boundaries, contracts, dependency direction, and evolution rules.
