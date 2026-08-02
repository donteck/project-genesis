# Canonical Blueprint 034

## The Frontend Architecture

| Record | Details |
|---|---|
| Blueprint number | 034 |
| Status | Canonical |
| Date established | August 2, 2026 |
| Authority | Project Genesis |
| Steward | Merchay Global Vision |
| Scope | LearningOS frontend layers, design system, components, layouts, pages, features, state, responsiveness, accessibility, performance, testing, and engineering organization |
| Purpose | Define the complete frontend architecture, design system philosophy, component hierarchy, layouts, state management, accessibility standards, responsive strategy, performance principles, and engineering organization for LearningOS. |

---

## Purpose and Authority

The Frontend Architecture defines how LearningOS turns product purpose, domain capabilities, and design principles into a coherent learner experience. It establishes layers, boundaries, shared language, accessibility requirements, responsive behavior, state ownership, performance expectations, and an engineering structure that can evolve without fragmenting the interface.

This blueprint governs every first-party LearningOS web experience and informs other client applications where the same principles apply. It defines responsibilities and contracts rather than permanently binding the platform to one framework or rendering strategy.

> "Interfaces should reduce thinking, not increase it."

---

## 1. Why Frontend Architecture Matters

The frontend is where learners experience the promises expressed by every other LearningOS architecture. Identity becomes a sign-in and recovery experience. Knowledge becomes a navigable path. AI becomes a conversation. Projects become a workspace. Assessment becomes feedback. Reliability becomes preserved work. Privacy becomes understandable control.

Frontend architecture matters because it:

- Creates a consistent language across journeys and domains
- Makes the correct interaction easier to build than an inconsistent one
- Preserves accessibility as the platform grows
- Clarifies where design, state, domain, and rendering responsibilities belong
- Reduces duplication without creating universal components that understand everything
- Allows product teams to deliver independently within shared boundaries
- Protects performance and resilience across devices and networks
- Makes interface behavior testable and observable
- Supports gradual framework and design evolution
- Helps every screen answer what the learner can understand and do next

Without architecture, local convenience compounds into visual inconsistency, state confusion, inaccessible controls, fragile pages, oversized bundles, and journeys that feel like unrelated products.

---

## 2. The Frontend Philosophy

LearningOS frontends follow these principles.

### Learning Before Interface

The interface exists to help a person understand, act, create, reflect, and grow. Visual novelty must not compete with that purpose.

### Meaning Before Reuse

Components are shared when they express the same responsibility and interaction contract, not merely because they look similar.

### Accessibility From the Beginning

Semantic structure, keyboard access, focus, contrast, motion, language, error recovery, and assistive technology behavior are design inputs—not remediation tasks.

### State Has an Owner

Every state belongs to the URL, server, domain workflow, feature, form, or local component. State is placed at the narrowest durable level that owns its meaning.

### The Server and Client Collaborate

Rendering and data strategies follow interaction needs, privacy, freshness, resilience, and performance. The client is not the default home for all logic or data.

### Progressive Enhancement Protects Access

Core journeys should remain understandable and recoverable when scripts are delayed, networks are weak, optional integrations fail, or advanced capabilities are unsupported.

### Consistency Enables Confidence

Repeated patterns should behave predictably across pages, modalities, breakpoints, and domains. Exceptions require a learner-centered reason.

### Boundaries Enable Evolution

Features depend on stable system and domain contracts, not provider details, persistence models, or unrelated feature internals.

> "Consistency creates confidence."

---

## 3. The Frontend Pyramid

The frontend is organized from visible experience to durable foundation.

```text
Experience
    ↓
Features
    ↓
Pages
    ↓
Layouts
    ↓
Components
    ↓
Design System
    ↓
Foundation
```

### Experience

The complete learner perception across navigation, content, actions, feedback, accessibility, performance, trust, and continuity.

### Features

Purposeful workflows such as onboarding, learning a lesson, completing a project, receiving mentor guidance, or publishing evidence.

### Pages

Route-level compositions that establish data boundaries, metadata, access policy, page purpose, and feature placement.

### Layouts

Stable spatial and navigational structures that compose the application shell, workspaces, reading experiences, and responsive regions.

### Components

Reusable interaction and presentation units with explicit semantics, variants, states, and composition contracts.

### Design System

Tokens, primitives, patterns, content guidance, accessibility behavior, documentation, and governance that create shared interface language.

### Foundation

Rendering, routing, styling, type, data, testing, localization, security, telemetry, build, and browser-support capabilities.

Dependencies should generally point downward. Lower layers must not import feature or page knowledge. Higher layers compose lower capabilities without bypassing their contracts.

