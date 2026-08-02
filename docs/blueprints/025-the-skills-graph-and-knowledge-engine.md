# Canonical Blueprint 025

## The Skills Graph & Knowledge Engine

| Record | Details |
|---|---|
| Blueprint number | 025 |
| Status | Canonical |
| Date established | August 2, 2026 |
| Authority | Project Genesis |
| Steward | Merchay Global Vision |
| Scope | LearningOS knowledge domains, skills, competencies, concepts, dependencies, learning objects, evidence, learner skill state, AI reasoning, personalization, career mapping, and analytics |
| Purpose | Define the complete skills graph, competency model, knowledge graph, dependency mapping, career mapping, and AI reasoning architecture for LearningOS. |

---

## Purpose and Authority

The Skills Graph & Knowledge Engine connects what exists to be learned with what a person can currently demonstrate, what they may need next, and where developed capability may lead. It provides the reasoning structure beneath journeys, recommendations, assessment, portfolios, mentorship, and career exploration.

The graph does not reduce a person to a score or assume that one path fits every learner. It represents versioned knowledge and evidence relationships, preserves uncertainty, and supports explainable choices. Learners retain agency over goals; educators and institutions retain accountable authority over governed requirements.

This blueprint defines the graph, skill nodes, competency levels, dependencies, AI integration, personalized learning, career mapping, analytics, future expansion, and engineering architecture through which LearningOS turns connected knowledge into intelligent learning.

> "Knowledge is a network, not a checklist."

---

## 1. Why Knowledge Graphs Matter

Traditional content structures often describe what is stored or assigned but not how knowledge, skill, evidence, and opportunity relate. A transcript may show courses completed while leaving unanswered which capabilities were developed, how strongly they were demonstrated, which prerequisites remain, and what the learner can build next.

Knowledge graphs matter because they:

- Represent relationships that hierarchies alone cannot express
- Connect concepts to skills, learning, practice, projects, and evidence
- Reveal prerequisites, alternatives, equivalencies, and transfer
- Help learners understand why a next step matters
- Allow prior evidence to change the recommended path
- Connect capability to portfolio and career opportunity
- Support interdisciplinary discovery
- Help authors detect gaps, duplication, and isolated content
- Give AI a governed reasoning structure
- Preserve how knowledge and competency definitions evolve

The graph should not claim certainty where relationships are inferred, disputed, contextual, or changing. It should identify provenance, version, confidence, authority, and the conditions under which a relationship applies.

A graph becomes educationally useful when its relationships lead to better understanding, practice, evidence, decisions, and opportunity—not merely when it contains many nodes and edges.

---

## 2. The Knowledge Philosophy

The Skills Graph & Knowledge Engine is governed by the following principles.

### Knowledge Is Relational

Understanding grows through connections among concepts, methods, evidence, applications, domains, and experiences.

### Skills Are Demonstrable

A skill is not simply a keyword or content tag. It describes an ability that can be practiced and supported by evidence under defined conditions.

### Competency Is Contextual

Capability may differ by domain, complexity, independence, quality, recency, and transfer. A single universal skill percentage cannot express every relevant distinction.

### Dependencies Need Evidence

Prerequisites and recommended sequences should be based on domain reasoning and learner outcomes, remain open to challenge, and support alternatives when equivalent preparation exists.

### Personalization Preserves Agency

The system should explain options and likely consequences without treating an inferred path as a command or predicted career as destiny.

### Evidence Outranks Activity

Content views, time spent, or course completion may inform context but do not establish competency without appropriate evidence.

### Provenance Creates Trust

Skill definitions, levels, mappings, dependencies, evidence rules, and career relationships should identify who or what established them and when they were reviewed.

### The Graph Is Revisable

Knowledge, work, tools, and roles change. Graph evolution should preserve historical interpretation while allowing current understanding to improve.

> "Every skill connects to a larger understanding."

---

## 3. The Knowledge Graph

The canonical evidence spine is:

```text
Knowledge Domain
  ↓
Skill
  ↓
Competency
  ↓
Concept
  ↓
Lesson
  ↓
Exercise
  ↓
Project
  ↓
Assessment
  ↓
Evidence
```

The spine shows one common relationship from domain to evidence. The actual graph supports many-to-many relationships:

- A Domain contains many Skills and Concepts
- A Skill may cross several Domains
- A Competency definition may combine several Skills
- A Concept may support many Skills
- A Lesson may develop several Concepts
- An Exercise may practice one or more skill components
- A Project may integrate and demonstrate many Skills
- An Assessment may evaluate evidence from multiple activities
- An Evidence item may support several bounded claims

