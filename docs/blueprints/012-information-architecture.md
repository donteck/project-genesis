# Canonical Blueprint 012

## Information Architecture

| Record | Details |
|---|---|
| Blueprint number | 012 |
| Status | Canonical |
| Date established | August 2, 2026 |
| Authority | Project Genesis |
| Steward | Merchay Global Vision |
| Scope | LearningOS content, features, navigation, terminology, routes, permissions, search, and user journeys |
| Purpose | Define the complete organizational structure of LearningOS and establish how content, features, navigation, and user journeys form a coherent information architecture. |

---

## Purpose and Authority

LearningOS brings together learning, projects, evidence, growth, people, and identity. Without a coherent information architecture, those capabilities become separate features that force people to understand the internal organization of the product before they can accomplish meaningful work.

This blueprint establishes the canonical structure through which LearningOS organizes content and action. Home is the orienting root. Learn, Build, Prove, Grow, Community, and Account are the six domains. Each item, page, feature, and journey should have an explicit home within that structure and clear relationships to the domains around it.

This blueprint governs conceptual organization and navigation intent. Detailed visual design, route syntax, component behavior, permissions, and responsive presentation may evolve, but they should preserve the structure and principles defined here.

> "Clarity is kindness."

---

## 1. Why Information Architecture Matters

Information architecture determines whether people can form an accurate mental model of LearningOS. It answers where information belongs, how capabilities are named, which relationships are visible, and how a person moves from intention to action.

Clear architecture matters because it:

- Reduces the effort required to understand the product
- Makes features and content easier to find and remember
- Creates consistent expectations across pages and devices
- Connects learning activities to projects, evidence, and opportunity
- Gives new features a stable organizational home
- Prevents duplicated, contradictory, or orphaned experiences
- Supports accessible navigation and meaningful page structure
- Makes permissions, ownership, search, analytics, and URLs easier to reason about
- Allows engineering teams to preserve conceptual boundaries
- Helps LearningOS grow without becoming a collection of unrelated menus

Information architecture should be designed around the user's world, not the organization's departments, database tables, or implementation history. Internal complexity may be necessary, but it should not be transferred to the person trying to learn or build.

> "Good architecture reduces thinking about the interface so people can focus on learning."

---

## 2. The Four Navigation Questions

Every LearningOS page should help a person answer four questions without having to reconstruct the interface from memory.

### Question I — Where Am I?

The page should reveal the current domain, object, activity, and relevant position in a larger journey. Page titles, active navigation, breadcrumbs, step indicators, and contextual labels should agree.

### Question II — What Can I Do Here?

Primary and secondary actions should match the purpose of the page, the person's role, the state of the object, and available permissions. Hidden capability and excessive action density both weaken clarity.

### Question III — What Should I Do Next?

The interface should identify a meaningful next action based on progress, goals, dependencies, and context. Recommendations should explain their purpose and preserve the person's agency.

### Question IV — How Do I Return or Change Direction?

People should be able to return to the parent context, move to another domain, resume previous work, or recover from a wrong turn without losing progress.

These questions apply to public pages, authenticated workspaces, lessons, projects, assessments, community spaces, settings, and administrative experiences. A page that cannot answer them requires a clearer purpose or stronger context.

---

## 3. The Six LearningOS Domains

Home is the orienting root of LearningOS. Beneath it are six domains defined by the primary intention a person brings to the system.

### Domain I — Learn

**Intent:** Develop knowledge, understanding, and skill.

Learn contains:

- Discover and search
- Learning paths and roadmaps
- Courses, modules, and lessons
- Learning resources and reference materials
- Practice activities and formative feedback
- Saved learning and personal library
- Enrollments, active learning, and learning history
- AI tutoring and learning support

### Domain II — Build

**Intent:** Apply learning through creation and problem-solving.

Build contains:

- Projects and project workspaces
- Challenges, briefs, and requirements
- Templates, tools, and reusable assets
- Milestones, tasks, drafts, and iterations
- Collaboration and project feedback
- Builder journals, decisions, and reflection
- Published artifacts and contribution records
- Authoring experiences for permitted creator roles