---

## 4. Foundation Layer

The Foundation Layer supplies frontend capabilities that every upper layer can rely on.

### Foundation Responsibilities

- Application runtime and rendering modes
- Routing, navigation, metadata, and URL conventions
- Type system, schema validation, and generated contracts
- Styling pipeline, tokens, themes, and asset handling
- Data clients, authentication context, and request policy
- Error, loading, empty, offline, and recovery infrastructure
- Internationalization, localization, and bidirectional layout support
- Accessibility utilities and automated checks
- Logging, analytics, performance, and trace correlation
- Testing tools, fixtures, mocks, and browser environments
- Build, code splitting, deployment, and compatibility targets

### Browser and Device Support

LearningOS publishes a support policy based on learner access, security support, usage evidence, assistive technology, institutional environments, and the cost of exclusion. Unsupported capabilities degrade intentionally rather than failing silently.

### Type and Contract Boundaries

External data is treated as unknown until validated. API-generated types may describe transport, but feature and domain adapters translate transport objects into frontend models appropriate to the interaction.

### Security

The foundation provides safe defaults for content rendering, navigation, cookies, tokens, forms, external links, uploads, and browser security policy. Secrets and privileged authorization never depend on client code.

### Failure Foundations

Global boundaries handle unexpected rendering and route failures, while local boundaries keep unrelated regions usable. Error interfaces preserve correlation details for support without exposing sensitive internals.

The foundation is intentionally small. Business behavior does not become a foundation utility merely because several features need it.

---

## 5. Design System

The LearningOS Design System is the shared language through which Project Genesis expresses clarity, confidence, care, and action.

### System Layers

1. **Principles:** clarity, accessibility, consistency, agency, focus, and trust
2. **Tokens:** color, typography, spacing, size, radius, elevation, motion, and layering
3. **Primitives:** semantic, accessible building blocks with minimal visual opinion
4. **Components:** governed controls and display patterns
5. **Patterns:** recurring combinations such as forms, feedback, progress, and disclosure
6. **Templates:** reference compositions for common page and workspace structures
7. **Guidance:** content, behavior, accessibility, usage, and migration documentation

### Design Tokens

Tokens express semantic intent such as surface, text, border, action, success, caution, danger, focus, and progress. Feature code must not rely on arbitrary values when a governed semantic token exists.

Tokens support themes and contrast modes without changing component meaning. Changes are versioned, visually tested, and evaluated across the complete component inventory.

### Governance

Every system contribution includes purpose, anatomy, semantics, variants, states, responsive behavior, content guidance, accessibility contract, examples, tests, and owner. New components must demonstrate a recurring need that composition cannot already satisfy.

### Documentation

The system provides interactive examples for default, hover, focus, active, disabled, loading, error, empty, long-content, localized, reduced-motion, high-contrast, and responsive states where applicable.

### Evolution

Components and tokens have experimental, supported, deprecated, and retired states. Breaking changes include codemods or migration guidance when practical, consumer visibility, and an adoption window.

The design system is a product for builders and a consistency promise to learners.

---

## 6. Components

Components encapsulate a coherent semantic and interaction responsibility.

### Component Categories

- **Primitives:** visually minimal semantic building blocks
- **Controls:** buttons, links, fields, selectors, toggles, and disclosures
- **Feedback:** alerts, status, validation, progress, loading, and notifications
- **Data display:** lists, tables, cards, timelines, badges, and visualizations
- **Navigation:** breadcrumbs, tabs, menus, pagination, and wayfinding
- **Overlays:** dialogs, popovers, tooltips, and contextual panels
- **Content:** headings, prose, code, media, citations, and learning callouts
- **Feature components:** domain-aware compositions owned inside one feature

### Component Contract

A component defines:

- Semantic element and accessible name strategy
- Required and optional properties
- Controlled and uncontrolled behavior where appropriate
- Variants based on meaning rather than arbitrary styling
- Loading, empty, error, disabled, and read-only states
- Keyboard and focus behavior
- Responsive and localization behavior
- Event callbacks and side-effect boundaries
- Test and documentation expectations

### Composition

Composition is preferred over large configuration objects and boolean combinations. Components expose slots or subcomponents when consumers need meaningful structure while preserving invariants.

### Domain Isolation

Shared components do not fetch domain data, import feature state, authorize business actions, or understand provider payloads. Feature components may do domain-specific work but remain within the owning feature boundary.

### Feedback

Actions provide immediate, accessible feedback. Optimistic updates are used only when reversal is understandable and data risk is low. Irreversible or consequential actions wait for authoritative confirmation.