### Graph Layers

#### Domain Layer

Represents disciplines, practices, industries, problem spaces, and knowledge communities.

#### Capability Layer

Represents skills, competencies, proficiency levels, performance criteria, and transferable capabilities.

#### Knowledge Layer

Represents concepts, principles, methods, terminology, standards, and relationships among ideas.

#### Learning Layer

Represents paths, modules, lessons, resources, examples, exercises, projects, and support.

#### Evidence Layer

Represents assessments, artifacts, observations, feedback, credentials, portfolio records, provenance, and validity.

#### Opportunity Layer

Represents career skills, roles, tasks, projects, contribution pathways, further learning, and external requirements.

### Graph Sources

Relationships may be:

- Canonical and approved by Project Genesis
- Governed by an organization or credential issuer
- Imported from an external standard or taxonomy
- Proposed by a subject-matter expert
- Inferred from learner evidence or analytics
- Suggested by AI and awaiting validation
- Learner-specific and private to a journey model

The system must not present all source classes as equally authoritative.

---

## 4. Skill Nodes

A Skill Node is the canonical representation of a defined ability within the graph.

### Required Skill Identity

A Skill Node should include:

- Stable identifier
- Preferred name and clear definition
- Domain and related concepts
- Skill type and transferability
- Observable performance statement
- Contexts and conditions of use
- Competency-level descriptors
- Evidence and assessment expectations
- Prerequisite and related skills
- Learning, exercise, project, and assessment relationships
- Career, role, task, and opportunity mappings
- Owner, source, authority, and review status
- Version, effective dates, and history

### Skill Types

- **Foundational knowledge:** durable facts, concepts, and principles
- **Technical skill:** use of methods, tools, systems, or procedures
- **Applied skill:** selection and use of capability in context
- **Cognitive skill:** reasoning, analysis, synthesis, evaluation, and problem-solving
- **Creative skill:** generation, design, adaptation, and original expression
- **Relational skill:** communication, collaboration, facilitation, and mentorship
- **Stewardship skill:** governance, ethics, safety, documentation, and succession
- **Meta-skill:** learning, reflection, adaptability, and self-direction

### Node Granularity

Skills should be specific enough to support meaningful evidence and broad enough to remain useful across more than one isolated task. The graph may relate atomic skill components to composite capabilities without pretending they are interchangeable.

### Skill Equivalence

Equivalent or overlapping skills require explicit mapping with direction, degree, context, version, evidence, and authority. Similar names do not establish equivalence automatically.

### Skill State versus Skill Definition

The Skill Node defines the shared capability. Learner Skill State represents an individual, evidence-bounded interpretation against a particular Skill Node version. The two must remain separate.

---

## 5. Competency Levels

The canonical learner competency progression is:

```text
Not Started
  ↓
Aware
  ↓
Practicing
  ↓
Capable
  ↓
Proficient
  ↓
Advanced
  ↓
Mentor
```

### Not Started

No meaningful evidence of engagement or capability is available. This state should not be interpreted as inability.

### Aware

The learner can recognize the skill, describe its purpose, and identify basic concepts or examples with support.

### Practicing

The learner can attempt components of the skill in structured conditions, use guidance, respond to feedback, and show emerging consistency.

### Capable

The learner can apply the skill independently in defined, representative contexts and produce acceptable evidence against published criteria.

### Proficient

The learner can apply the skill reliably across varied contexts, make sound tradeoffs, diagnose problems, and maintain quality with limited support.

### Advanced

The learner can handle complexity and novelty, integrate related capabilities, improve methods, create new value, and explain expert judgment.

### Mentor

The learner can help others develop the skill through explanation, observation, feedback, practice design, and responsible guidance while continuing their own learning.

### Competency Dimensions

A level decision may consider:

- Knowledge and understanding
- Independence and required support
- Complexity and novelty
- Quality and consistency
- Context range and transfer
- Judgment and explanation
- Recency and sustained performance
- Creation and contribution
- Ability to teach or mentor

Levels should be supported by evidence and clear criteria. Activity may suggest readiness for assessment but should not silently advance competency. Mentor is a demonstrated capability and responsibility, not a reward for popularity or time served.

---

## 6. Dependency Mapping

Dependency Mapping describes what knowledge or capability supports another and how strongly that relationship constrains a learner's path.

### Dependency Types

