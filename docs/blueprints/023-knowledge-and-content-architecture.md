# Canonical Blueprint 023

## The Knowledge & Content Architecture

| Record | Details |
|---|---|
| Blueprint number | 023 |
| Status | Canonical |
| Date established | August 2, 2026 |
| Authority | Project Genesis |
| Steward | Merchay Global Vision |
| Scope | LearningOS domains, skills, pathways, courses, modules, lessons, exercises, projects, assessments, credentials, resources, metadata, relationships, search, AI context, governance, and archives |
| Purpose | Define the complete knowledge graph, content model, lifecycle, governance, versioning, and AI context architecture for LearningOS. |

---

## Purpose and Authority

LearningOS transforms knowledge into structured journeys, practice, projects, evidence, credentials, and opportunity. That transformation depends on more than individual content files. Every item needs identity, purpose, provenance, relationships, lifecycle, version, ownership, and an understood place in the learner's development.

The Knowledge & Content Architecture establishes a connected system in which content can be found, understood, trusted, reused, adapted, evaluated, and improved. It defines both what knowledge objects are and how they relate across learning, building, proving, growing, and career capability.

This blueprint governs the knowledge graph, core content types, lifecycle, versioning, relationships, AI integration, search, content governance, and product and engineering responsibilities throughout LearningOS.

> "Knowledge grows stronger when everything is connected."

---

## 1. Why Knowledge Architecture Matters

Content without architecture becomes a collection. It may be valuable in isolation but difficult to discover, sequence, reuse, validate, update, or connect to meaningful outcomes.

Knowledge architecture matters because it:

- Gives every content item a clear identity and purpose
- Connects learning material to capability and opportunity
- Reveals prerequisites, dependencies, alternatives, and next steps
- Supports reuse without uncontrolled duplication
- Preserves sources, authorship, review, and version history
- Makes search and AI retrieval more accurate and explainable
- Allows content to evolve without breaking active learner journeys
- Supports governance across creators, organizations, and domains
- Connects projects, assessments, evidence, and credentials
- Preserves historical knowledge after current content changes

Structure influences learning. A learner who can see where an idea came from, what it depends on, how it is practiced, and where it leads can form a stronger mental model than a learner encountering isolated pages.

Knowledge architecture should make complexity navigable without pretending that every discipline is linear. It must support hierarchies, graphs, sequences, alternatives, cycles, and interdisciplinary relationships.

---

## 2. The Knowledge Philosophy

The LearningOS knowledge system is governed by the following principles.

### Knowledge Is Connected

Ideas gain meaning through relationships to concepts, evidence, people, problems, methods, capabilities, and applications.

### Content Has Purpose

Every item should state what it helps a person understand or do, who it serves, and how it contributes to a larger journey.

### Provenance Creates Trust

Sources, authors, contributors, reviewers, methods, dates, and transformations should remain traceable.

### Structure Should Teach

Organization, sequencing, prerequisites, examples, practice, and relationships should help learners understand the domain—not merely help systems store files.

### Reuse Requires Context

A reusable object should preserve meaning, requirements, rights, version, and dependencies when used in a new pathway or organization.

### Knowledge Is Revisable

Approved content represents the strongest current understanding, not final truth. Correction should preserve history and explain change.

### Access Is Purposeful

Knowledge should be broadly discoverable where responsible while respecting privacy, licensing, security, assessment integrity, organizational boundaries, and cultural obligations.

### Application Completes Understanding

Content should connect to practice, projects, assessment, reflection, and contribution whenever the learning purpose requires demonstrated capability.

> "Content informs. Structure teaches."

---

## 3. The Knowledge Graph

The LearningOS Knowledge Graph is the connected model of domains, concepts, capabilities, content, activities, evidence, credentials, people, organizations, and opportunities.

The canonical learning-to-opportunity spine is:

```text
Domain
  ↓
Learning Path
  ↓
Module
  ↓
Lesson
  ↓
Exercise
  ↓
Project
  ↓
Assessment
  ↓
Certification
  ↓
Career Skill
```

The spine expresses a common progression, not a restriction that every relationship must be linear. A Domain may contain many Learning Paths. Lessons may support several projects. A Project may demonstrate multiple Career Skills. An Assessment may evaluate evidence from several modules or external experience.

