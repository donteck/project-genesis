# Canonical Blueprint 039

## The Workflow & Automation Engine

## Purpose

Define the complete LearningOS workflow orchestration, event-driven automation, scheduled jobs, AI-coordinated processes, human approval gates, workflow state management, retries, idempotency, compensation, timeouts, ownership, security, observability, metrics, templates, and testing architecture.

---

## 1. Why Workflow Architecture Matters

LearningOS coordinates long-running processes across learners, mentors, instructors, AI agents, services, events, integrations, and administrators. Without a formal workflow architecture, important processes become hidden inside route handlers, background jobs, database triggers, and vendor-specific automation.

A workflow must make progress, ownership, failure, approval, and recovery visible.

> **Automation should remove friction without removing accountability.**

---

## 2. The Automation Philosophy

Automation exists to reduce repetitive effort, improve consistency, and help people focus on higher-value judgment. It must not silently replace human accountability in decisions that affect credentials, learner outcomes, access, finances, privacy, or safety.

Every workflow must define:

- A trigger
- Inputs and validation
- Explicit ownership
- Visible state
- Authorized actions
- Approval requirements
- Error and retry behavior
- Recovery or compensation
- Completion criteria
- Events and audit history

---

## 3. The Workflow Model

```text
Trigger
  ↓
Validation
  ↓
Context Loading
  ↓
Decision
  ↓
Action
  ↓
Approval when required
  ↓
External Integration
  ↓
Verification
  ↓
Completion
  ↓
Event Publication
```

No important process should be invisible or depend on undocumented side effects.

---

## 4. Workflow Categories

### User-Initiated Workflows

Triggered by a learner, mentor, instructor, administrator, or organization member. Examples include submitting a project, requesting mentorship, publishing a portfolio, starting an assessment, or updating a profile.

### Event-Driven Workflows

Triggered when a domain event occurs.

```text
Lesson Completed
  ↓
Progress Updated
  ↓
Journey Recalculated
  ↓
AI Recommendation Generated
  ↓
Notification Sent
```

### Scheduled Workflows

Triggered by time, such as weekly learning summaries, monthly organization reports, credential-expiration reminders, nightly synchronization, and stale-request review.

### AI-Orchestrated Workflows

Coordinated by the AI orchestration layer for tasks such as context retrieval, project analysis, feedback drafting, recommendation generation, and escalation for human review.

### Administrative Workflows

Used for content approval, user moderation, security review, organization provisioning, billing reconciliation, incident escalation, and governance.

---

## 5. Workflow State Machine

Long-running workflows must expose explicit states.

```text
pending
  ↓
running
  ↓
waiting_for_input
  ↓
waiting_for_approval
  ↓
completed
```

Alternative states include:

```text
failed
cancelled
expired
compensating
```

State must be represented directly, not inferred from unrelated records.

---

## 6. Human Approval Gates

High-impact operations require human review. Examples include issuing or revoking credentials, publishing official content, changing learner outcomes, accepting AI-generated assessment decisions, executing financial actions, deleting accounts, and changing organizational access.

Approval records must preserve:

- Approver identity
- Authority used
- Item and version reviewed
- Evidence considered
- Decision
- Timestamp
- Comments or conditions

---

## 7. Human-in-the-Loop Rule

> **The greater the consequence, the stronger the approval requirement.**

Low-risk repetitive work may complete automatically. High-impact decisions require explicit oversight, reviewable evidence, and a durable audit trail.

---

## 8. Workflow Definitions

Every versioned workflow definition should include:

```text
workflow_id
name
version
owner
trigger
inputs
steps
conditions
timeouts
retry_policy
approval_policy
compensation_strategy
outputs
status
```

Historical executions must remain linked to the exact workflow version that ran.

---

## 9. Workflow Execution Records

Every execution should preserve:

```text
execution_id
workflow_id
workflow_version
trigger_source
actor_id
organization_id
current_state
started_at
completed_at
step_history
errors
approvals
correlation_id
```

Execution records make workflows observable, support incident analysis, and preserve accountability.

---

## 10. Step Types

Supported step types may include:

- Validation
- Domain command
- Database operation
- API call
- AI agent call
- Event publication
- Notification
- Delay
- Approval
- Conditional branch
- Loop
- Parallel execution
- Human task
- Compensation action

Each step should have one clear responsibility and a typed result.

---

## 11. Branching

Conditional paths must be explicit and testable.

```text
Assessment Submitted
  ↓
Automated Validation
  ↓
Score Above Threshold?
  ├── Yes → Human Spot Check
  └── No  → Revision Requested
```

Branch conditions belong to documented policy or domain rules rather than hidden prompt logic.

---

## 12. Parallel Execution

Independent actions may execute concurrently.

```text
Project Approved
  ├── Update Portfolio
  ├── Update Journey
  ├── Recalculate Skills
  ├── Generate Achievement
  └── Send Notification
```

Parallel execution must preserve idempotency, observability, tenant isolation, and clear completion semantics.

---

## 13. Retries

Transient failures may retry automatically. Retry policies must define:

- Retryable errors
- Non-retryable errors
- Maximum attempts
- Delay and backoff
- Jitter where appropriate
- Escalation behavior
- Dead-letter handling

Examples include provider timeouts, temporary network failures, webhook delivery failures, search indexing failures, and unavailable email services.

