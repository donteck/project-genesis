# Canonical Blueprint 035

## The Backend & Service Architecture

## Purpose

Define the backend layers, domain services, use cases, repository model, integration adapters, modular-monolith strategy, service boundaries, commands, queries, transactions, asynchronous workflows, error handling, security, observability, and testing architecture for LearningOS.

---

## 1. Why Backend Architecture Matters

The backend protects the meaning of LearningOS.

It ensures that learner progress, project submission, assessment, certification, portfolio evidence, mentoring, billing, notifications, and AI-assisted workflows behave consistently regardless of whether they are triggered by the web application, a mobile client, an administrator, an AI agent, a webhook, or a background process.

The backend should express business purpose—not merely move data between screens and tables.

> **Business rules belong to the domain, not the interface.**

---

## 2. The Backend Architecture

```text
User Interface
      ↓
Application Interface
      ↓
Use Cases
      ↓
Domain Services
      ↓
Repositories and Integrations
      ↓
Database, Events, AI and External Systems
```

Each layer has one clear responsibility. Higher layers coordinate intent. Lower layers provide controlled access to persistence, infrastructure, and external systems.

---

## 3. Application Interface

The application interface is where requests enter the backend.

Examples include:

- Server Actions
- Route Handlers
- REST or GraphQL endpoints
- Webhooks
- Background jobs
- Scheduled tasks
- AI tool calls
- Administrative commands

Its responsibilities are to:

- Authenticate the caller
- Authorize the requested action
- Validate and normalize input
- Identify the correct use case
- Attach trace and correlation context
- Return a stable, safe response

Complex business logic must not live in controllers, route handlers, or UI actions.

---

## 4. Use Cases

Use cases represent meaningful actions performed by the platform.

Examples:

- Register a learner
- Begin a learning journey
- Complete a lesson
- Submit a project
- Review an assessment
- Issue a certificate
- Publish a portfolio
- Assign a mentor
- Invite a learner to an organization
- Generate an AI-supported next-step recommendation

A use case coordinates domain rules, repositories, integrations, transactions, and events required to complete one outcome.

Use cases should be explicit, testable, and named in the language of the product.

---

## 5. Domain Services

Domain services contain LearningOS business rules that do not naturally belong to a single entity.

Examples:

- Determine whether prerequisites are complete
- Calculate journey progress
- Validate certification eligibility
- Evaluate mentor permissions
- Select a learner's next milestone
- Decide whether portfolio evidence is sufficient
- Apply organization-specific learning policy
- Determine whether an assessment attempt may begin

Domain logic must not be duplicated across pages, APIs, database triggers, AI prompts, or background jobs.

---

## 6. Repositories

Repositories provide controlled access to persisted domain information.

Examples:

- Learner repository
- Journey repository
- Learning repository
- Project repository
- Assessment repository
- Portfolio repository
- Community repository
- Knowledge repository
- Organization repository

The domain layer should request meaningful information without depending directly on database tables, SQL syntax, ORM details, or a specific storage vendor.

Repositories should expose domain-oriented operations rather than generic database access.

---

## 7. Integration Adapters

Adapters connect LearningOS to external systems while protecting internal domain logic from vendor-specific details.

Examples:

- Supabase
- GitHub
- Vercel
- Stripe
- Email and messaging providers
- Search infrastructure
- Analytics platforms
- AI model providers
- Object storage
- Calendar and productivity systems

The application should depend on internal contracts. External providers implement those contracts.

This makes integrations testable, replaceable, and resilient to vendor change.

---

## 8. Service Boundaries

Backend services should align with the bounded contexts established by Canonical Blueprint 031.

```text
Identity Service
Learning Service
Journey Service
Project Service
Assessment Service
Portfolio Service
Community Service
Knowledge Service
AI Service
Analytics Service
Organization Service
Billing Service
Notification Service
Platform Service
```

Each service owns its rules, workflows, contracts, tests, events, documentation, and operational responsibilities.

> **A service should have one clear responsibility and one accountable owner.**

---

## 9. Modular Monolith First

LearningOS should begin as a modular monolith with strong domain boundaries.

This provides:

- Simpler deployment
- Easier local development
- Lower operational cost
- Straightforward transactions
- Faster iteration
- Easier debugging
- Clear future extraction paths

A modular monolith is not an unstructured monolith. Each domain remains isolated through explicit interfaces, ownership rules, tests, and dependency constraints.

> **Start modular. Distribute only when evidence demands it.**

---

## 10. Service Extraction Rule

A domain should become an independently deployed service only when there is demonstrated justification.

Before extraction, confirm:

1. The boundary is stable.
2. Ownership is clear.
3. Independent scaling or availability is required.
4. Deployment independence creates measurable value.
5. Contracts are documented and tested.
6. Monitoring and incident ownership exist.
7. Data ownership and migration are understood.
8. A rollback strategy exists.

Microservices must solve real operational or organizational problems—not serve architectural prestige.

---

## 11. Command and Query Separation

Backend operations fall into two primary categories.

### Commands

Commands change state.

Examples:

- Complete a lesson
- Submit a project
- Issue a certificate
- Update a learner profile
- Assign a mentor
- Change a role