- **Required prerequisite:** credible evidence is necessary before the target activity
- **Recommended prerequisite:** preparation strongly improves readiness but alternatives may exist
- **Conceptual dependency:** understanding one concept supports another
- **Procedural dependency:** one skill is needed to execute another
- **Evidence dependency:** a claim requires another verified claim or artifact
- **Sequence dependency:** order matters because state or output carries forward
- **Co-requisite:** capabilities should develop together
- **Alternative prerequisite:** any one of several preparations may satisfy readiness
- **Equivalency:** a governed external or alternate capability can substitute
- **Conflict or exclusion:** two versions, rules, or states cannot apply together

### Dependency Record

Every governed dependency should be able to identify:

- Source and target nodes
- Dependency type and direction
- Strength or necessity
- Applicable competency level
- Context and exceptions
- Evidence and rationale
- Owner and approving authority
- Version and validity dates
- Learner impact and migration policy

### Readiness Reasoning

Readiness should combine dependencies with evidence, recency, prior learning, learner goals, support availability, and the consequence of failure. The system should distinguish:

- Ready
- Ready with support
- Evidence needed
- Missing required prerequisite
- Alternative route available
- Human review required
- Dependency uncertain or disputed

### Avoiding Rigid Paths

Dependency maps should support diagnostic challenge, recognition of prior learning, alternate evidence, accommodations, and educator override with reason. A recommended sequence should not become a hidden gate.

Analytics may suggest new dependencies, but correlation does not establish causation. Proposed graph changes require review before becoming canonical requirements.

---

## 7. AI Integration

AI uses the graph to reason over relationships, retrieve evidence, explain recommendations, and propose next actions within the AI Orchestration Layer.

### AI Reasoning Flow

```text
Learner Goal or Question
          ↓
Identity, Tenant, Consent, and Purpose
          ↓
Current Skill State and Evidence
          ↓
Graph Traversal and Dependency Evaluation
          ↓
Content, Project, Assessment, and Opportunity Retrieval
          ↓
Candidate Paths or Explanations
          ↓
Constraint, Policy, and Quality Validation
          ↓
Structured Recommendation with Provenance
          ↓
Learner Choice or Human Review
```

### Appropriate AI Capabilities

- Explain how concepts and skills relate
- Identify prerequisite gaps and alternate routes
- Recommend learning, practice, projects, or assessments
- Map learner evidence to candidate skills for review
- Suggest new graph relationships to expert curators
- Compare career requirements with demonstrated evidence
- Generate structured practice from approved skill criteria
- Detect stale, contradictory, duplicated, or isolated mappings
- Summarize why a competency state changed
- Help educators inspect learner pathways and graph coverage

### Structured AI Outputs

AI graph reasoning should return typed results such as:

- Node and version references
- Relationship paths
- Evidence references
- Candidate competency state
- Readiness conclusion
- Recommendation and alternatives
- Supporting and conflicting signals
- Confidence and limitations
- Required human review
- Expiration or reevaluation condition

### AI Boundaries

AI should not:

- Write canonical graph relationships without approval
- Promote a learner's verified competency solely from unreviewed inference
- expose another learner or tenant's evidence
- treat absence of data as absence of potential
- infer career destiny or personal worth
- use hidden sensitive traits to rank opportunity
- override credential, assessment, or organization requirements
- cite graph paths whose source and version cannot be identified

---

## 8. Personalized Learning

Personalized learning uses learner goals, evidence, preferences, constraints, and graph relationships to offer relevant paths while preserving choice and shared standards.

### Personalization Inputs

- Learner-selected aspiration and goals
- Current journeys and active commitments
- Demonstrated competency and evidence
- Diagnostic and formative assessment
- Prior learning and external credentials
- Practice patterns and feedback
- Accessibility, language, format, and scheduling preferences
- Organization or program requirements
- Available content, projects, mentors, and opportunities
- Learner correction and recommendation feedback

### Personalization Outputs

- Recommended next skill or concept
- Learning and practice sequence
- Project matched to capability and interest
- Assessment readiness and evidence needs
- Alternative route around a blocker
- Review or refresher for decayed or uncertain evidence
- Mentor, peer, or community support
- Career-skill exploration
- Explanation of why an option is relevant

### Path Construction

```text
Goal
  + Current Evidence
  + Required Capabilities
  + Dependencies
  + Learner Constraints and Preferences
  + Available Experiences
  = Explainable Candidate Journey
```

The result is a candidate journey, not an automatic command. Learners should be able to compare routes, understand tradeoffs, change direction, and ask for human guidance.

### Personalization Safeguards