### Graph Nodes

Nodes may represent:

- Domains, disciplines, topics, and concepts
- Capabilities, competencies, and career skills
- Learning paths, courses, modules, and lessons
- Resources, examples, exercises, and practice sets
- Projects, artifacts, templates, and tools
- Assessments, criteria, rubrics, and evidence
- Certificates, badges, and credential definitions
- Roles, occupations, opportunities, and contribution pathways
- Authors, reviewers, organizations, and issuers
- Sources, standards, policies, and historical versions

### Graph Edges

Edges are typed, directed when appropriate, attributable, and versioned. Examples include:

- contains
- requires
- introduces
- explains
- expands
- practices
- applies
- demonstrates
- assesses
- satisfies
- certifies
- maps to
- equivalent to
- alternative to
- supersedes
- cites
- authored by
- reviewed by
- governed by
- prepares for

### Graph Integrity

Every important edge should have an owner or source, relationship type, validity period where relevant, and version context. AI-suggested relationships should remain proposals until governed validation appropriate to consequence.

The graph should distinguish canonical relationships from inferred similarity, learner-specific recommendations, and temporary analytics.

---

## 4. Core Content Types

LearningOS should use typed content rather than one undifferentiated document model.

### Domain

A durable field of knowledge, practice, or capability that organizes concepts, pathways, experts, standards, and opportunities.

### Capability & Career Skill

A defined ability a person can develop and demonstrate. It includes scope, level, evidence expectations, related concepts, and opportunity relevance.

### Learning Path

A goal-oriented route through capabilities, content, practice, projects, assessments, and support. Paths may include prerequisites, alternatives, and choice points.

### Course

A governed learning experience with intended audience, outcomes, modules, policies, authorship, assessment, and completion conditions.

### Module

A coherent unit within a course or path that develops a meaningful subset of capability and organizes lessons and activities.

### Lesson

A focused learning object that introduces or develops understanding through explanation, examples, interaction, practice, and next-step relationships.

### Resource

A reference, reading, video, audio item, dataset, source, glossary entry, template, example, tool, or external material supporting learning or creation.

### Exercise & Practice Set

A structured opportunity to retrieve, apply, rehearse, experiment, receive feedback, and improve a defined component of capability.

### Project & Project Template

An authentic creation environment or reusable brief that integrates knowledge, decisions, implementation, testing, documentation, reflection, and evidence.

### Assessment, Criterion & Rubric

Governed definitions of what is evaluated, which evidence is accepted, how quality is interpreted, which assistance is allowed, and how results are reviewed.

### Credential Definition

A versioned claim an authorized issuer may grant when defined capability, evidence, and review requirements are satisfied.

### Knowledge Article

A curated explanation, guide, decision record, discovery, standard, or institutional knowledge object intended for reference and reuse beyond one course.

### Content Metadata

Every type should support relevant metadata such as title, summary, purpose, audience, language, accessibility, difficulty, duration estimate, owner, authors, sources, rights, status, version, dates, capabilities, prerequisites, organization, visibility, and review schedule.

Types may share composable content blocks, but their distinct semantics, permissions, validation, and lifecycle should remain explicit.

---

## 5. The Content Lifecycle

The canonical content lifecycle is:

```text
Draft
  ↓
Review
  ↓
Approved
  ↓
Published
  ↓
Maintained
  ↓
Archived
  ↓
Historical
```

### Draft

Content is being researched, authored, structured, and tested. It is not authoritative and is visible only to permitted collaborators.

### Review

Content is evaluated for purpose, accuracy, learning quality, accessibility, rights, safety, assessment integrity, technical behavior, and organizational requirements.

### Approved

An authorized reviewer or workflow has accepted a specific version for publication. Approval does not modify the version afterward.

### Published

The approved version is available to its intended audience through stable identity, permissions, search, graph relationships, and release metadata.

### Maintained

Published content is monitored and updated through new versions based on evidence, learner feedback, source changes, accessibility, defects, and scheduled review.

### Archived

Content is no longer offered for new use but remains available to authorized people, active historical records, migrations, audits, or learners whose prior activity depends on it.

### Historical

Content is preserved as part of institutional or intellectual history. It is clearly marked as non-current and linked to its successor, retirement reason, and original context where known.

