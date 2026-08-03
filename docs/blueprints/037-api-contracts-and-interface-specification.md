# Canonical Blueprint 037

## API Contracts & Interface Specification

## Purpose

Define the complete LearningOS API philosophy, endpoint organization, versioning strategy, authentication model, authorization rules, response standards, error handling, pagination, filtering, rate limiting, webhooks, SDK strategy, observability, lifecycle management, and documentation standards.

---

## 1. Why API Contracts Matter

LearningOS depends on stable communication between web clients, mobile applications, AI systems, backend services, external integrations, and future platform extensions.

An API contract defines what callers may expect and what providers must preserve. Stable contracts reduce accidental coupling, simplify testing, and allow implementations to evolve without breaking consumers.

> **Every API is a promise. Every promise must be stable.**

## 2. API Philosophy

LearningOS APIs should expose business capabilities rather than database structure.

They should be:

- Predictable
- Versioned
- Secure
- Consistent
- Discoverable
- Observable
- Backward compatible where practical
- Documented as part of the product

## 3. API Architecture

```text
Client
  ↓
Gateway
  ↓
Authentication
  ↓
Application Layer
  ↓
Domain Service
  ↓
Repository
  ↓
Database
```

Clients never depend directly on database tables or internal persistence details.

## 4. API Categories

LearningOS supports five API categories:

1. **Public APIs** — published portfolios, catalogs, and public documentation.
2. **Authenticated APIs** — learner dashboards, projects, progress, and AI mentoring.
3. **Organization APIs** — tenant-scoped administration, analytics, and team learning.
4. **Internal APIs** — service-to-service communication unavailable to public clients.
5. **System APIs** — operations, automation, monitoring, and platform administration.

## 5. URL Structure

The recommended external convention is:

```text
/api/v1/auth/
/api/v1/users/
/api/v1/learning/
/api/v1/journeys/
/api/v1/projects/
/api/v1/assessments/
/api/v1/certificates/
/api/v1/portfolios/
/api/v1/ai/
/api/v1/organizations/
/api/v1/analytics/
/api/v1/notifications/
```

URLs should be stable, resource-oriented, and free from implementation-specific naming.

## 6. Resource Naming

Prefer nouns and standard HTTP semantics.

```text
GET    /projects
POST   /projects
GET    /projects/{id}
PATCH  /projects/{id}
DELETE /projects/{id}
```

Avoid action-style paths such as `/createProject` or `/getProjects` unless modeling a true domain command that cannot be represented clearly as a resource transition.

## 7. HTTP Methods

- `GET` retrieves data without changing state.
- `POST` creates a resource or begins a domain command.
- `PUT` replaces a complete resource representation.
- `PATCH` applies a partial update.
- `DELETE` removes or archives according to domain policy.

Method behavior must remain consistent across domains.

## 8. Response Standards

Successful responses use a predictable envelope:

```json
{
  "success": true,
  "data": {},
  "meta": {},
  "links": {}
}
```

Collection responses include explicit pagination metadata.

## 9. Error Standards

Errors use a stable structure:

```json
{
  "success": false,
  "error": {
    "code": "PROJECT_NOT_FOUND",
    "message": "Project not found.",
    "details": []
  },
  "traceId": "..."
}
```

Error categories include validation, authentication, authorization, business rule, conflict, rate limit, not found, dependency failure, and unexpected system error.

Internal implementation details, credentials, stack traces, and private learner data must never be exposed.

## 10. Versioning

Breaking changes require a new version, such as `/api/v2/`.

Backward-compatible additions may remain within the current version. Every version should have a documented support period, deprecation policy, and migration path.

## 11. Pagination

Collection endpoints should support bounded retrieval through page-based or cursor-based pagination.

A page-based response may include:

```json
{
  "items": [],
  "page": 1,
  "pageSize": 25,
  "totalItems": 325,
  "totalPages": 13
}
```

Cursor-based pagination is preferred for large, frequently changing datasets.

## 12. Filtering

Filtering should be explicit, composable, validated, and documented.

```text
GET /projects?status=approved&skill=react&mentor=true
```

Filters must respect authorization and tenant boundaries.

## 13. Sorting

Sorting should use documented fields and directions:

```text
sort=createdAt&order=desc
```

Unsupported fields should produce a validation error rather than silently changing behavior.

## 14. Authentication

Supported authentication modes may include:

- Session or JWT authentication
- OAuth and OpenID Connect
- Passkeys
- API keys for approved server integrations
- Organization-scoped credentials
- Service credentials for trusted internal workloads

Each credential type must have explicit scope, expiration, revocation, and storage requirements.

## 15. Authorization

Authentication answers who the caller is. Authorization determines what the caller may do.

Every endpoint must document:

- Required role or permission
- Ownership requirements
- Organization scope
- Data visibility rules
- Elevated privilege requirements

Authorization must be enforced server-side and, where applicable, by database row-level security.

## 16. Idempotency

Critical operations should accept idempotency keys so retries cannot create duplicate effects.

Examples include:

- Payments
- Certificate issuance
- Project submission
- Webhook processing
- External synchronization

## 17. Rate Limiting

Limits should vary by API category, identity, organization, risk, and cost.

AI, authentication, public, webhook, and administrative endpoints may require distinct limits. Rate-limit responses should communicate retry guidance without revealing security-sensitive thresholds.

## 18. Webhooks

Outbound webhooks should include:

- Event identifier
- Event type and version
- Timestamp
- Signed payload
- Delivery identifier
- Retry policy
- Idempotency support

```text
Project Published
  ↓
Webhook Event
  ↓
Signed Delivery
  ↓
External Consumer
```

Webhook consumers must verify signatures and tolerate duplicate delivery.

## 19. Documentation

Every endpoint should document:

- Purpose
- Request parameters and body
- Response structure
- Authentication and permissions
- Errors
- Rate limits
- Examples
- Version and deprecation status

Documentation is part of the API contract.

## 20. OpenAPI

Public and partner-facing APIs should produce an OpenAPI specification synchronized with implementation.

OpenAPI should support documentation generation, validation, contract testing, SDK generation, and compatibility review.

## 21. SDK Strategy

Official SDKs may be provided for TypeScript, Python, Swift, Kotlin, and other languages as adoption requires.

SDKs simplify authentication, pagination, retries, error handling, and version migration but must never hide important security or domain rules.

## 22. API Lifecycle

```text
Draft
  ↓
Review
  ↓
Approved
  ↓
Implemented
  ↓
Published
  ↓
Deprecated
  ↓
Retired
```

No public endpoint should be retired without notice, migration guidance, and impact assessment.

## 23. Observability

Every request should be traceable through correlation identifiers, version, latency, caller identity when appropriate, domain operation, dependency calls, and outcome.

Logs and traces must exclude secrets and sensitive content.

## 24. Product and Engineering Implications

- Frontend and mobile teams can build against predictable contracts.
- Domain services remain independent from transport details.
- AI tools interact through explicit, permission-aware interfaces.
- External partners receive stable integration boundaries.
- Contract tests become a release requirement.
- Breaking changes are governed rather than improvised.

---

## Permanent Principles

> **Every API is a promise.**

> **Stable contracts create stable platforms.**

> **Expose business capabilities, not database tables.**

> **Consistency reduces cognitive load.**