> "Every component teaches the learner how the platform works."

---

## 7. Layouts

Layouts create persistent spatial relationships, navigation confidence, and responsive structure.

### Canonical Layouts

LearningOS should maintain a small family of layouts:

- **Application shell:** top bar, primary navigation, workspace, context panel, and status region
- **Dashboard:** prioritized overview, progress, recommendations, projects, and reflection
- **Learning:** focused content, navigation, practice, notes, and mentor support
- **Workspace:** tools, artifacts, documentation, preview, and contextual guidance
- **Reading:** constrained long-form content with outline and supporting references
- **Administrative:** dense but accessible management and reporting workflows
- **Public:** discovery, marketing, authentication entry, and published portfolios

### Layout Responsibilities

Layouts own persistent regions, skip links, landmarks, navigation, responsive arrangement, scroll boundaries, focus restoration, and shared loading or error behavior. They do not own page-specific business rules.

### Nested Layouts

Nested layouts preserve context across related routes and allow stable navigation without forcing every page into one universal shell. Nesting depth is kept understandable and must not create competing scroll containers or landmark duplication.

### Context Panel

The context panel contains optional supporting information, mentor guidance, outline, activity, or properties. Primary tasks remain possible without it, and its content relocates predictably on small screens.

### Layout Stability

Reserved space, predictable loading structures, stable typography, and known media dimensions reduce visual movement. Layout behavior is tested with long translations, zoom, dynamic text, errors, and sparse content.

---

## 8. Pages & Features

Pages establish route boundaries; features deliver domain-centered outcomes.

### Page Responsibilities

A page owns:

- Route parameters, search parameters, and canonical URL behavior
- Metadata and discoverability policy
- Authentication and coarse access boundary
- Initial data composition and rendering strategy
- Selection of layouts and features
- Route-level loading, not-found, and error behavior

Pages remain thin. Domain transformations, interaction rules, and reusable workflows belong to features or domain adapters.

### Feature Responsibilities

A feature may own:

- User story and domain language
- Feature-specific components and forms
- Server actions or use-case clients
- Local workflows and state machines
- Data adapters, validation, and permissions presentation
- Feature-level analytics and observability
- Tests, fixtures, documentation, and ownership

### Vertical Slices

Features are organized as vertical slices when practical. A project-submission feature keeps its interface, schema, workflow, tests, and adapters near one another instead of distributing them across global technical folders.

### Cross-Feature Interaction

Features do not import private internals from one another. Shared domain contracts, public feature entry points, events, URL state, or page composition coordinate interactions.

### Feature Lifecycle

Feature flags separate deployment from release. Every flag has purpose, owner, audience, default, audit history, expiration, and removal plan. Experiment logic is isolated and cannot permanently fork the product unnoticed.

---

## 9. State Philosophy

State management begins by identifying authority and lifetime, not by choosing a library.

### State Categories

#### URL State

Navigation, filters, pagination, tabs, and shareable selections belong in route or search parameters when users should bookmark, refresh, or share them.

#### Server State

Authoritative domain data remains on the server and is accessed through typed, authorized contracts. Clients cache and revalidate it according to freshness and consistency needs.

#### Workflow State

Multi-step and long-running processes use explicit state machines or server-owned workflow state when transitions, retries, intermediate outcomes, and recovery matter.

#### Form State

Draft input, validation, dirty state, submission, and field errors remain close to the form. Valuable or long-lived drafts receive durable preservation.

#### Feature State

State shared by a bounded feature is owned by that feature and exposed through a narrow interface.

#### Local UI State

Disclosure, hover, temporary selection, and other ephemeral presentation state remains inside the smallest component that owns it.

#### Global Client State

Truly application-wide client state is rare and limited to concerns such as active session presentation, theme, locale, or cross-route transient notices. A global store is not a default integration bus.

### Derived State

Derived values are computed from authoritative sources rather than stored in parallel. If state can be calculated safely, duplicating it creates synchronization risk.

### Mutations

Mutations validate on the server, enforce authorization at the resource, use idempotency where retries occur, and return explicit domain outcomes. Optimistic interfaces include rollback and reconciliation behavior.

### Offline and Conflict

Offline capability is chosen per journey. When concurrent edits are possible, the product exposes conflict resolution appropriate to the data instead of silently overwriting work.

---

## 10. Responsive Strategy

Responsive design adapts purpose and hierarchy to available space, input method, content, user preferences, and device capability.

### Content-Led Breakpoints

