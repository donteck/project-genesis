# Canonical Blueprint 036

## The Database Schema Architecture

## Purpose

Define the complete LearningOS relational schema philosophy, domain ownership, entity relationships, constraints, row-level security, multi-tenancy, versioning, auditability, migration strategy, retention, indexing, search boundaries, backup, and recovery architecture.

---

## 1. Why Database Schema Architecture Matters

The database protects the durable truth of LearningOS. Interfaces, frameworks, and services may change, but learner identity, progress, projects, evidence, credentials, permissions, and historical records must remain trustworthy.

A strong schema protects integrity through explicit ownership, relationships, constraints, security policies, transactions, migrations, and recoverable history.

> **The database should protect the truth of the product.**

---

## 2. The Schema Philosophy

LearningOS data must be:

- Clearly owned
- Strongly related
- Secure by default
- Historically traceable
- Versionable where necessary
- Designed for change
- Understandable to future builders

Every table must have a defined purpose. Every relationship must express business meaning. Every important rule should be enforced as close to the data as practical.

---

## 3. Core Schema Domains

```text
LearningOS Database
├── Identity
├── Organizations
├── Learning Content
├── Learner Journeys
├── Progress
├── Skills & Competencies
├── Projects
├── Assessments
├── Certifications
├── Portfolio & Evidence
├── Community & Mentorship
├── AI Memory
├── Notifications
├── Billing
├── Analytics
├── Events
└── Platform Governance
```

These domains correspond to the bounded contexts established in Canonical Blueprint 031.

---

## 4. Identity Schema

Primary records:

```text
auth.users
profiles
user_preferences
user_roles
role_assignments
user_consents
user_devices
security_events
```

### Profiles

The `profiles` table stores application-specific identity, not authentication credentials.

Recommended fields:

```text
id
user_id
full_name
display_name
headline
bio
avatar_url
timezone
locale
country_code
experience_level
career_goal
onboarding_status
created_at
updated_at
```

`user_id` references the authentication provider's user record.

---

## 5. Organization and Tenancy Schema

Primary records:

```text
organizations
organization_members
organization_roles
teams
team_members
organization_settings
organization_invitations
```

LearningOS should support individuals, schools, universities, companies, training organizations, departments, and cohorts.

> **Tenant ownership must be explicit, never inferred.**

Organization-owned records generally include `organization_id`. Learner-owned records generally include `user_id`. Some records may include both.

---

## 6. Learning Content Schema

Primary records:

```text
domains
learning_paths
courses
course_modules
lessons
lesson_resources
exercises
content_versions
content_dependencies
content_tags
```

Recommended hierarchy:

```text
Domain
  ↓
Learning Path
  ↓
Course
  ↓
Module
  ↓
Lesson
  ↓
Exercise
```

Ordering should be represented with explicit fields such as `position`, `sort_order`, or `sequence_number` rather than encoded into identifiers.

---

## 7. Learner Journey Schema

Primary records:

```text
learner_goals
learner_journeys
journey_milestones
journey_steps
journey_recommendations
journey_reflections
```

A journey should preserve destination, current state, milestones, recommendations, historical changes, and completion status.

A learner may retain multiple historical journeys while having only one designated primary active journey. This should be protected through a partial unique constraint or equivalent database policy.

---

## 8. Progress Schema

Primary records:

```text
course_enrollments
lesson_progress
module_progress
course_progress
learning_activity
study_sessions
learning_streaks
```

Recommended states:

```text
not_started
in_progress
completed
review_required
mastered
```

Completion and mastery must remain distinct.

---

## 9. Skills and Competency Schema

Primary records:

```text
skills
skill_relationships
skill_prerequisites
competency_levels
learner_skills
skill_evidence
career_roles
career_role_skills
```

Supported relationships may include:

```text
requires
supports
related_to
specializes
supersedes
demonstrated_by
```

Relationships that influence recommendations, progression, or certification must remain queryable and constrained rather than existing only as unstructured JSON.

---

## 10. Project Schema

Primary records:

```text
projects
project_members
project_milestones
project_artifacts
project_versions
project_repositories
project_deployments
project_reflections
project_reviews
```

Recommended statuses:

```text
draft
planned
active
submitted
under_review
revision_requested
approved
published
archived
```

Each project preserves purpose, requirements, ownership, contributors, versions, evidence, reviews, deployment references, and reflection.

---

## 11. Assessment Schema

Primary records:

```text
assessments
assessment_versions
assessment_attempts
assessment_responses
assessment_rubrics
rubric_criteria
assessment_reviews
assessment_results
```

Assessment definitions must be versioned. Every attempt remains linked to the exact assessment version and rubric used when it was submitted.

Historical outcomes must never be silently changed by later edits.

---

