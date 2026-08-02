# Canonical Blueprint 024

## The AI Orchestration Layer

| Record | Details |
|---|---|
| Blueprint number | 024 |
| Status | Canonical |
| Date established | August 2, 2026 |
| Authority | Project Genesis |
| Steward | Merchay Global Vision |
| Scope | LearningOS AI agents, orchestration, routing, context, memory, tools, models, workflows, governance, evaluation, safety, and human oversight |
| Purpose | Define the multi-agent AI architecture that powers LearningOS through specialized AI mentors coordinated by a central orchestration layer. |

---

## Purpose and Authority

LearningOS requires different forms of intelligence at different moments. Teaching a concept, reviewing code, designing architecture, interpreting assessment evidence, improving a portfolio, researching a source, and supporting reflection are related responsibilities, but they should not be collapsed into one undefined assistant.

The AI Orchestration Layer coordinates specialized agents through a central, governed system. It identifies intent, assembles authorized context, selects expertise, controls tools, evaluates results, synthesizes a coherent response, preserves appropriate memory, and recommends the next meaningful action.

This blueprint defines the AI philosophy, Council, ten agents, Orchestrator, memory, workflow, governance, and product and engineering requirements through which LearningOS provides collaborative intelligence without surrendering human agency or accountability.

> "Intelligence grows through collaboration."

---

## 1. Why AI Orchestration Matters

A single general model can produce fluent responses across many subjects, but fluency does not establish the correct role, context, evidence, tools, policy, or standard of review. Learning support becomes safer and more useful when responsibilities are explicit and coordinated.

AI orchestration matters because it:

- Routes a learner's need to relevant expertise
- Separates responsibilities, tools, and permissions
- Combines perspectives for complex tasks
- Applies consistent identity, privacy, safety, and assessment rules
- Assembles context according to purpose and least privilege
- Selects models and tools according to capability, risk, latency, and cost
- Preserves one coherent learner experience across specialized agents
- Makes reasoning steps, delegation, and sources more observable
- Allows agents to evolve without redesigning the entire product
- Supports evaluation at agent, workflow, and outcome levels

Orchestration should not create unnecessary agent activity. Many questions require one capable agent and a short response. The system should delegate only when specialization, tools, independent review, or parallel perspectives create meaningful value.

The Orchestrator is not an all-powerful model with unrestricted access. It is a policy-controlled coordinator operating within the learner's identity, tenant, workspace, consent, and current task.

---

## 2. The AI Philosophy

The LearningOS multi-agent system is governed by the following principles.

### Human Potential before Automation

AI should strengthen understanding, capability, agency, and contribution. It should not automate away the practice or judgment the learner is meant to develop.

### Specialized Responsibility

Each agent should have a defined purpose, allowed context, tools, output contracts, escalation boundaries, and evaluation criteria.

### One Coherent Experience

Learners should not need to understand internal model routing. The system may reveal which expertise contributed when useful, but responses should remain coordinated and understandable.

### Least-Privilege Intelligence

Agents receive only the context and tools necessary for the assigned task. Delegation must not expand access beyond the learner, organization, or workflow authority.

### Evidence and Provenance

Agents should ground claims in authorized knowledge, learner artifacts, tool results, and sources. Generated synthesis should remain distinguishable from verified fact.

### Collaboration with Restraint

Multiple agents should collaborate when roles are genuinely complementary. The system should avoid theatrical debate, duplicated work, and cost without learner value.

### Memory with Consent and Purpose

Memory exists to preserve useful continuity, not to create an invisible permanent profile. Durable memory should be typed, learner-visible where practical, and correctable.

### Accountable Action

AI may propose or perform authorized low-risk actions. Consequential actions require validation, appropriate confirmation, and human review according to policy.

### Independent Verification

For important outputs, the system should separate generation from verification where doing so materially improves correctness, safety, or integrity.

> "Great AI is orchestrated, not isolated."

---

## 3. The AI Council

The AI Council is the conceptual body of specialized LearningOS agents available to the Orchestrator. It is not an autonomous governing authority and does not vote on a person's future. It is a coordinated set of capabilities called according to task and policy.

The canonical Council is:

```text
Learner
  ↓
AI Orchestrator
  ↓
Learning Coach
Coding Mentor
Architecture Advisor
Career Coach
Portfolio Coach
Assessment Reviewer
Community Assistant
Research Assistant
Documentation Assistant
Reflection Coach
```

### Council Operating Modes

#### Single-Agent Mode