- Do not lower capability standards silently
- Do not create permanent labels from early performance
- Avoid narrowing exploration through past behavior alone
- Make prerequisites and recommendation factors visible
- Provide an unpersonalized or reset path where practical
- Allow correction of inaccurate goals and evidence
- Review outcome equity across groups without using sensitive data improperly
- Distinguish organization requirements from AI suggestions

> "The graph knows the learner better than a transcript ever could."

This quotation expresses the graph's ability to represent richer evidence and relationships. It does not justify surveillance or claim that the system knows a person better than they know themselves.

---

## 9. Career Mapping

Career Mapping connects demonstrated skills and evidence to roles, tasks, projects, industries, contribution pathways, and future learning.

### Career Graph Nodes

- Career field and industry
- Role and role family
- Work task and responsibility
- Technical and transferable skill
- Competency expectation
- Credential or regulatory requirement
- Project and portfolio evidence
- Experience pattern
- Opportunity and organization
- Learning or transition pathway

### Mapping Sources

Career relationships may come from:

- Employer and practitioner research
- Occupational and skills standards
- Professional bodies and credential issuers
- Job and project analysis
- Educator and mentor review
- Learner outcomes and validated portfolio evidence
- Public labor-market data
- Organization-specific role frameworks

Sources, geography, industry, date, methodology, and confidence should remain visible because roles and markets change.

### Career Readiness

The engine may compare an opportunity's stated capabilities with learner evidence to identify:

- Demonstrated matches
- Relevant transferable skills
- Missing required evidence
- Skills under development
- Credentials or constraints requiring verification
- Portfolio projects worth highlighting
- Learning, project, or mentorship steps that may strengthen readiness

Readiness is not employability destiny. Hiring depends on context, opportunity, people, and factors the graph cannot fully represent. The system should avoid fabricated precision and discriminatory proxies.

### Career Exploration

Career Mapping should reveal adjacent and unexpected possibilities, not only optimize for the learner's past. Learners should be able to explore roles through skills, problems, values, environments, projects, and contribution types.

### Opportunity Feedback

Where appropriate and consented, verified outcomes may improve mappings. Employer or opportunity-provider feedback should never silently rewrite a learner's competency or become an unchallengeable hidden reputation score.

---

## 10. Knowledge Analytics

Knowledge Analytics examines the graph's quality, learner pathways, capability development, and system outcomes while protecting privacy and avoiding reduction of people to metrics.

### Graph Health Analytics

- Orphan, duplicate, or ambiguous skills
- Missing prerequisites and broken relationships
- Stale definitions and review dates
- Conflicting mappings and versions
- Coverage by domain, level, language, and accessibility
- Skills without learning, practice, project, assessment, or evidence paths
- Career mappings without current provenance

### Learning Analytics

- Common readiness gaps
- Path progression and meaningful completion
- Practice-to-capability relationships
- Project and assessment evidence attainment
- Alternative-route effectiveness
- Time and support required for defined milestones
- Reassessment and improvement patterns
- Learner-chosen recommendation usefulness

### Equity and Access Analytics

- Differential access to content, projects, mentors, and assessments
- Outcome differences requiring investigation
- Accessibility barriers
- Language and regional coverage
- Recommendation exposure and path narrowing
- Human-review and appeal patterns

Differences are signals for investigation, not automatic proof of cause or deficiency in a group.

### Career Analytics

- Skill demand changes with source and geography
- Transferable-skill pathways
- Evidence associated with opportunity transitions
- Mapping freshness and disagreement
- Credential and portfolio usefulness
- Emerging roles and declining mappings

### Governance Analytics

Analytics should identify data source, population, period, missingness, methodology, privacy treatment, uncertainty, and allowed decisions. Aggregate insights should not enable re-identification or unauthorized individual evaluation.

The system should measure whether graph intelligence helps learners understand relationships, make better choices, demonstrate capability, and find opportunity—not merely whether recommendations are clicked.

> "Understanding relationships creates intelligent learning."

---

## 11. Future Expansion

The Skills Graph & Knowledge Engine should evolve toward a portable, interoperable, multilingual, and human-governed representation of lifelong capability.

Future expansion may include:

- Cross-institution skill and competency interoperability
- Portable learner-controlled skill records
- Federated graph exchange without centralizing all personal evidence
- Recognition of prior learning across formal and informal contexts
- International and industry-specific skill mappings
- Multilingual concept and skill equivalence
- Dynamic project and apprenticeship pathways
- Team and organizational capability graphs
- Mentor and educator capability networks
- Research, entrepreneurship, civic, and creative contribution maps
- Time-aware skills reflecting technology and practice evolution
- Simulations comparing alternate learning and career paths
- Privacy-preserving aggregate graph learning
- Verifiable credentials connected to bounded skill claims
- Learner-governed personal AI that carries portable graph context