## 12. Certification Schema

Primary records:

```text
certifications
certification_requirements
issued_credentials
credential_evidence
credential_verifications
credential_revocations
```

Issued credentials should preserve:

```text
credential_id
recipient_user_id
certification_id
certification_version
issued_at
expires_at
verification_code
status
evidence_snapshot
```

Credentials should link to evidence while preserving immutable historical snapshots where necessary.

---

## 13. Portfolio and Evidence Schema

Primary records:

```text
portfolios
portfolio_sections
portfolio_items
evidence_records
evidence_links
portfolio_visibility
portfolio_publications
resume_versions
```

Evidence may originate from projects, assessments, certifications, mentoring, community contributions, external systems, and uploaded artifacts.

The schema must distinguish among:

```text
source record
evidence snapshot
public presentation
```

---

## 14. Community and Mentorship Schema

Primary records:

```text
communities
community_members
discussions
discussion_replies
study_groups
study_group_members
mentorship_requests
mentorship_relationships
mentor_sessions
peer_reviews
reputation_events
```

Reputation must remain event-based and auditable. A mutable score without preserved reasons is insufficient.

---

## 15. AI Memory Schema

Primary records:

```text
ai_conversations
ai_messages
ai_memory_items
ai_memory_scopes
ai_recommendations
ai_feedback
ai_tool_executions
ai_safety_events
```

Memory scopes:

```text
session
journey
project
skill
portfolio
community
lifelong
```

Sensitive memory must include owner, purpose, consent basis, retention policy, visibility, and deletion state. Conversation history must not become permanent memory by default.

---

## 16. Events and Audit History

Primary records:

```text
domain_events
event_consumers
event_failures
audit_logs
change_history
```

A meaningful event should include:

```text
id
event_type
event_version
aggregate_type
aggregate_id
actor_id
organization_id
correlation_id
causation_id
payload
occurred_at
published_at
```

Business events describe what happened in the product. Audit logs describe access to or changes in protected resources.

---

## 17. Primary Key Strategy

UUID-based identifiers are the recommended default because they support distributed creation, stable public references, and reduced enumeration risk.

Human-readable identifiers remain separate:

```text
id: UUID
slug: full-stack-engineering
public_code: CERT-2026-8F4K2
```

Email addresses and mutable usernames must never serve as primary keys.

---

## 18. Foreign Keys

Foreign keys protect meaningful relational integrity.

Examples:

```text
profiles.user_id → auth.users.id
course_modules.course_id → courses.id
lessons.module_id → course_modules.id
project_reviews.project_id → projects.id
issued_credentials.user_id → auth.users.id
```

Deletion behavior must be intentional: `RESTRICT`, `CASCADE`, `SET NULL`, or governed soft deletion.

> **Deletion behavior must reflect business meaning.**

---

## 19. Constraints

Database constraints protect essential truths, including:

- Unique public slugs
- Positive ordering values
- Valid status values
- One primary active journey per learner
- One membership per user per organization
- No duplicate credential issuance for the same requirement
- Progress values between 0 and 100
- End dates not preceding start dates

Application validation improves usability. Database constraints preserve integrity. Both are required.

---

## 20. Status Models

Avoid inconsistent free-form status strings.

Use database enums for stable values, lookup tables when metadata or administration is needed, and check constraints for simple bounded states.

Every lifecycle should document valid transitions.

```text
draft
  ↓
submitted
  ↓
under_review
  ↓
approved
```

---

## 21. Timestamps

Important tables generally include:

```text
created_at
updated_at
```

Lifecycle-specific timestamps may include:

```text
published_at
completed_at
archived_at
deleted_at
verified_at
revoked_at
```

Timestamp meaning must always be explicit.

---

## 22. Soft Deletion

Soft deletion is appropriate where recovery, auditability, and historical relationships matter.

Typical field:

```text
deleted_at
```

Soft deletion does not replace legal deletion, anonymization, or privacy obligations.

---

## 23. Immutable Records

Some finalized records should become immutable, including:

- Issued credentials
- Completed assessment snapshots
- Financial transactions
- Security audit records
- Published domain events
- Consent records
- Historical evidence snapshots

Corrections should create amendments or replacement versions rather than silent mutation.

---

## 24. Row-Level Security

Supabase Row-Level Security must protect every exposed application table.

Example policies:

```text
Users may read and update their own private profile.
Organization administrators may manage records inside their organization.
Mentors may view only assigned learners.
Public visitors may read only explicitly published portfolios.
Learners may never modify issued credentials directly.
```

RLS is a database security boundary, not a UI convenience.

---

## 25. Service-Role Isolation

Privileged credentials must never enter browser code or public environment variables. They should be restricted to trusted server processes and explicit privileged operations.

