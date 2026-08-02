# Canonical Blueprint 032

## The Event-Driven Architecture

| Record | Details |
|---|---|
| Blueprint number | 032 |
| Status | Canonical |
| Date established | August 2, 2026 |
| Authority | Project Genesis |
| Steward | Merchay Global Vision |
| Scope | LearningOS event categories, event bus, publication, schemas, metadata, storage, replay, delivery reliability, security, privacy, and observability |
| Purpose | Define the complete event-driven communication model for LearningOS, including event categories, event bus architecture, event storage, replay strategy, reliability, and observability. |

---

## Purpose and Authority

The Event-Driven Architecture defines how LearningOS domains communicate meaningful facts without surrendering their independence. It establishes a shared language for events, a durable path for publication and delivery, and governed mechanisms for retention, replay, observation, and evolution.

This blueprint applies to domain events, cross-domain integration events, lifecycle signals, operational events, event consumers, event storage, and the LearningOS Event Bus. It complements Domain-Driven Architecture by specifying the collaboration model across bounded contexts and complements API & Integration Architecture by defining the internal event foundation from which approved external delivery may occur.

> "Events preserve the story of a system."

---

## 1. Why Event-Driven Architecture Matters

LearningOS outcomes frequently span domains. A completed project may affect assessment readiness, journey progress, portfolio evidence, analytics, AI context, notifications, and achievements. Requiring the Projects domain to call and understand every downstream system would make one action fragile, slow, and difficult to evolve.

Event-driven architecture matters because it:

- Allows a domain to announce an authoritative fact once
- Lets interested consumers respond independently
- Removes unnecessary temporal coupling from learner transactions
- Isolates failures so optional reactions do not block core outcomes
- Preserves causal history across long-running journeys
- Supports new consumers without modifying the original producer
- Makes asynchronous work, delay, and recovery visible
- Enables analytics and projections from governed facts
- Creates reliable integration points across bounded contexts
- Helps architecture evolve through versioned shared understanding

Events are not a universal replacement for APIs, commands, queries, or transactions. They are appropriate when communicating facts that have already occurred and when consumers can tolerate explicit asynchronous behavior.

---

## 2. The Event Philosophy

LearningOS events follow these principles.

### Facts, Not Instructions

An event uses past-tense business language and states what occurred. It does not secretly command consumers or name the implementation expected to react.

### Meaning Before Transport

The business meaning, owner, schema, privacy classification, and lifecycle of an event exist independently of a broker, queue, database, or cloud provider.

### Producers Own Truth

The producing domain owns the fact and its contract. Consumers own their reactions, projections, and failure handling.

### Contracts Create Shared Understanding

Public event schemas are versioned published language. Consumers depend on documented semantics rather than producer internals.

### Delivery Is Not Processing

The event bus can confirm delivery mechanics, but each consumer must record and expose whether its business reaction succeeded.

### Asynchrony Must Be Visible

Products and operations acknowledge intermediate, delayed, failed, and eventually consistent states instead of pretending every reaction is immediate.

### History Requires Governance

Retention and replay can create value, risk, and cost. Events are stored only for explicit operational, analytical, historical, or legal purposes.

### Failure Is Expected

Duplicates, delay, reordering, transient outages, poison messages, incompatible consumers, and partial progress are normal design conditions.

> "Independent systems collaborate through shared understanding."

---

## 3. The LearningOS Event Bus

The LearningOS Event Bus is the governed asynchronous communication fabric connecting event-producing and event-consuming domains.

```text
LearningOS Event Bus
├── Identity
├── Learning
├── Journey
├── Projects
├── Assessment
├── Portfolio
├── Community
├── AI
├── Analytics
└── Notifications
```

The diagram identifies principal participants, not an exhaustive list and not a declaration that every domain consumes every event.

### Event Bus Responsibilities

The bus provides:

- Authenticated producer and consumer connections
- Authorized topic or stream access
- Durable publication and subscription
- Partitioning and ordering within declared boundaries
- Consumer groups and independent offsets
- Bounded retry and dead-letter routing
- Schema and compatibility integration
- Delivery telemetry, lag, and trace propagation
- Retention enforcement and controlled replay interfaces
- Capacity, quota, and backpressure controls

### Responsibilities Outside the Bus

The bus does not own:

- Domain rules or authoritative state
- Decisions about whether an event should exist
- Consumer business transactions
- End-to-end exactly-once outcomes
- Data consent or lawful purpose
- Cross-domain process meaning
- Permanent historical retention by default

### Topology