---

## 14. Idempotency

Every retryable command or step must be safe to repeat.

The platform must not:

- Issue a credential twice
- Charge a payment twice
- Publish duplicate domain events
- Create duplicate portfolio evidence
- Assign the same mentor twice

Idempotency keys should represent the business operation, not merely one HTTP request.

---

## 15. Compensation

Cross-system workflows cannot always rely on one database transaction. When later steps fail, the workflow may execute compensating actions to restore business consistency.

Compensation should be designed for the meaning of the workflow. It should not blindly reverse every completed action.

```text
Organization Created
  ↓
Billing Subscription Created
  ↓
Welcome Package Failed
  ↓
Retry, mark provisioning incomplete, or escalate
```

---

## 16. Timeouts and Expiration

Waiting states must not remain open forever. Invitations, approval requests, payment sessions, mentor requests, and unfinished onboarding should define expiration and escalation policies.

Every timeout should specify what happens next: fail, cancel, retry, reassign, archive, or request human intervention.

---

## 17. Workflow Ownership

Every workflow has one accountable owner, such as the Identity, Learning, Assessment, AI, Billing, Notification, or Platform domain.

Cross-domain orchestration does not remove ownership. The orchestrator coordinates; domains remain authoritative for their own business rules.

---

## 18. Orchestration vs Choreography

### Orchestration

A central coordinator directs a process. Use it for complex, long-running, approval-based, or highly observable workflows.

### Choreography

Domains independently react to published events. Use it for loosely coupled, optional, and naturally independent reactions.

> Use orchestration when the process itself has a meaningful lifecycle. Use choreography when independent domains merely react to an event.

---

## 19. AI Workflow Safety

AI-driven steps must define:

- Allowed tools and actions
- Authorized data scopes
- Maximum autonomy
- Model and prompt versions
- Output schema validation
- Approval thresholds
- Fallback behavior
- Evidence requirements
- Safety and privacy checks

AI-generated output is untrusted until validated by deterministic rules or authorized human review.

---

## 20. Workflow Builder

A future Workflow Builder may allow authorized administrators, instructors, content teams, and operations teams to configure approved workflows visually.

The builder should expose governed components rather than arbitrary code execution. Every published workflow must pass validation, permissions review, versioning, and testing requirements.

---

## 21. Automation Templates

Reusable templates may include:

- Learner onboarding
- Course launch
- Cohort enrollment
- Mentor matching
- Project review
- Certification issuance
- Portfolio publication
- Organization provisioning
- Billing recovery
- Incident escalation

Templates reduce duplicated engineering effort while preserving governed behavior.

---

## 22. Notifications

Notifications are workflow outputs, not the business workflow itself. A delayed email should not automatically invalidate a successfully issued certificate.

Business completion and communication delivery must be modeled separately.

---

## 23. Observability

Every workflow should expose:

- Current state
- Current and failed step
- Step duration
- Retry count
- Approval status
- Trigger source
- Correlation ID
- Related entities
- Final outcome

Operators should be able to diagnose workflows without reconstructing them manually from unrelated logs.

---

## 24. Metrics

Useful metrics include:

- Completion and failure rates
- Average and percentile duration
- Approval wait time
- Retry rate
- Manual-intervention rate
- Compensation rate
- Cost per execution
- AI usage and latency
- Workflow abandonment

Metrics should improve reliability, cost control, and user experience.

---

## 25. Security

Workflow execution must enforce authentication, authorization, tenant boundaries, approval authority, data minimization, secret isolation, safe tool access, rate limits, and audit history.

A workflow must never gain more authority than the initiating actor or an explicitly authorized service identity.

---

## 26. Testing

Workflow tests should cover:

- Successful execution
- Validation and authorization failure
- Step timeout
- Retry success and exhaustion
- Approval, rejection, and expiration
- Cancellation
- Compensation
- Duplicate trigger
- Out-of-order event
- External-provider failure
- Tenant-boundary enforcement
- AI-output validation failure

Long-running workflows should be deterministic under test through controlled time, events, queues, and provider adapters.

---

## 27. Recommended Architecture

```text
src/
├── workflows/
│   ├── definitions/
│   ├── orchestrators/
│   ├── steps/
│   ├── policies/
│   ├── approvals/
│   ├── compensation/
│   └── tests/
├── infrastructure/
│   ├── queues/
│   ├── scheduler/
│   ├── events/
│   ├── workers/
│   └── observability/
└── domains/
    └── ...
```

The workflow engine coordinates domains without absorbing their business logic.

---

## 28. Product and Engineering Implications

LearningOS should treat workflows as versioned product capabilities rather than scattered automation scripts. Product teams must define user-visible state, approvals, cancellation, and recovery. Engineers must protect idempotency, domain authority, event traceability, and tenant isolation.

The architecture should begin with a small governed workflow layer and evolve toward durable orchestration infrastructure only as operational evidence requires it.

---

## Permanent Principles

> **Automation should remove friction without removing accountability.**

> **Every workflow must have a visible state, an owner, and a recovery path.**

> **The greater the consequence, the stronger the approval requirement.**

> **Retries must be safe. Failures must be observable. Decisions must be auditable.**

> **AI may coordinate work, but validated business rules remain authoritative.**