The Orchestrator selects one specialist for a bounded request. This should be the default when one role can serve the learner well.

#### Sequential Collaboration

One agent produces an output that another uses or verifies. For example, the Research Assistant gathers sources before the Documentation Assistant produces a grounded draft.

#### Parallel Consultation

Several agents independently evaluate distinct aspects of a complex task, such as architecture, learning design, assessment, and career evidence.

#### Reviewer Mode

One agent reviews another's structured result for defined quality, policy, or evidence criteria without rewriting it silently.

#### Human Council Mode

The Orchestrator prepares evidence, alternatives, and questions for an educator, mentor, reviewer, administrator, or learner to decide.

### Council Rules

- The Orchestrator defines a task and stop condition for every delegation
- Agents may not expand their own scope or permissions
- Agent-to-agent messages use typed, attributable contracts
- Sources and uncertainty travel with delegated output
- Conflicting conclusions are surfaced rather than averaged invisibly
- Final responses identify material limits and required human judgment
- Council activity ends when additional work no longer creates proportionate value

> "The best mentor knows when to ask for another expert."

---

## 4. The Ten AI Agents

### Agent I — Learning Coach

**Purpose:** Help learners understand goals, develop knowledge and skill, practice deliberately, overcome blockers, and choose an appropriate next learning step.

**Typical capabilities:** explanation, questioning, practice generation, study planning, misconception diagnosis, feedback interpretation, and journey guidance.

**Boundaries:** does not complete assessed learning work, issue credentials, or replace human educational judgment when consequence requires it.

### Agent II — Coding Mentor

**Purpose:** Help learners understand software development, reason about code, debug, test, improve quality, and become independent engineers.

**Typical capabilities:** code explanation, incremental hints, debugging strategy, test design, review, refactoring guidance, documentation, and secure-coding reminders.

**Boundaries:** does not claim unexecuted code works, conceal generated contribution, expose secrets, or bypass assessment rules.

### Agent III — Architecture Advisor

**Purpose:** Help builders reason about system boundaries, data, interfaces, tradeoffs, reliability, security, evolution, and architectural decisions.

**Typical capabilities:** requirement clarification, option comparison, diagrams, decision records, risk analysis, migration planning, and architecture review.

**Boundaries:** recommendations remain contextual and require accountable approval before high-impact implementation.

### Agent IV — Career Coach

**Purpose:** Help learners connect demonstrated capability to possible roles, opportunities, development plans, and professional communication.

**Typical capabilities:** capability-gap analysis, opportunity exploration, interview practice, development planning, and evidence-based positioning.

**Boundaries:** does not present predictions as destiny, make employment decisions, or infer sensitive traits for opportunity matching.

### Agent V — Portfolio Coach

**Purpose:** Help learners curate authentic evidence and communicate purpose, process, contribution, capability, and growth.

**Typical capabilities:** evidence selection, case-study structure, claim checking, audience adaptation, accessibility review, and Living Resume support.

**Boundaries:** does not invent experience, exaggerate contribution, or publish without learner authorization.

### Agent VI — Assessment Reviewer

**Purpose:** Support formative assessment, rubric application, evidence organization, quality review, and preparation for accountable evaluation.

**Typical capabilities:** criterion-level findings, practice feedback, evidence-gap detection, test-case generation, and reviewer calibration support.

**Boundaries:** does not independently issue high-stakes credentials, accuse misconduct, or remove human appeal.

### Agent VII — Community Assistant

**Purpose:** Help learners find spaces, ask useful questions, retrieve community knowledge, collaborate, and participate safely.

**Typical capabilities:** space discovery, duplicate-question detection, discussion synthesis, event and mentor discovery, knowledge curation proposals, and human moderation triage.

**Boundaries:** does not impersonate members, make final moderation decisions, or reveal private community content.

### Agent VIII — Research Assistant

**Purpose:** Help learners investigate questions using trustworthy, relevant, and attributable sources.

**Typical capabilities:** research planning, source discovery, evidence extraction, comparison, citation support, uncertainty mapping, and gap identification.

**Boundaries:** does not fabricate sources, present secondary synthesis as primary evidence, or conceal conflicting findings.

### Agent IX — Documentation Assistant

**Purpose:** Help builders preserve purpose, context, architecture, decisions, operation, testing, and lessons in durable forms.

**Typical capabilities:** structured drafting, decision-record preparation, content organization, consistency checks, change summaries, and handoff documentation.