Commands enforce authorization, business rules, validation, consistency, idempotency, and event publication.

### Queries

Queries retrieve information without changing business state.

Examples:

- Get dashboard data
- View journey progress
- Search skills
- Load project history
- Display a portfolio
- Retrieve organization analytics

Separating commands from queries improves clarity, security, performance, and testing.

---

## 12. Transactions and Consistency

Some workflows must succeed atomically.

```text
Assessment Approved
      ↓
Certificate Created
      ↓
Evidence Linked
      ↓
Portfolio Updated
      ↓
Journey Progressed
```

The architecture must explicitly define:

- Which changes require immediate consistency
- Which reactions may happen asynchronously
- Where transaction boundaries begin and end
- How partial failure is prevented or repaired
- How compensating actions work

Critical learner records must never remain in an ambiguous or contradictory state.

---

## 13. Background Work

Long-running or noncritical work should execute asynchronously.

Examples:

- Sending email and push notifications
- Generating portfolio summaries
- Rendering certificates
- AI project analysis
- Search indexing
- Analytics aggregation
- Media processing
- External synchronization
- Scheduled recommendations

Background work should include retry policies, idempotency, observability, dead-letter handling, and user-visible status when appropriate.

The learner should not wait for work that can safely continue in the background.

---

## 14. Error Architecture

Errors should be typed, predictable, safe, observable, and actionable.

```text
Validation Error
Authentication Error
Authorization Error
Business Rule Error
Conflict Error
Not Found Error
Rate Limit Error
Integration Error
Temporary Failure
Unexpected System Error
```

The backend should:

- Preserve useful diagnostic context internally
- Return understandable user-facing messages
- Avoid exposing secrets, tokens, stack traces, provider internals, or private data
- Distinguish retryable from non-retryable failures
- Attach trace identifiers to unexpected failures

---

## 15. Idempotency

Important commands must be safe to retry.

Examples:

- Payment processing
- Certificate issuance
- Webhook handling
- Project submission
- Event consumption
- Notification delivery
- Organization invitations

Repeating the same operation must not create duplicate records, duplicate payments, duplicate credentials, or repeated downstream consequences.

Idempotency keys, uniqueness constraints, event identifiers, and processed-message records should be used where appropriate.

---

## 16. Backend Security

Every service must enforce security independently of the frontend.

Required controls include:

- Authentication
- Authorization
- Input validation
- Data ownership checks
- Tenant isolation
- Least privilege
- Rate limiting where appropriate
- Secret isolation
- Audit logging
- Secure defaults
- Safe error handling

UI visibility is never an authorization boundary.

---

## 17. Observability

Every meaningful operation should be traceable across the complete backend path.

```text
Request
  ↓
Use Case
  ↓
Domain Service
  ↓
Database or Integration
  ↓
Event
  ↓
Background Consumer
```

Observability should include:

- Structured logs
- Metrics
- Distributed traces where justified
- Correlation IDs
- Domain event visibility
- Queue health
- Integration health
- Error-rate and latency monitoring

Logs must never expose passwords, session tokens, private learner data, payment secrets, or protected AI context.

---

## 18. Testing Strategy

The backend should support multiple levels of verification.

- Unit tests for business rules
- Use-case tests for orchestration
- Integration tests for repositories and persistence
- Contract tests for external adapters
- Authorization and tenant-isolation tests
- Event-processing tests
- Idempotency tests
- Failure and retry tests
- End-to-end tests for critical learner workflows

The most important tests protect:

- Identity and access
- Learner progress
- Project ownership
- Assessment integrity
- Certification eligibility
- Portfolio evidence
- Privacy
- Billing
- Organization isolation

---

## 19. Recommended Organization

```text
src/
├── domains/
│   ├── identity/
│   ├── learning/
│   ├── journey/
│   ├── projects/
│   ├── assessment/
│   ├── portfolio/
│   ├── community/
│   ├── knowledge/
│   ├── ai/
│   └── analytics/
├── application/
│   ├── commands/
│   ├── queries/
│   └── workflows/
├── infrastructure/
│   ├── database/
│   ├── events/
│   ├── queues/
│   ├── integrations/
│   └── observability/
└── shared/
    ├── errors/
    ├── security/
    ├── validation/
    └── types/
```

The exact folders may evolve. The separation of responsibilities must remain explicit.

Shared code should be small, stable, and genuinely cross-domain. It must not become a location for unowned business logic.

---

## 20. Product and Engineering Implications

This architecture requires future LearningOS implementation to:

- Organize business logic around domains and use cases
- Keep interfaces thin
- Prevent business-rule duplication
- Begin with a modular monolith
- Use explicit contracts for external providers
- Separate commands from queries
- Define transaction and asynchronous boundaries deliberately
- Make important operations idempotent
- Enforce authorization in backend services
- Build observability into workflows
- Test business meaning, not only code paths

The result should be a backend that remains understandable and adaptable as LearningOS grows from its initial release into a global platform.

---

## Permanent Principles

> **Business rules belong to the domain, not the interface.**

> **Start modular. Distribute only when evidence demands it.**

> **A service should have one clear responsibility and one accountable owner.**

> **Backend architecture protects the meaning of the product.**