### Domain III — Prove

**Intent:** Demonstrate, evaluate, and communicate capability.

Prove contains:

- Assessments, quizzes, and examinations
- Assignments, submissions, and rubrics
- Project demonstrations and reviews
- Skills evidence and competency records
- Certificates, credentials, and verification
- Portfolio artifacts and presentations
- Transcripts, achievements, and progress evidence
- Feedback, reassessment, and appeals where applicable

### Domain IV — Grow

**Intent:** Understand progress and choose the next meaningful direction.

Grow contains:

- Goals and development plans
- Progress, strengths, and growth areas
- Skills graph and capability profile
- Personalized recommendations and next steps
- Career, opportunity, and role pathways
- Mentorship goals and development history
- Analytics, reflection, and longitudinal growth
- Lifelong learning records and future plans

### Domain V — Community

**Intent:** Learn, build, contribute, and belong with other people.

Community contains:

- Cohorts, groups, academies, and organizations
- Discussions, questions, and shared resources
- Events, live classes, and calendars
- Peer collaboration and review
- Mentorship and educator relationships
- Member profiles and contribution recognition
- Community projects, showcases, and announcements
- Moderation, safety, conduct, and reporting

### Domain VI — Account

**Intent:** Manage identity, access, preferences, privacy, and services.

Account contains:

- Profile and identity
- Organizations, roles, and memberships
- Authentication and security
- Notifications and communication preferences
- Accessibility, language, and display preferences
- Privacy, consent, data, and connected services
- Plans, billing, orders, and subscriptions where applicable
- Help, support, legal information, and account lifecycle

Content belongs to the domain matching its primary user intent. Cross-domain relationships should be represented through contextual links and shared object views rather than duplicating canonical records.

---

## 4. The Navigation Principle

The LearningOS navigation principle is:

> **Orient first. Reveal what matters. Preserve a clear path forward.**

The primary navigation should use the stable domain language:

```text
Home
  ↓
Learn
  ↓
Build
  ↓
Prove
  ↓
Grow
  ↓
Community
  ↓
Account
```

This hierarchy expresses the complete top-level architecture. It also communicates a natural progression: orient at Home, gain capability through Learn, apply it through Build, demonstrate it through Prove, direct continued development through Grow, multiply it through Community, and govern personal identity and access through Account.

The arrows do not require a rigid linear journey. People may enter and move among domains according to purpose. Community and Account should remain globally reachable, while contextual navigation should connect related work across Learn, Build, Prove, and Grow.

Navigation should remain recognizable across viewport sizes and roles. Presentation may change from desktop sidebar to mobile tab bar, menu, or contextual header, but names, destinations, active states, and hierarchy should remain consistent.

> "The best navigation disappears because it feels natural."

---

## 5. The Three-Decision Design Goal

A person should be able to reach or confidently begin any common, high-value task within three meaningful decisions from Home.

A *decision* is a choice that requires the person to interpret options, not every technical click or interaction. Opening a menu, expanding a disclosure, or confirming a known choice does not automatically represent a separate navigation decision.

The preferred pattern is:

```text
Decision 1: Choose the domain
Decision 2: Choose the object, collection, or goal
Decision 3: Choose the action or next step
```

Examples include:

- Home → Learn → Active course → Continue lesson
- Home → Build → Current project → Resume milestone
- Home → Prove → Skills evidence → Share credential
- Home → Grow → Development plan → Choose next goal
- Home → Community → Cohort → Join discussion
- Home → Account → Security → Manage sign-in method

The goal applies to common tasks, not every rare administrative operation. Complex or high-risk actions may require additional steps for understanding, consent, security, or review.

If a common task requires more than three decisions, the team should examine whether navigation is exposing internal structure, whether naming is unclear, whether the task lacks a stable home, or whether Home should provide a direct contextual entry point.

---

## 6. Information Hierarchy