Normal user requests should rely on the authenticated public client plus enforced authorization and RLS.

---

## 26. Multi-Tenant Isolation

Tenant-aware records require tenant identifiers, RLS, authorization checks, foreign-key consistency, and dedicated tests.

Recommended composite uniqueness patterns:

```text
UNIQUE (organization_id, slug)
UNIQUE (organization_id, external_id)
UNIQUE (organization_id, user_id)
```

These patterns prevent collisions and leakage across organizations.

---

## 27. JSON Usage

JSON and JSONB are appropriate for provider payloads, event payloads, experimental metadata, and versioned snapshots.

They must not replace relational modeling for data that must be joined, constrained, secured independently, indexed predictably, or reported consistently.

> **Use relational columns for business truth and JSON for controlled flexibility.**

---

## 28. Indexing Strategy

Indexes should support measured access patterns.

Common candidates include:

```text
user_id
organization_id
status
created_at
updated_at
slug
normalized email
foreign keys
event_type
correlation_id
published_at
```

Too few indexes create latency. Too many increase write and maintenance cost.

---

## 29. Search Architecture

Transactional tables remain optimized for business operations. Search may use PostgreSQL full-text search, vector search, dedicated search infrastructure, or materialized search documents.

Search indexes are derived representations and must not become the only source of truth.

---

## 30. Migration Architecture

Every schema change must be represented through version-controlled migrations containing:

- Purpose
- Forward operation
- Data transformation
- Compatibility considerations
- Validation
- Recovery or rollback strategy
- Expected risk

Production changes must never exist only as manual database operations.

---

## 31. Expand-and-Contract Migrations

For high-risk changes:

```text
1. Add the new structure.
2. Support old and new structures temporarily.
3. Backfill data.
4. Validate consistency.
5. Switch application reads and writes.
6. Remove the old structure later.
```

This pattern reduces downtime and rollback risk.

---

## 32. Seed Data

Seed data categories:

### Required system data

- Roles
- Permission definitions
- Competency levels
- Platform configuration

### Development data

- Test learners
- Example courses
- Sample projects

### Demonstration data

- Showcase portfolios
- Guided onboarding examples

Development and demonstration records must never be confused with production data.

---

## 33. Database Functions and Triggers

Functions and triggers may enforce updated timestamps, immutable audit events, derived counters, integrity guarantees, and security-sensitive rules.

Complex product workflows should generally remain visible in domain or application services unless atomic database enforcement is necessary.

Hidden trigger behavior must be documented.

---

## 34. Data Retention

Every sensitive data category must define why it is stored, retention duration, access rights, export rights, deletion rights, anonymization possibilities, and regulatory obligations.

Retention is architecture, not an afterthought.

---

## 35. Backup and Recovery

The schema strategy must support:

- Automated backups
- Point-in-time recovery
- Restoration testing
- Migration recovery
- Corruption detection
- Regional resilience
- Credential and evidence preservation

> **A backup is not trusted until restoration has been tested.**

---

## 36. Recommended Supabase Organization

```text
supabase/
├── migrations/
├── seed.sql
├── functions/
├── policies/
├── tests/
└── README.md

src/
├── domains/
│   ├── identity/
│   ├── learning/
│   ├── journeys/
│   ├── projects/
│   ├── assessments/
│   └── portfolios/
├── infrastructure/
│   └── database/
│       ├── queries/
│       ├── repositories/
│       ├── mappers/
│       └── types/
└── lib/
    └── supabase/
```

Generated database types are infrastructure contracts, not the complete domain model.

---

## 37. Database Review Checklist

Before approving a new table, ask:

1. Which domain owns it?
2. What business truth does it represent?
3. Who may read it?
4. Who may modify it?
5. Does it require history?
6. Does it require versioning?
7. Does it require soft deletion?
8. What happens when a related record is removed?
9. Which constraints protect it?
10. Which indexes support its queries?
11. Which RLS policies protect it?
12. How will it migrate safely?

---

## 38. Product and Engineering Implications

Blueprint 036 requires every LearningOS implementation to:

- Align schema ownership with domain boundaries
- Protect learner and tenant data through RLS and authorization
- Version assessments, credentials, content, and critical evidence
- Preserve historical meaning rather than rewriting finalized records
- Treat migrations, retention, backup, and recovery as first-class architecture
- Separate transactional truth from search and analytics projections
- Maintain explicit data lifecycle and ownership documentation

---

## Permanent Principles

> **The database protects the truth of the product.**

> **Application validation improves experience. Database constraints preserve integrity.**

> **Every record must have an owner, a purpose, and a lifecycle.**

> **Use relational structure for business truth and flexible data only where flexibility is intentional.**

> **Historical evidence should never be silently rewritten.**