Lifecycle transitions should be explicit, attributable, and governed. Emergency withdrawal for safety, rights, security, or serious inaccuracy may bypass the ordinary sequence while preserving incident and decision history.

---

## 6. Versioning Strategy

Versioning protects active learners, historical evidence, reproducibility, and responsible improvement.

### Version Identity

Every publishable content object should have:

- Stable object identifier across its lifetime
- Immutable version identifier
- Human-readable version label where useful
- Status and effective dates
- Parent or predecessor version
- Change summary and reason
- Author, reviewer, and approver attribution
- Compatibility and migration information

### Change Classes

#### Patch Change

Corrects presentation, spelling, accessibility metadata, broken links, or non-substantive defects without changing intended meaning or requirements.

#### Minor Change

Improves examples, explanation, structure, resources, or practice while preserving defined outcomes and evidence expectations.

#### Major Change

Changes outcomes, prerequisites, structure, assessment, credential meaning, rights, policy, or another contract affecting learner journeys and evidence.

### Published Immutability

A published version should not be silently rewritten. Corrections create a new version or a clearly recorded erratum proportional to impact.

### Learner Version Binding

Enrollments, submissions, assessment results, certificates, and portfolio evidence should record the relevant content, rubric, and credential versions. Active learners need explicit migration policy when a new version appears.

### Forking and Reuse

Organizations or creators may adapt eligible content through governed forks that preserve source provenance, license, parent version, modifications, and responsibility for maintenance.

### Deprecation and Supersession

Deprecated versions should identify successor, support window, migration guidance, unresolved incompatibilities, and archive date. Historical preservation should prevent old content from appearing current in search or AI responses.

---

## 7. Knowledge Relationships

Relationships give content instructional and operational meaning.

### Structural Relationships

- Domain contains Path
- Path includes Course, Module, Project, or Assessment
- Course contains Module
- Module contains Lesson
- Lesson contains or references Resource and Exercise

### Learning Relationships

- Concept is prerequisite for Concept
- Lesson introduces or reinforces Capability
- Exercise practices Capability
- Project applies and demonstrates Capability
- Assessment evaluates Capability
- Credential certifies a defined Capability claim

### Evidence Relationships

- Artifact results from Project
- Submission references Artifact version
- Feedback evaluates Submission
- Reflection interprets experience
- Evidence supports Capability claim
- Portfolio presents selected Evidence

### Opportunity Relationships

- Career Skill maps to Role or Opportunity
- Learning Path prepares for Career Skill
- Project simulates or contributes to real work
- Credential satisfies or supports an external requirement

### Provenance Relationships

- Content cites Source
- Version supersedes Version
- Adaptation derives from Content
- Person authors, reviews, or approves Content
- Organization governs or issues Content and Credential

### Community Relationships

- Discussion clarifies Content
- Question identifies a knowledge gap
- Mentor recommends Content
- Community resource extends a Lesson or Project
- Discovery motivates revision

Relationship display should help people answer: What does this depend on? What does it help me do? What should I explore next? What evidence does it produce? Who created and verified it?

> "Every lesson should know where it came from and where it leads."

---

## 8. AI Integration

AI should help people discover, understand, adapt, and improve knowledge while preserving provenance, authority, learner agency, and content governance.

### AI Context Architecture

```text
Learner Question or Task
          ↓
Identity, Permission, and Workspace Scope
          ↓
Journey, Capability, and Content Relationships
          ↓
Permission-Aware Retrieval
          ↓
Version, Provenance, Freshness, and Authority Filters
          ↓
Context Assembly within Purpose and Budget
          ↓
Model Guidance or Structured Proposal
          ↓
Grounding, Citation, Safety, and Policy Validation
          ↓
Learner Response, Action, or Human Review
```

### Appropriate AI Capabilities

- Retrieve relevant content and explain relationships
- Adapt explanation and examples to learner context
- Generate practice proposals from approved capabilities
- Suggest missing metadata or graph relationships
- Summarize content with source links and version context
- Identify stale, duplicated, conflicting, or isolated knowledge
- Support translation and accessibility transformations
- Help authors draft structured content and assessments
- Recommend governed next steps from the Journey Engine
- Assist reviewers with checklists and evidence organization

### AI Context Rules