Topics or streams are organized around stable domain facts rather than teams, environments, or individual consumers. Naming includes domain and event family, while schema version remains explicit in the envelope or registry.

Consumer groups isolate each logical reaction. A slow analytics consumer must not delay assessment, portfolio, or notification consumers.

### Infrastructure Independence

The canonical envelope, publication contract, consumer behavior, and operational semantics remain provider-neutral. Broker-specific capabilities are accessed through adapters and may not become undocumented business requirements.

---

## 4. Core Event Categories

LearningOS classifies events by meaning, audience, and governance.

### Domain Events

Domain events represent meaningful facts inside a bounded context, such as `ProjectCompleted`, `AssessmentPassed`, or `JourneyGoalChanged`. They may remain internal when no cross-domain contract is required.

### Integration Events

Integration events are stable, privacy-reviewed facts published for other contexts or approved external consumers. They may be derived from internal domain events and contain only the information required for collaboration.

### Process Events

Process events describe milestones in long-running workflows, such as a certification workflow awaiting review, timing out, compensating, or completing. Their owner is the coordinating process, not the domains whose work it invokes.

### Lifecycle Events

Lifecycle events communicate creation, activation, suspension, archival, restoration, deletion, or supersession of governed resources. They support caches, search, projections, and retention workflows.

### Learning Activity Events

Learning activity events describe authorized educational interactions, including lesson engagement, practice, reflection, help requests, and submissions. They require strict purpose, minimization, consent, and retention controls.

### AI Events

AI events describe governed orchestration milestones such as request accepted, agent selected, tool action authorized, response completed, safety intervention, evaluation completed, or memory update applied. Prompts and private content are not included by default.

### Operational Events

Operational events communicate service, deployment, security, data-quality, and recovery conditions. They support operations but do not automatically become business-domain history.

### Audit Events

Audit events preserve security-relevant and governance-relevant actions with stronger integrity, access, and retention requirements. The audit system is purpose-built; an ordinary event stream is not automatically an adequate audit ledger.

### External Events

External events enter through verified integration adapters and anti-corruption layers. Provider payloads are validated, deduplicated, classified, and translated before they influence domain behavior.

Category determines audience, schema review, data classification, retention, transport, observability, replay authority, and expected service level.

---

## 5. Event Flow Examples

A completed project can produce independent cross-domain reactions.

```text
Project Completed
       ↓
Event Published
       ↓
Assessment
       ↓
Portfolio
       ↓
Journey
       ↓
Analytics
       ↓
AI
       ↓
Notifications
       ↓
Achievements
```

The vertical diagram makes the potential outcomes readable; implementation should favor fan-out from the published event where reactions are independent rather than forcing an unnecessary sequential chain.

### Project Completion

The Projects domain validates its invariants, commits the completed state and publication intent, then returns the authoritative outcome to the learner. It does not wait for every downstream reaction.

### Assessment Reaction

Assessment may create or update an eligibility state when the completed project satisfies declared submission requirements.

### Portfolio Reaction

Portfolio may create a private evidence candidate. It must not publish learner work without an explicit learner-controlled action.

### Journey Reaction

Journey may mark a milestone, unlock an eligible next step, or recalculate guidance while preserving learner choice.

### Analytics Reaction

Analytics records an authorized learning fact and updates governed aggregates or recommendations with visible freshness.

### AI Reaction

AI may refresh bounded context or prepare a reflection prompt. It must not copy private project content into unrestricted memory.

### Notification Reaction

Notifications evaluates preference, channel, urgency, locale, and quiet-time policy before sending any message.

### Achievement Reaction

An achievement policy may recognize the outcome if its own rules are satisfied. It does not infer that project completion alone proves every related capability.

Other common flows include identity verification activating onboarding, assessment approval issuing certification, community contribution affecting reputation, and content publication refreshing search. Each flow has an owner and documented consistency expectations.

> "Every meaningful action deserves a meaningful event."

---

## 6. Event Metadata

Every public LearningOS event uses a canonical envelope that separates routing and governance metadata from the domain payload.

### Required Envelope Fields

| Field | Purpose |
|---|---|
| `event_id` | Globally unique, immutable event identity |
| `event_type` | Stable business event name |
| `schema_version` | Contract version used by the payload |
| `occurred_at` | Time the domain fact occurred |
| `published_at` | Time the event entered publication |
| `producer` | Owning domain and producing component |
| `tenant_id` | Authorized organizational boundary where applicable |
| `subject_type` | Kind of resource or actor concerned |
| `subject_id` | Stable subject reference |
| `correlation_id` | Identifier linking an end-to-end journey |
| `causation_id` | Identifier of the command or event that caused this fact |
| `trace_context` | Distributed observability context |
| `data_classification` | Privacy and security handling category |
| `purpose` | Governed reason for processing and publication |
| `payload` | Versioned domain-specific event data |