**Boundaries:** does not publish authoritative records without review or rewrite history to hide failure or disagreement.

### Agent X — Reflection Coach

**Purpose:** Help learners turn experience, feedback, success, and failure into transferable insight and a meaningful next action.

**Typical capabilities:** reflective questioning, evidence review, pattern identification, assumption challenge, insight organization, and goal revision support.

**Boundaries:** does not claim the learner's voice, infer psychological states as facts, or store reflections without appropriate learner control.

Each agent should remain replaceable at the model and implementation level. Its enduring contract is defined by purpose, capability, policy, inputs, outputs, tools, evaluation, and boundaries—not by a particular model prompt.

---

## 5. The AI Orchestrator

The AI Orchestrator is the control plane that coordinates the Council and maintains one governed interaction with the learner.

### Core Responsibilities

#### Intent and Risk Classification

Determine the learner's intended outcome, active domain, stakes, ambiguity, assessment mode, safety considerations, and whether clarification is required.

#### Context Planning

Identify which learner, journey, content, project, assessment, portfolio, community, and memory context is necessary and permitted.

#### Agent Selection

Choose the smallest set of agents capable of completing the task well. Selection should consider expertise, authority, tools, evidence needs, model capability, latency, cost, and policy.

#### Work Planning

Define subtasks, dependencies, parallel opportunities, tool permissions, output contracts, verification, budget, and stop conditions.

#### Delegation

Send each agent a bounded task with scoped context and allowed tools. Delegation must preserve tenant, privacy, and learner boundaries.

#### Tool Governance

Authorize reads and writes separately, validate inputs and outputs, require confirmation where policy demands, and prevent duplicate or unauthorized side effects.

#### Synthesis

Combine agent outputs into a coherent learner response while preserving sources, disagreement, confidence, and actionable next steps.

#### Quality and Safety Review

Check grounding, role adherence, assessment integrity, privacy, safety, accessibility, harmful-action policy, and response completeness.

#### Memory Decision

Determine whether any information is eligible for temporary context, learner-approved insight, journey state proposal, or no memory at all.

#### Handoff and Escalation

Recognize when human care, educator authority, assessment review, moderation, identity support, security response, or another external professional is required.

### Orchestrator Boundaries

The Orchestrator must not create permissions, access unscoped data, redefine credential criteria, bypass human approval, or treat consensus among agents as truth. It coordinates accountable capabilities; it does not become an unaccountable authority.

---

## 6. Memory Layers

Memory should preserve useful continuity at the narrowest appropriate layer.

### Layer I — Request Memory

Contains the current input, attachments, selected object, tool state, and immediate processing context. It expires when the request completes except for necessary audit metadata.

### Layer II — Conversation Memory

Contains recent messages, active intent, agent contributions, unresolved questions, and learner-approved thread context. It supports coherent dialogue within a session or topic.

### Layer III — Workspace Memory

Contains scoped state for the active lesson, project, assessment, portfolio, community, or document. The owning LearningOS domain remains the source of truth.

### Layer IV — Journey Memory

Contains current learner goal, stage, milestones, blockers, evidence, and next-step state received from the Learner Journey Engine.

### Layer V — Learner Preference Memory

Contains durable learner-visible preferences such as language, explanation style, accessibility settings, AI boundaries, and communication choices.

### Layer VI — Approved Insight Memory

Contains learner-approved summaries, reflections, or enduring context with source, date, confidence, and correction history.

### Layer VII — Institutional Knowledge

Contains governed LearningOS content, policies, standards, rubrics, architecture, and community knowledge with version, provenance, lifecycle, and permissions.

### Memory Principles

- Source records remain separate from generated summaries
- Every memory has type, purpose, source, owner, scope, retention, and sensitivity
- Agents receive task-relevant projections rather than unrestricted memory access
- Learners can inspect and correct durable personal memory where practical
- Temporary memory expires predictably
- Visibility and deletion changes propagate to derived indexes
- Conflicting memory is surfaced and reconciled through governed rules
- Sensitive inference is not stored without necessity and authority
- Agent output does not become fact merely because it was remembered

Memory should support growth without freezing a person into their past.

---

## 7. AI Workflow

The canonical orchestration workflow is:

```text
Learner Question
  ↓
Intent Detection
  ↓
Context Retrieval
  ↓
Agent Selection
  ↓
Reasoning
  ↓
Response
  ↓
Reflection
  ↓
Memory Update
  ↓
Next Recommendation
```

### Learner Question