Breakpoints respond to where layouts lose clarity rather than mirroring a fixed list of popular devices. Shared tokens create consistency, and container queries allow components to respond to their actual region.

### Mobile Priority

Small screens expose the primary task, next action, essential context, and safe navigation first. Secondary panels become drawers, sheets, inline sections, or later steps without disappearing permanently.

### Large Screens

Additional space supports comparison, persistent context, and productive work; it does not justify unbounded line length, scattered actions, or decorative emptiness.

### Input and Capability

Interfaces support keyboard, touch, pointer, voice, zoom, orientation change, and assistive technology. Hover is never the only path to information or action. Targets remain usable without assuming precise pointing.

### Responsive Content

Tables, diagrams, code, editors, and timelines receive content-specific strategies such as reflow, controlled horizontal scrolling, alternative views, summaries, or full-screen focus modes.

### Testing Matrix

Responsive verification covers representative narrow, medium, wide, zoomed, landscape, touch, keyboard, reduced-motion, high-contrast, slow-network, and long-localization conditions. Device testing complements browser simulation.

---

## 11. Accessibility Standards

LearningOS treats accessibility as a permanent quality and civil responsibility.

### Conformance

First-party experiences target WCAG 2.2 Level AA or its governed successor as a minimum. Legal compliance is a floor; usability with assistive technology is the practical measure.

### Semantic Structure

Pages use meaningful headings, landmarks, lists, tables, forms, buttons, links, and document language. Native semantics are preferred before custom roles.

### Keyboard and Focus

Every interactive path is keyboard operable. Focus is visible, ordered, contained appropriately in overlays, restored after transitions, and moved only when necessary and predictable.

### Visual Access

Text, controls, focus, status, and essential graphics meet contrast requirements. Meaning never depends on color alone. Content remains usable under zoom, text spacing, reflow, and high-contrast settings.

### Motion and Media

Motion respects user preferences, avoids unnecessary vestibular triggers, and never becomes the sole carrier of meaning. Media provides captions, transcripts, descriptions, and controls appropriate to the content.

### Forms and Errors

Fields have programmatic labels, instructions, appropriate autocomplete, and accessible validation. Errors identify the problem, associate with fields, preserve input, and explain recovery.

### Dynamic Interfaces

Loading, completion, errors, notifications, and asynchronous updates are announced with appropriate timing and restraint. Live regions do not overwhelm assistive technology.

### Cognitive Accessibility

Language is direct, steps are limited and clear, choices are grouped, destructive actions are distinct, progress is understandable, and learners can pause or recover.

### Verification

Automated checks run continuously, but manual keyboard testing, screen-reader testing, zoom and contrast review, and evaluation with disabled users remain essential. Accessibility defects are prioritized by blocked learner outcomes and severity.

---

## 12. Performance Principles

Frontend performance protects learner attention, access, battery, data, and trust.

### Outcome-Based Performance

Performance is measured on real learner journeys, not only synthetic home-page scores. Critical actions include sign-in, dashboard readiness, lesson access, draft preservation, project workspace interaction, assessment submission, and mentor response.

### Rendering Strategy

Content should render as close to its authoritative source as practical. Static, server-rendered, streamed, cached, and client-rendered approaches are selected per route and interaction rather than applied universally.

### JavaScript Discipline

Client code is shipped only when interaction requires it. Heavy editors, visualizations, AI tools, and administrative modules load on demand. Third-party scripts require purpose, performance budgets, privacy review, and failure isolation.

### Data Discipline

Pages request the minimum fields needed, avoid request waterfalls, parallelize independent work, paginate collections, cache with explicit freshness, and prefetch only when evidence supports the cost.

### Asset Discipline

Images declare dimensions and use appropriate formats and responsive sources. Fonts are subset, stable, and loaded without hiding content. Icons and media avoid unnecessary payload.

### Stability and Responsiveness

Interfaces reserve space for asynchronous content, prioritize input responsiveness, divide long tasks, virtualize large collections where accessible, and keep main-thread work bounded.

### Budgets

Routes and feature classes define budgets for JavaScript, styles, images, fonts, requests, rendering time, interaction latency, and layout movement. Budgets are enforced in development and continuous delivery where practical.

### Measurement

Synthetic tests detect regressions; real-user monitoring reveals actual devices, networks, regions, and journeys. Measurements exclude or protect sensitive content and connect to release versions and feature exposure.

Performance degradation is a product defect when it prevents or discourages learning.

---

## 13. Folder Organization

The recommended project structure combines route composition, feature vertical slices, domain adapters, and governed shared layers.