- Apply the same permissions as direct content access
- Prefer approved and published content for learner guidance
- Identify historical, archived, draft, inferred, or external material explicitly
- Retain content identifiers and version provenance
- Do not allow embeddings or indexes to bypass deletion or visibility changes
- Distinguish source facts from model synthesis
- Cite sources at the level needed for verification
- Respect licensing, attribution, privacy, assessment, and organization boundaries
- Keep learner and tenant context isolated
- Require human approval for authoritative content publication

Generated content should enter the lifecycle as Draft. AI should not silently create, approve, publish, or revise canonical knowledge.

---

## 9. Search Architecture

Search should help people discover the right knowledge in context, not merely return text containing similar words.

### Search Modes

- **Lexical search:** exact words, titles, phrases, identifiers, and terminology
- **Semantic search:** meaning and conceptual similarity
- **Graph search:** prerequisites, related capabilities, paths, evidence, and successors
- **Faceted search:** type, domain, level, language, organization, status, format, and accessibility
- **Personal search:** learner-authorized history, saved content, projects, evidence, and communities
- **Command search:** direct navigation and permitted actions

### Ranking Signals

Ranking may consider:

- Query relevance
- User intent and selected domain
- Content authority and lifecycle status
- Current version and freshness
- Capability and journey fit
- Prerequisite readiness
- Accessibility and language fit
- Quality and review status
- Organization and role context
- Learner-controlled preferences

Popularity should not overpower relevance, authority, accessibility, or learner purpose.

### Search Result Requirements

Results should identify:

- Title and content type
- Purpose or relevant excerpt
- Owning domain and canonical location
- Lifecycle or version status where material
- Capability, path, or project relationship
- Source or organization authority
- Accessibility and format information where useful
- Why the result matched or was recommended

### Permission and Privacy

Permission filtering must occur before results, counts, snippets, autocomplete, facets, semantic retrieval, and AI context are returned. Unauthorized content should not be inferable from search behavior.

### Search Quality

Evaluation should cover relevance, zero-result queries, reformulation, task success, diversity, stale results, permission leakage, multilingual behavior, accessibility, and connection to meaningful action.

> "Knowledge is most valuable when it can be discovered, understood, and applied."

---

## 10. Content Governance

Content governance establishes who may create, review, approve, publish, maintain, archive, and interpret knowledge.

### Governance Roles

- **Author:** creates or revises draft content
- **Contributor:** proposes additions, corrections, examples, or translations
- **Subject Reviewer:** evaluates accuracy and disciplinary quality
- **Learning Reviewer:** evaluates pedagogy, alignment, practice, and assessment
- **Accessibility Reviewer:** evaluates inclusive access and alternatives
- **Rights Reviewer:** verifies sources, attribution, license, privacy, and consent
- **Approver:** accepts a version for publication within delegated authority
- **Publisher:** executes the governed release
- **Maintainer:** monitors current content and coordinates revision
- **Archivist:** preserves retired versions and historical context
- **Steward:** governs taxonomy, policy, quality, succession, and cross-domain integrity

Roles may be combined for low-risk content but should use separation of duties where consequence, conflict, credentialing, or institutional authority requires it.

### Governance Requirements

Every governed content type should define:

- Ownership and delegated authority
- Required metadata and validation
- Review criteria and approval path
- Publication and audience rules
- Maintenance owner and review schedule
- Feedback and correction process
- Rights, attribution, privacy, and licensing
- AI assistance disclosure and review
- Deprecation, archive, and historical retention
- Exception, escalation, and appeal paths

### Quality Dimensions

Content quality includes accuracy, purpose alignment, clarity, evidence, learning effectiveness, accessibility, inclusiveness, safety, currency, usability, rights, provenance, and maintainability.

Governance should not become a barrier to responsible contribution. Templates, progressive permissions, transparent queues, review service levels, and scoped publication can preserve quality while widening participation.

---

## 11. Product Implications

### Make Structure Visible to Learners

Show goals, prerequisites, progress, capabilities, projects, assessments, and next relationships without overwhelming the primary activity.

### Give Every Object a Canonical Home

Content may appear in dashboards, paths, search, AI, and communities, but it should link to one governed identity and current version.

### Support Reuse without Duplicate Drift

Authors should be able to reference shared objects, pin versions, receive update notices, compare changes, and choose governed migration rather than copy content blindly.