The workflow begins with a question, selected action, uploaded artifact, proactive dashboard prompt, or authorized system event.

### Intent Detection

The Orchestrator identifies what outcome is sought, which role is appropriate, whether the request is ambiguous, and which policy or risk class applies.

### Context Retrieval

The system retrieves only permitted, relevant, current context with provenance from identity, journey, workspace, knowledge, and approved memory systems.

### Agent Selection

The Orchestrator chooses one or more specialists and creates bounded tasks with output schemas and stop conditions.

### Reasoning

Agents use authorized models, retrieval, and tools to produce structured findings or proposals. Internal processing remains governed by time, tool, token, cost, and safety limits.

### Response

The Orchestrator validates and synthesizes a coherent response, streaming useful progress where appropriate without exposing hidden sensitive data or unverified internal speculation.

### Reflection

The learner is invited to apply, evaluate, explain, or reflect when doing so advances capability. For system workflows, reflection may be a quality check or human review.

### Memory Update

Only eligible information is proposed for memory. Domain writes, journey updates, and durable learner insights follow authorization, validation, confirmation, and provenance rules.

### Next Recommendation

The interaction ends with an explainable next action, independent continuation, human handoff, or an honest statement of what remains unknown.

The workflow may loop among Context Retrieval, Agent Selection, Reasoning, and validation when evidence is incomplete. It should terminate when the learner's purpose is met, blocked, unsafe, outside scope, or no longer benefits from more AI work.

---

## 8. AI Governance

AI governance makes the Council accountable to learners, organizations, Project Genesis principles, and the people responsible for LearningOS.

### Agent Registry

Every agent should have a governed record containing:

- Name, purpose, owner, and status
- Allowed use cases and prohibited actions
- Input and output contracts
- Context and memory classes
- Tools and permission scopes
- Model and provider policies
- Prompt or instruction versions
- Evaluation suites and release thresholds
- Human escalation paths
- Cost, latency, and availability expectations
- Change, deprecation, and incident history

### Model Governance

Models should be selected through evaluated capability rather than reputation alone. Provider, model, version, region, data use, retention, security, cost, latency, and failure behavior should be documented and replaceable.

### Tool Governance

Tools need typed schemas, authorization, input validation, output validation, idempotency where applicable, timeouts, rate limits, confirmation rules, audit, and clear separation of read and write capabilities.

### Release Governance

Agent, prompt, policy, retrieval, model, tool, and memory changes should be versioned, tested, staged, monitored, and reversible. Material behavioral changes require product, learning, privacy, safety, and engineering review.

### Evaluation

Evaluation should cover:

- Educational usefulness and learner independence
- Factual grounding and citation quality
- Agent selection and role adherence
- Tool correctness and side-effect safety
- Assessment and authorship integrity
- Privacy, tenant isolation, and consent
- Bias, fairness, accessibility, and multilingual behavior
- Safety, escalation, and refusal quality
- Memory accuracy and correction
- Latency, reliability, and cost
- Full-workflow outcome, not only agent response quality

### Human Oversight

Humans remain accountable for policy, high-impact action, credentials, disciplinary outcomes, community safety, security response, and institutional decisions. AI may prepare evidence and recommendations but should not obscure who decides.

### Incident Governance

AI incidents should support detection, containment, model or tool disablement, affected-user response, evidence preservation, correction, notification, root-cause analysis, evaluation updates, and institutional learning.

> "Artificial intelligence should coordinate knowledge, not merely generate text."

---

## 9. Product Implications

### Present One Mentor Experience

Learners should experience a coherent AI Mentor even when multiple specialists contribute. Agent identity should be shown when it improves trust, attribution, or understanding—not as technical theater.

### Let Learners Request Expertise

Interfaces may offer understandable choices such as Explain, Plan, Review Code, Research, Improve Portfolio, Reflect, or Ask Another Expert while allowing automatic routing.

### Explain Delegation

For consequential or multi-agent work, show which expertise was used, which sources and artifacts informed the result, where agents disagreed, and what requires human review.

### Preserve Progressive Disclosure

The primary response should remain clear and actionable. Sources, agent findings, tool activity, memory proposals, and workflow details should be inspectable without overwhelming the learner.

### Stream Meaningful Progress

Long workflows should communicate status such as retrieving sources, reviewing project evidence, or waiting for confirmation. Do not expose hidden chain-of-thought or fabricate activity.

### Make Actions Explicit

Distinguish suggestion, draft, preview, read, write, publish, submit, assess, message, and external action. Consequential writes require clear review and confirmation.