```text
src/
├── app/                         # Routes, metadata, layouts, and route boundaries
│   ├── (public)/
│   ├── (learning)/
│   ├── (workspace)/
│   ├── (administration)/
│   ├── api/                     # Frontend-owned route handlers when required
│   ├── layout.tsx
│   └── providers.tsx
├── features/                    # Vertical product capabilities
│   ├── onboarding/
│   │   ├── components/
│   │   ├── server/
│   │   ├── state/
│   │   ├── schemas/
│   │   ├── tests/
│   │   └── index.ts
│   ├── learner-journey/
│   ├── project-workspace/
│   ├── assessment/
│   ├── portfolio/
│   └── ai-mentor/
├── domains/                     # Frontend models and adapters by bounded context
│   ├── identity/
│   ├── learning/
│   ├── projects/
│   └── assessment/
├── layouts/                     # Shared application and workspace layouts
├── components/                  # Product-wide composed components
├── design-system/
│   ├── primitives/
│   ├── components/
│   ├── patterns/
│   ├── tokens/
│   ├── styles/
│   └── documentation/
├── foundation/
│   ├── api/
│   ├── auth/
│   ├── config/
│   ├── errors/
│   ├── i18n/
│   ├── observability/
│   ├── security/
│   └── testing/
├── assets/
└── types/                       # Truly cross-cutting declarations only
```

### Organization Rules

- Route folders compose features but do not become business-logic containers
- Features expose a deliberate public entry point and keep internals private
- Domain adapters translate API contracts into frontend language
- Shared components cannot import features or routes
- Design-system code cannot import product domains
- Foundation code cannot import layouts, pages, or features
- Tests and stories live near the responsibility they verify
- Barrel exports remain explicit and must not conceal circular dependencies
- A generic `utils` folder is avoided; utilities live with a named responsibility
- Generated code is isolated and never edited manually

Names may adapt to the selected framework, but dependency direction and ownership remain canonical.

---

## 14. Product & Engineering Implications

The frontend architecture is a shared product and engineering contract.

### Product Implications

Product teams must:

- Begin with the learner's purpose and next meaningful action
- Reuse established patterns before inventing new interaction language
- Define complete loading, empty, error, permission, offline, and success states
- Include responsive and accessibility behavior in acceptance criteria
- Preserve drafts and recovery for valuable learner work
- Distinguish immediate outcomes from asynchronous updates
- Review performance and privacy alongside visible design
- Measure whether the experience reduces uncertainty and enables progress

### Engineering Implications

Engineering teams must:

- Enforce layer and feature boundaries with automated architecture checks
- Keep domain authorization and authoritative validation on the server
- Validate external data and translate transport models at boundaries
- Use semantic design-system primitives and tokens
- Test behavior at component, feature, contract, route, and journey levels
- Monitor accessibility, performance, errors, and learner outcomes by release
- Keep feature flags temporary and migrations explicit
- Maintain browser support, dependency health, and upgrade paths
- Document ownership, public contracts, and operational behavior

### Testing Strategy

Verification includes:

- Unit tests for pure behavior and state transitions
- Component tests for semantics, interaction, keyboard, and variants
- Contract tests for frontend and domain API boundaries
- Visual regression across states, themes, and representative breakpoints
- Accessibility automation and manual assistive-technology review
- Integration tests for feature workflows and failure recovery
- End-to-end tests for critical learner journeys
- Performance budgets and real-user regression monitoring

Tests prioritize observable behavior and learner outcomes over implementation details.

### Architecture Governance

A frontend architecture group or equivalent stewardship practice maintains design-system governance, dependency rules, reference patterns, accessibility standards, performance budgets, and modernization guidance. Feature teams retain ownership within those shared contracts.

Architecture exceptions identify reason, risk, owner, compensating behavior, expiration, and migration. Repeated exceptions trigger review of the canonical pattern.

### Relationship to Other Canonical Blueprints

Information Architecture defines content and navigation structure. The Application Shell defines persistent regions. Domain-Driven Architecture defines business responsibility. Identity, Journey, AI, Projects, Assessment, Portfolio, Community, Analytics, Security, Events, and Operations provide the capabilities and constraints the frontend expresses as one coherent experience.

> "Great frontends disappear so learning can appear."

---

## Canonical Declaration

The Frontend Architecture is Canonical Blueprint 034 and the authoritative Project Genesis reference for LearningOS frontend layers, design systems, components, layouts, pages, state, responsiveness, accessibility, performance, folder organization, and engineering governance.

LearningOS will build interfaces that make purpose clear, behavior consistent, access universal, work recoverable, and technology quiet enough for learning to take the foreground.