LearningOS information is organized through six levels:

### Level 0 — System

LearningOS is the complete product ecosystem, including public discovery, authenticated experiences, creator and educator workspaces, organizational contexts, and administration.

### Level 1 — Root

Home is the personalized orientation layer. It summarizes current context, active work, progress, relevant changes, and recommended next actions without becoming the canonical storage location for domain content.

### Level 2 — Domain

Learn, Build, Prove, Grow, Community, and Account provide the stable top-level mental model and ownership boundary for features and information.

### Level 3 — Collection or Workspace

Collections and workspaces organize related objects around a goal or context: a learning path, course, project workspace, evidence portfolio, growth plan, cohort, organization, or account area.

### Level 4 — Object

Objects are addressable entities with identity, ownership, state, metadata, and permissions: course, lesson, project, submission, credential, goal, discussion, event, profile, or membership.

### Level 5 — Activity or Detail

Activities and details are the focused actions or views within an object: study a lesson, complete practice, edit a project, submit evidence, review feedback, update a goal, reply to a discussion, or change a preference.

The hierarchy should be reflected consistently in page titles, URLs, breadcrumbs, navigation state, search results, analytics, authorization, and API resources. A deep technical hierarchy should not create a deep user hierarchy unless the distinction helps people understand or act.

> "Every page should have a purpose, a home, and a clear path forward."

---

## 7. Domain Relationships

The six domains are distinct but connected through the learner's development.

| From | Relationship | To | Example |
|---|---|---|---|
| Learn | Knowledge becomes applied work | Build | A lesson opens a related project brief |
| Build | Work produces evidence | Prove | A completed project becomes a portfolio submission |
| Prove | Evidence informs development | Grow | Assessment results update skills and next steps |
| Grow | Goals direct learning | Learn | A growth plan recommends a learning path |
| Grow | Goals direct application | Build | A capability gap suggests a project challenge |
| Community | People support every stage | Learn, Build, Prove, Grow | Mentors teach, review, validate, and guide |
| Account | Identity and access govern every stage | All domains | Roles, memberships, privacy, and preferences shape access |
| Home | Current context orients every stage | All domains | Active work and next actions link into domain objects |

The primary record for an object should have one canonical domain owner:

- A course belongs to Learn even when its credential appears in Prove.
- A project belongs to Build even when its artifact appears in a portfolio.
- A credential belongs to Prove even when it informs recommendations in Grow.
- A goal belongs to Grow even when it links to a course or project.
- A cohort belongs to Community even when it contains learning and events.
- A membership belongs to Account even when it grants access across domains.

Related domains may present contextual projections of an object, but updates should preserve a single source of truth and consistent permissions.

---

## 8. User Navigation Patterns

### Orientation Pattern

Home should answer: What is active? What changed? What needs attention? What is the most meaningful next action? It should prioritize continuity over promotion for returning users.

### Browse Pattern

Domain landing pages should support exploration through clear collections, filters, search, categories, and recommendations. Browse structure should use user language and reveal why an item is relevant.

### Resume Pattern

Active lessons, projects, submissions, plans, and conversations should be resumable from Home and their owning domain. Resume links should restore meaningful context and preserve progress.

### Search Pattern

Global search should find content and objects across domains, clearly label each result's type and home, respect permissions, and offer domain filters. Selecting a result should open its canonical location.

### Journey Pattern

Multi-domain journeys should use contextual next steps rather than forcing users back through top-level navigation. Completing a course may lead to a project; completing a project may lead to evidence submission; verified evidence may update growth planning.

### Workspace Pattern

When a person enters a focused course, project, assessment, or cohort workspace, local navigation may temporarily become primary. Global orientation and an exit path should remain available.

### Role Pattern

Learners, creators, educators, mentors, organization administrators, and platform administrators may receive different actions and workspaces. Stable domain language should remain shared; role-specific capability should appear inside the appropriate domain rather than create a separate competing architecture.

### State Pattern