### Interoperability Principles

Expansion should preserve stable identifiers, source authority, version, relationship semantics, evidence provenance, learner consent, tenant boundaries, export, and correction.

### Human Governance

Domain communities, educators, practitioners, learners, organizations, credential issuers, and stewards should participate in graph governance. No model or platform should become the sole authority over what human capability means.

### Long-Term Goal

The long-term goal is not a complete graph that claims to know all knowledge. It is a living system that helps each generation understand more relationships, create stronger pathways, and leave better evidence for the next.

---

## 12. Engineering Implications

### Use a Versioned Graph Schema

Nodes and edges need stable identifiers, types, properties, provenance, authority, lifecycle, version, validity, and audit. Schema evolution should preserve historical interpretation.

### Separate Canonical, Organizational, and Learner Graphs

- **Canonical graph:** Project Genesis-approved definitions and relationships
- **Organizational graph:** tenant-governed programs, roles, standards, and mappings
- **Learner graph:** private goals, evidence relationships, competency state, and recommendations

Queries should combine allowed layers without copying or leaking data across boundaries.

### Store Skill Definitions Separately from Learner State

Skill Nodes and level criteria are shared definitions. Learner Skill State is a versioned projection supported by evidence, evaluation, source, confidence, recency, and review status.

### Model Edges as First-Class Records

Dependencies, equivalencies, mappings, and evidence links need identifiers, type, direction, source and target versions, context, confidence, owner, approval, and validity periods.

### Build a Graph Query Service

Provide typed, permission-aware operations for traversal, prerequisite resolution, pathfinding, evidence lookup, competency comparison, career mapping, and explanation. Bound depth, fan-out, and cost.

### Implement a Reasoning Tool Layer

AI agents should call governed graph tools that return structured paths and provenance rather than generate graph facts from prompt memory. Tool writes create proposals, not canonical changes.

### Use Provider-Neutral AI Execution

Graph reasoning agents should be independent from a specific model provider. Model selection, structured-output validation, retries, fallbacks, latency, cost, and policy should be controlled through the AI Orchestration Layer.

### Create an Evidence Evaluation Pipeline

Assessment and project events should produce candidate skill evidence. Deterministic rules, rubric results, authorized AI assistance, and human review update learner projections according to consequence.

### Preserve Event and Projection History

Skill-state changes should identify triggering evidence, prior state, criteria version, evaluator, decision method, date, expiration or review, and correction history.

### Support Temporal Queries

The engine should answer what a skill, dependency, career mapping, or learner state meant at a historical time, especially for credentials and portfolio evidence.

### Build Hybrid Retrieval

Combine graph traversal with lexical, semantic, and vector retrieval. Embeddings remain derived, version-linked, permission-aware, and rebuildable.

### Enforce Tenant and Evidence Privacy

Apply authorization before traversal, counts, recommendations, embeddings, analytics, and AI context. Aggregate analytics need minimum thresholds and re-identification controls.

### Cache with Safe Invalidation

Graph paths and recommendations may be cached by policy, graph version, tenant, learner state, and purpose. Permission, evidence, or graph changes should invalidate affected results.

### Validate Graph Integrity

Automated checks should identify cycles where forbidden, unreachable requirements, contradictory edges, missing versions, orphan evidence, expired mappings, and invalid authority.

### Evaluate Reasoning End to End

Test not only model output but graph selection, traversal, evidence use, structured result, explanation, policy, learner choice, and downstream outcome.

### Test Adversarial and Failure Conditions

Verification should cover malicious graph content, prompt injection, cross-tenant traversal, cyclic dependencies, stale evidence, contradictory mappings, model failure, tool timeout, incomplete paths, career bias, correction, rollback, and provider outage.

### Plan for Scale and Portability

Partition by domain and tenant where appropriate, support incremental indexing, preserve documented export formats, and avoid designs that make knowledge or learner evidence impossible to migrate.

---

## Canonical Status

The Skills Graph & Knowledge Engine is Canonical Blueprint 025 and the authoritative Project Genesis reference for LearningOS skill nodes, competency states, knowledge relationships, dependencies, AI reasoning, personalization, career mapping, and knowledge analytics.

Future skills, graph relationships, learner models, recommendations, career mappings, AI tools, and analytics should be evaluated by whether they preserve evidence, explain relationships, protect agency, and help every learner move from knowledge toward demonstrated capability and meaningful opportunity.