### Optional Metadata

Region, locale, actor reference, consent reference, source system, partition key, experiment exposure, retention class, and integrity signature may be included when justified by the contract.

### Metadata Rules

- Metadata is not an escape route for ungoverned personal data
- Event identifiers remain stable across retries and replay
- Delivery-attempt identifiers are separate from event identity
- Occurrence time is not replaced by processing time
- Correlation and causation are propagated across consumers
- Tenant and authorization context are validated, not merely trusted
- Payload fields carry clear optionality and semantic definitions
- Unknown fields are handled according to the compatibility contract

### Schema Registry

A source-controlled registry records owner, description, category, schema, examples, classification, retention, topics, consumers, compatibility mode, lifecycle status, and deprecation plan. Automated checks prevent incompatible publication.

---

## 7. Event Store

The Event Store preserves selected events for defined periods and purposes. It is not automatically the authoritative state store for every domain.

### Storage Purposes

Events may be retained to support:

- Delivery recovery within the broker retention window
- Rebuilding approved projections
- Diagnosing incidents and failed workflows
- Verifying cross-domain outcomes
- Auditing governed actions in a suitable audit store
- Producing privacy-approved analytics
- Preserving historically meaningful institutional records

Each purpose has separate access, integrity, retention, and deletion requirements.

### Event Log and Domain State

Most LearningOS domains may use current-state persistence and a transactional outbox. Event sourcing is adopted only when reconstructing state from events provides demonstrated domain value and the team can support versioning, snapshots, privacy, correction, replay, and operational complexity.

### Storage Model

The store should preserve event identity, order within its declared partition, schema version, envelope, payload integrity, ingestion metadata, and archival state. Storage is append-oriented; corrections occur through explicit corrective events or governed administrative procedures rather than invisible mutation.

### Privacy and Retention

Immutability does not override privacy obligations. Event design minimizes personal content, favors references, defines expiration, supports cryptographic or logical erasure where appropriate, and prevents indefinite retention by default.

Deletion workflows must address active streams, archives, projections, backups, analytics, and external consumers according to documented authority and technical constraints.

### Security

Producers, consumers, operators, and replay tools receive separate least-privilege permissions. Events are encrypted in transit and at rest. Sensitive access, export, schema change, replay, and retention override are audited.

### Portability

Canonical event schemas and archival formats remain portable. The platform can export and verify retained history without depending permanently on one broker or cloud service.

---

## 8. Event Replay

Replay reprocesses existing events through one or more consumers to restore, rebuild, migrate, or verify derived state. It is a controlled production change.

### Approved Replay Uses

- Rebuild a corrupted or new projection
- Recover a consumer after an outage
- Apply corrected consumer logic to a bounded history
- Migrate derived state to a new implementation
- Reproduce an incident in an isolated environment
- Verify compatibility before a consumer transition

### Replay Plan

Every material replay defines:

1. Purpose and expected result
2. Source stream, event types, tenants, and time range
3. Consumer and code version
4. Authorization and data classification
5. Idempotency and side-effect suppression
6. Ordering, rate, capacity, and backpressure
7. Dry-run or shadow validation
8. Reconciliation and success criteria
9. Pause, rollback, repair, and abort conditions
10. Owner, approval, schedule, communication, and audit record

### Replay Isolation

Replay traffic is distinguishable from live traffic and cannot accidentally send notifications, charge payments, publish portfolios, issue duplicate credentials, call external systems, or repeat other irreversible effects.

Consumers explicitly declare whether they are replay-safe. Side-effecting consumers require a replay mode, deduplication ledger, compensating controls, or exclusion.

### Schema Evolution

Historical events may be transformed through reviewed upcasters or consumed by version-aware handlers. Original stored meaning remains traceable. Destructive rewriting of history is exceptional and requires formal governance.

### Reconciliation

Completion is proven by expected counts, checksums, invariant checks, sampled domain review, error reconciliation, and comparison with authoritative state. A drained queue alone does not prove a correct replay.

---

## 9. Reliability Principles

Event-driven reliability is achieved through end-to-end outcomes, not broker availability alone.

### Atomic Publication Intent

Domain state and publication intent are committed together through a transactional outbox or equivalent mechanism. Publishers may retry without repeating the domain transition.

### At-Least-Once Delivery