### Design Authoring around Types and Purpose

Authoring interfaces should adapt metadata, structure, validation, workflow, and preview to the content type instead of presenting one generic rich-text editor.

### Show Provenance and Status

Learners and reviewers should be able to identify author, source, organization, version, publication state, recency, and corrections at an appropriate depth.

### Connect Content to Action

Lessons should lead to practice, projects, assessment, reflection, related knowledge, or a justified next step. Reference material should reveal where it applies.

### Build Feedback into Maintenance

Users should be able to report inaccuracy, accessibility barriers, broken links, outdated material, rights concerns, and unclear learning paths with traceable resolution.

### Treat Historical Content Carefully

Archived and historical items should remain accessible when authorized but clearly marked and excluded from default current recommendations.

### Preserve Organizational Context

Organizations may curate, restrict, adapt, and sequence content within delegated authority while maintaining source provenance and tenant boundaries.

### Evaluate Knowledge Outcomes

Product measures should include discovery success, understanding, reuse, application, graph completeness, maintenance health, correction time, accessibility, and evidence created—not content volume alone.

---

## 12. Engineering Implications

### Use a Typed Content Registry

Define stable identifiers, type schemas, metadata requirements, lifecycle, validation, ownership, and extension mechanisms for every core content type.

### Separate Identity, Version, and Placement

A content object has stable identity; a version is immutable content and metadata; a placement connects a selected version to a path, course, module, organization, or experience.

### Model Relationships as First-Class Records

Graph edges should include type, source and target, direction, provenance, version bounds, status, owner, confidence where inferred, and audit history.

### Preserve Immutable Published Versions

Use versioned records and durable asset references. Published content, submissions, assessment results, credentials, and portfolio evidence should remain reproducible against their bound versions.

### Build Workflow State Explicitly

Draft, review, approval, publication, maintenance, deprecation, archive, and historical transitions need authorized commands, guards, events, notifications, and audit.

### Implement Permission-Aware Indexing

Lexical, semantic, vector, graph, and analytics indexes must carry tenant, visibility, lifecycle, and version constraints. Revocation and deletion should propagate predictably.

### Create an AI Context Service

Context assembly should accept actor, tenant, purpose, workspace, journey, query, allowed content classes, version policy, and budget, then return ranked passages and graph facts with provenance.

### Keep Embeddings Derived and Rebuildable

Embeddings should reference content versions, model, chunking policy, language, permissions, and creation time. They are derived indexes, not canonical knowledge.

### Validate Structured Content

Schemas, references, required blocks, accessibility metadata, broken links, graph integrity, assessment contracts, and publication rules should be validated automatically where possible.

### Orchestrate Long-Running Processing

Imports, media transforms, transcription, translation, indexing, embedding, link checks, AI analysis, export, and publication should use observable, retryable, idempotent jobs.

### Protect Rights and Sensitive Content

Assets and text need licensing, attribution, privacy classification, malware scanning, signed access, retention, territorial or audience restrictions where applicable, and takedown workflows.

### Support Portable Import and Export

Content packages should preserve structure, versions, relationships, metadata, assets, rights, and provenance in documented formats, with validation before import.

### Observe Knowledge Health

Monitor broken relationships, orphan nodes, stale review dates, outdated sources, failed indexing, zero-result searches, inaccessible media, duplicated content, and unresolved reports.

### Test Complete Lifecycles and Boundaries

Verification should cover authoring, concurrent revision, review, rejection, approval, publication, reuse, forking, learner version binding, migration, search permissions, AI grounding, correction, withdrawal, archive, historical display, export, and restoration.

### Plan for Taxonomy and Schema Evolution

Content types, metadata, relationship vocabularies, and graph models will change. Migrations should preserve identifiers, versions, evidence references, search continuity, and historical interpretation.

---

## Canonical Status

The Knowledge & Content Architecture is Canonical Blueprint 023 and the authoritative Project Genesis reference for the LearningOS knowledge graph, content model, lifecycle, governance, versioning, AI context, and search architecture.

Future content types, authoring, learning paths, relationships, versions, retrieval, AI guidance, search, publication, maintenance, and archives should be evaluated by whether they make knowledge connected, trustworthy, discoverable, understandable, and applicable.