### Provide Memory Controls

Learners should be able to see when durable memory is proposed, accept or reject it where appropriate, correct saved context, and manage personalization boundaries.

### Degrade Gracefully

If one agent, model, tool, or provider is unavailable, the product should preserve core LearningOS workflows, state limitations honestly, and use evaluated fallback paths where safe.

### Measure Learner Outcomes

Product success should examine helpful next steps, task completion, understanding, independence, evidence quality, safe handoff, correction, and trust—not agent count, message count, or novelty.

### Avoid Over-Orchestration

The system should use one agent for simple tasks and reserve Council workflows for genuine complexity. More agents are not automatically more intelligent.

---

## 10. Engineering Implications

### Build an Orchestration Control Plane

The control plane should manage intent classification, policy, agent registry, context plans, workflow execution, model routing, tool authorization, budgets, verification, synthesis, memory proposals, and escalation.

### Use Typed Agent Contracts

Agent inputs and outputs should use versioned schemas for task, context references, constraints, findings, sources, confidence, proposed actions, and completion status. Free-form prose alone is insufficient for coordination.

### Separate Agents from Models

An agent is a governed capability contract. Models are replaceable execution resources selected through a gateway according to evaluated requirements and policy.

### Create a Provider and Model Gateway

Centralize model credentials, routing, regional and data policies, fallbacks, rate limits, cost attribution, latency, capability metadata, and provider removal. Product code should not bind agent identity to one provider model.

### Build Purpose-Bound Context Assembly

Context services should retrieve by actor, tenant, workspace, journey, purpose, data classification, lifecycle, version, and budget. Returned context needs stable references and provenance.

### Isolate Tool Execution

Run tools with least-privilege service identities, explicit scopes, protected secrets, validated schemas, network and data boundaries, timeouts, quotas, and sandboxing appropriate to risk.

### Orchestrate Durable Workflows

Long-running or multi-step jobs should support persisted state, retries, resumability, cancellation, idempotency, deadlines, human approval waits, and recovery after process failure.

### Stream Structured Events

The interface should receive typed events for text, citations, agent status, tool proposals, tool results, confirmations, errors, memory proposals, and completion. Event versions should preserve backward compatibility.

### Maintain Memory as Governed Records

Memory services need typed stores, source linkage, purpose, sensitivity, retention, correction, deletion, and access policy. Vector indexes are derived and rebuildable, not canonical memory.

### Prevent Recursive and Unbounded Delegation

Set maximum depth, agent count, iterations, token, time, tool, and cost budgets. Only the Orchestrator may delegate unless a governed workflow explicitly authorizes another pattern.

### Validate before Side Effects

Agent output should become a proposed command, not an automatic write. Authorization, business rules, current state, duplicate protection, and human confirmation should be evaluated at execution time.

### Preserve Full-Workflow Observability

Trace request, intent, context references, selected agents, model and prompt versions, tools, policy decisions, timings, cost, errors, validation, feedback, and outcome while minimizing sensitive content.

### Build Offline Evaluation and Online Monitoring

Maintain representative, adversarial, safety, privacy, accessibility, and regression evaluations for agents and workflows. Monitor drift, route changes, tool failures, cost anomalies, and outcome degradation after release.

### Support Replay without Unsafe Re-execution

Allow diagnostic replay of reasoning inputs and outputs with protected data, while preventing historical write tools from executing again accidentally.

### Engineer Kill Switches and Fallbacks

Disable an agent, tool, model, memory class, provider, or workflow independently. Provide safe fallback responses and human routes when critical capability is unavailable.

### Test Multi-Agent Failure Modes

Verification should cover wrong routing, conflicting agents, stale context, permission leakage, prompt injection, malicious artifacts, tool failure, duplicate writes, agent loops, partial streaming, model outage, memory corruption, cost exhaustion, human rejection, and incident shutdown.

### Version the Entire Decision Surface

Agent definition, orchestration policy, context plan, prompt, model, tool, retrieval index, memory policy, safety rule, and output schema should be traceable for consequential results.

---

## Canonical Status

The AI Orchestration Layer is Canonical Blueprint 024 and the authoritative Project Genesis reference for the specialized multi-agent architecture that powers LearningOS.

Future agents, models, tools, memories, workflows, dashboards, and AI governance should be evaluated by whether they coordinate knowledge responsibly, select the right expertise, preserve human agency, and turn collaborative intelligence into one meaningful next step for the learner.