Empty, loading, error, offline, restricted, completed, archived, and deleted states should explain what happened, preserve orientation, and offer an appropriate path forward.

### Responsive Pattern

Desktop, tablet, mobile, assistive technology, and keyboard navigation should preserve order, labels, active state, focus behavior, and access to critical actions even when visual presentation changes.

---

## 9. Product Implications

### Assign Every Feature to a Domain

Product proposals should name the primary domain, user intent, canonical object, parent context, and cross-domain relationships before interface design begins.

### Use Stable User Language

Learn, Build, Prove, Grow, Community, and Account should remain consistent across navigation, page titles, onboarding, help, notifications, and documentation. Internal team or technical terminology should not leak into the interface without user value.

### Design Home as Orientation, Not Storage

Home may aggregate summaries and next actions, but canonical content should remain owned by its domain. This keeps Home adaptable without creating duplicate information structures.

### Make Primary Action Obvious

Each page should have a defined purpose and one visually dominant next action when appropriate. Secondary actions should be available without competing equally for attention.

### Preserve Context across Journeys

Transitions among Learn, Build, Prove, and Grow should carry relevant context, show why the transition matters, and provide a clear return path.

### Design Search and Notifications by Domain

Results and notifications should identify the owning domain and object. Selecting one should lead to a stable, contextual destination rather than a generic dashboard.

### Validate with Real Navigation Tasks

Research and usability testing should include findability, labeling, information scent, resume behavior, cross-domain journeys, accessibility, and the Three-Decision Design Goal.

### Govern Architecture Changes

New top-level domains or changes to canonical ownership require evidence that existing domains cannot express the user intent clearly. Such changes should include migration, redirects, terminology updates, analytics continuity, and documentation.

---

## 10. Engineering Implications

### Align Routes with the Conceptual Model

Route groups and stable URLs should reflect canonical domains and objects where practical. Implementation frameworks may add internal structure, but public routes should remain meaningful and durable.

### Define Domain Ownership

Modules, services, APIs, schemas, events, and teams should have clear ownership boundaries aligned with Learn, Build, Prove, Grow, Community, and Account. Shared capabilities should expose documented contracts rather than duplicate domain logic.

### Preserve Canonical Object Identity

Cross-domain projections should reference stable identifiers and sources of truth. A portfolio view of a project should not become a conflicting project record.

### Centralize Navigation Metadata

Labels, destinations, active-state rules, permissions, icons, ordering, breadcrumbs, and analytics identifiers should derive from governed navigation definitions where feasible.

### Make Authorization Contextual

Navigation visibility and action availability should respect identity, organization, role, ownership, object state, and policy. Hiding a link is not authorization; server-side enforcement remains required.

### Support Deep Links and Recovery

Addressable pages should restore authentication, organization context, permissions, and meaningful object state. Missing, moved, restricted, or deleted destinations should preserve orientation and offer recovery.

### Build Accessible Semantics

Landmarks, heading hierarchy, navigation labels, focus management, skip links, keyboard operation, announcements, and page titles should express the same information hierarchy available visually.

### Instrument User Journeys

Analytics should measure navigation success, search refinement, abandonment, loops, dead ends, resume behavior, and cross-domain transitions while protecting privacy and avoiding surveillance-driven design.

### Test Architecture as Behavior

Automated and manual tests should verify route stability, breadcrumbs, active states, permissions, redirects, deep links, responsive navigation, keyboard access, and critical three-decision journeys.

### Version Structural Change

Renaming domains, moving canonical objects, or changing route contracts requires documented decisions, compatibility plans, redirects, content migration, event-schema updates, and monitoring.

---

## Canonical Status

Information Architecture is Canonical Blueprint 012 and the authoritative Project Genesis reference for the complete organizational structure of LearningOS.

Future content, features, navigation, routes, search, notifications, permissions, and user journeys should be evaluated by whether they preserve Home as the orienting root, fit clearly within the six domains, answer the four navigation questions, and help people reach common meaningful actions within three decisions.