LearningOS assumes at-least-once delivery. Consumers use event identity and business invariants to make processing idempotent.

### Ordering

Ordering is guaranteed only within a documented partition, commonly an aggregate or subject. Consumers must not assume global order and must define behavior for late events.

### Retry Discipline

Transient failures receive bounded exponential backoff with jitter. Retry budgets prevent storms. Permanent failures move to quarantine or a dead-letter process with ownership, alerts, inspection, and controlled redrive.

### Backpressure

Consumers expose lag and capacity. The platform throttles producers or noncritical consumers, scales processing where justified, and protects critical event families during saturation.

### Poison Events

Invalid or repeatedly failing events are isolated without blocking unrelated partitions. Repair preserves original identity, evidence, and audit history.

### Graceful Degradation

Optional reactions may be delayed while authoritative actions remain available. Products disclose stale projections or pending outcomes when the delay matters to learners.

### Disaster Recovery

Event infrastructure has recovery objectives aligned with domain state. Restoration preserves offsets, identifiers, schemas, access controls, and publication continuity. Recovery exercises include broker loss, outbox backlog, duplicate delivery, corrupted projections, and controlled replay.

### No Mythical Exactly Once

Infrastructure features may reduce duplication, but end-to-end exactly-once business outcomes require domain idempotency and reconciliation across every side effect. LearningOS does not use an exactly-once label to avoid this responsibility.

> "Architecture becomes resilient when communication becomes decoupled."

---

## 10. Product & Engineering Implications

Event-driven architecture changes how experiences, services, teams, and operations handle time and partial progress.

### Product Implications

Product teams must:

- Identify which outcome is immediate and which reactions are asynchronous
- Design clear pending, delayed, stale, failed, recovered, and completed states
- Preserve learner actions safely across retries and refreshes
- Avoid promising instant propagation when the contract is eventual
- Make repeated submissions safe and understandable
- Prioritize critical reactions over optional celebration or analytics
- Provide support with correlation identifiers and workflow visibility
- Treat notifications and public achievements as consent-aware side effects
- Measure end-to-end learner outcomes rather than event counts alone

### Engineering Architecture

Engineering must provide:

- A canonical, provider-neutral event envelope
- Transactional publication from authoritative domains
- A schema registry and compatibility checks
- Governed topic, partition, retention, and consumer-group conventions
- Idempotency stores or domain-level deduplication where needed
- Process managers for explicit long-running workflows
- Replay tooling with dry-run, filters, rate controls, and audit
- Dead-letter inspection, repair, and redrive workflows
- Local development and deterministic test harnesses
- Data lineage from producer through projections and external delivery

### Observability

Event observability follows a fact from domain commit to every required reaction. It includes:

- Outbox age and publication failure
- Publish rate, size, and schema rejection
- Broker availability, partitions, quotas, and retention
- Consumer lag, throughput, retry, and dead-letter volume
- Processing latency and business outcome latency
- Duplicate and out-of-order handling
- Process age, timeout, compensation, and completion
- Replay scope, progress, errors, and reconciliation
- Trace correlation across synchronous and asynchronous boundaries

Alerts connect to learner impact, service objectives, owners, and runbooks. High volume is not automatically high importance.

### Testing

Verification covers producer contracts, schema compatibility, consumer idempotency, duplicate and reordered delivery, missing dependencies, retries, poison events, backpressure, process timeouts, replay isolation, authorization, tenant separation, privacy deletion, and disaster recovery.

Contract tests prove published language. End-to-end tests prove critical collaboration. Fault injection proves behavior under partial failure.

### Governance

Every public event has an owner, category, purpose, schema, consumers, data classification, retention, reliability expectation, and retirement plan. New events are reviewed for domain meaning and necessity; they are not created merely to expose internal state changes.

Consumers register their purpose and operational owner. Unknown consumers cannot become permanent invisible dependencies.

### Relationship to Other Canonical Blueprints

Domain-Driven Architecture defines who owns each fact. API & Integration Architecture governs approved external delivery and webhooks. Security, Privacy & Trust Architecture constrains event data and access. Platform Operations governs service objectives and recovery. Analytics and AI consume only authorized event categories for declared purposes.

---

## Canonical Declaration

The Event-Driven Architecture is Canonical Blueprint 032 and the authoritative Project Genesis reference for LearningOS event categories, event bus, metadata, storage, replay, reliable delivery, and event observability.

LearningOS will publish meaningful facts with clear ownership, allow independent systems to collaborate through stable language, and preserve resilience through explicit asynchronous design.

