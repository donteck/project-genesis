# Canonical Blueprint 013

## The Application Shell

| Record | Details |
|---|---|
| Blueprint number | 013 |
| Status | Canonical |
| Date established | August 2, 2026 |
| Authority | Project Genesis |
| Steward | Merchay Global Vision |
| Scope | The authenticated LearningOS application across learner, builder, educator, mentor, organization, and administrative experiences |
| Purpose | Define the permanent application shell that creates a consistent experience throughout LearningOS. |

---

## Purpose and Authority

The LearningOS application shell is the stable frame through which people enter domains, understand context, perform work, receive guidance, and interpret system state. Content and workflows may change, but the shell should preserve orientation and interaction expectations throughout the product.

This blueprint defines five permanent regions: Top Bar, Left Navigation, Main Workspace, Context Panel, and Status Bar. *Permanent* means that each region has an enduring responsibility in the application model. It does not require every region to remain visibly expanded on every screen size or in every focused activity.

Detailed styling, dimensions, component choices, and implementation may evolve. Changes should preserve the semantic responsibilities, accessibility, hierarchy, and behavioral consistency established here.

> "A great interface disappears so learning can appear."

---

## 1. Why the Application Shell Matters

LearningOS contains many forms of work: discovering courses, studying lessons, building projects, submitting evidence, reviewing growth, joining communities, authoring content, mentoring people, and administering organizations. Without a consistent shell, each experience can feel like a separate product.

The application shell matters because it:

- Gives every page a recognizable home
- Preserves global navigation while local work changes
- Separates primary work from supporting context
- Makes system status and feedback predictable
- Reduces relearning between domains and roles
- Supports deep links, resume behavior, and cross-domain journeys
- Creates stable accessibility landmarks and focus expectations
- Establishes reusable layout, interaction, and state patterns
- Allows new capabilities to fit without redesigning the entire frame
- Builds trust through consistent behavior

The shell should reduce interface uncertainty, not maximize visible controls. Stability comes from clear responsibility and predictable behavior rather than keeping every option on screen.

> "Consistency creates trust."

---

## 2. The Five Permanent Regions

The canonical desktop shell uses the following five-region structure:

```text
+--------------------------------------------------------------------------------+
| 1. TOP BAR                                                                     |
| Brand / Context | Search or Command | Notifications | Help | Profile           |
+------------------+-----------------------------------------+-------------------+
|                  |                                         |                   |
| 2. LEFT          | 3. MAIN WORKSPACE                       | 4. CONTEXT PANEL  |
| NAVIGATION       |                                         |                   |
|                  | Page title and orientation              | Guidance          |
| Home             | Primary content or activity             | Details           |
| Learn            | Primary actions                         | Feedback          |
| Build            |                                         | Related actions   |
| Prove            |                                         |                   |
| Grow             |                                         |                   |
| Community        |                                         |                   |
| Account          |                                         |                   |
|                  |                                         |                   |
+------------------+-----------------------------------------+-------------------+
| 5. STATUS BAR                                                                  |
| Save / Sync | Connectivity | Progress or activity state | System messages     |
+--------------------------------------------------------------------------------+
```

The five regions establish a clear division of responsibility:

| Region | Primary responsibility | Core question answered |
|---|---|---|
| Top Bar | Global identity, context, discovery, and utilities | Which environment and identity am I using? |
| Left Navigation | Stable movement among LearningOS domains | Where can I go? |
| Main Workspace | Current content, task, and primary action | What am I doing now? |
| Context Panel | Supporting information and contextual tools | What will help me here? |
| Status Bar | Persistent system and activity state | What is happening, saved, or requiring attention? |

The Main Workspace is visually and functionally primary. Every other region exists to orient, support, or communicate without competing with the work.

---

## 3. Top Bar

The Top Bar provides global identity, context, discovery, and utilities that remain relevant across domains.

### Core Responsibilities

- Display LearningOS identity and provide a reliable route to Home
- Show the active organization, academy, or workspace where relevant
- Provide global search or command access
- Surface notifications and time-sensitive attention responsibly
- Provide help, documentation, and support access
- Expose the signed-in identity and account menu
- Support role or organization switching without losing clarity
- Host global creation actions only when they are broadly relevant

### Behavioral Principles

The Top Bar should remain compact, predictable, and subordinate to the Main Workspace. It should not become a container for every feature that lacks a clear home.

Organization and role switching must communicate the resulting context change before or immediately after it occurs. The active context should be visible wherever it materially affects access, data, or actions.

Search should span permitted objects across domains and label results by type and canonical home. Notifications should link to stable contextual destinations and distinguish informational updates from required action.

On constrained screens, Top Bar utilities may move into menus or dedicated views, but identity, context, critical status, and access to navigation must remain understandable.

---

## 4. Left Navigation

The Left Navigation expresses the canonical LearningOS information architecture and provides stable movement among domains.

### Canonical Destinations

```text
Home
Learn
Build
Prove
Grow
Community
Account
```

### Core Responsibilities

- Present stable top-level destinations in a consistent order
- Clearly identify the active domain
- Support expanded domain navigation when it improves orientation
- Reflect permissions without exposing inaccessible actions
- Preserve labels and conceptual order across roles
- Allow collapse without removing accessible names or orientation
- Provide a predictable route back to Home

The Left Navigation should communicate *where capabilities belong*, not mirror every internal route. Local course, project, assessment, or community navigation belongs in the Main Workspace or an appropriate workspace-level pattern.

Role-specific capabilities should appear inside their owning domain. Creator tools belong within Learn or Build according to intent; assessment administration belongs within Prove; organization membership belongs within Account. New roles should not automatically create new top-level domains.

On mobile, the Left Navigation may become a drawer, sheet, or carefully selected bottom navigation. The canonical destinations, active state, accessible labels, and path to the complete domain list must remain consistent.

> "Navigation should create confidence, not complexity."

---

## 5. Main Workspace

The Main Workspace is the primary region for content, learning, creation, assessment, reflection, and administration. It should receive the largest share of attention, space, and performance priority.

### Required Structure

When applicable, the Main Workspace should include:

1. Orientation: domain, breadcrumb, workspace, or journey position
2. Page identity: clear title and concise purpose
3. State: status, progress, ownership, or relevant metadata
4. Primary content or activity
5. Primary action and appropriate secondary actions
6. Completion, continuation, or next-step guidance

The workspace may take different forms:

- Reading and lesson view
- Practice or assessment view
- Project canvas or editor
- Dashboard or analytical view
- Portfolio and evidence view
- Discussion or event view
- Configuration and administration view
- Focus mode for immersive work

The shell should allow these forms without changing fundamental orientation. Page-specific controls should remain close to the content they affect. Destructive, irreversible, or high-impact actions require clear consequences and appropriate confirmation.

Loading, empty, error, offline, restricted, completed, and archived states should retain the page's identity and provide a meaningful next action.

> "Every screen should answer: What should I do next?"

---

## 6. Context Panel

The Context Panel contains information and tools that support the current Main Workspace without becoming the primary work itself.

### Appropriate Content

- Learning objectives, instructions, and reference information
- AI tutor, copilot, or contextual assistance
- Feedback, rubric, comments, and review guidance
- Object details, metadata, collaborators, and activity
- Outline, table of contents, milestones, or local progress
- Related resources, evidence, and next steps
- Properties and settings specific to the selected object

### Behavioral Principles

The Context Panel should be contextual, optional when appropriate, and easy to open or dismiss. Its contents should change with the selected object or activity without causing the Main Workspace to lose state.

The panel should not contain an essential action that cannot be discovered elsewhere, and it should not become a second unrelated workspace. If an activity requires sustained attention, complex navigation, or substantial creation, it likely belongs in the Main Workspace.

AI assistance in the Context Panel should communicate scope, uncertainty, data use, and generated status. It should support thinking and action without obscuring the original content, taking control without consent, or manufacturing false evidence of capability.

On smaller screens, the panel may become a sheet, drawer, tab, or full-screen supporting view. Opening and closing it should preserve focus, scroll, selection, and unsaved work.

---

## 7. Status Bar

The Status Bar communicates persistent system and activity state that people may need while working.

### Appropriate Status Information

- Saved, saving, unsaved, synced, or conflict state
- Online, offline, degraded, or reconnecting state
- Upload, generation, submission, or background-task progress
- Current lesson, project, assessment, or workflow progress
- Validation results requiring attention
- Time limits when relevant and ethically appropriate
- Environment or mode indicators when confusion would create risk
- Concise system messages with accessible detail

### Behavioral Principles

The Status Bar should be quiet during normal operation and prominent when action or risk requires attention. It should not become an advertising surface, engagement ticker, or permanent stream of low-value messages.

Status must not rely on color alone. Changes should use understandable text, icons with labels, and announcements appropriate to urgency. Repeated updates should avoid overwhelming assistive technology.

Important status should also appear near the affected object or action. The Status Bar reinforces state across the workspace; it does not replace contextual error handling.

On mobile, status may appear as a compact persistent region, contextual banner, toast with durable history, or inline indicator. Critical states such as unsaved work, failed submission, or lost connectivity must remain visible until resolved or acknowledged.

---

## 8. Responsive Philosophy

Responsive design should preserve responsibilities, priority, and continuity rather than mechanically shrink a desktop layout.

### Wide Screens

All five regions may be visible. Left Navigation and Context Panel may be independently collapsible. The Main Workspace should retain a readable maximum width where content benefits from it and expand where creation or data work requires space.

### Medium Screens

The Left Navigation may collapse to an icon-and-label rail or drawer. The Context Panel may overlay, collapse, or open on demand. The Main Workspace remains primary.

### Small Screens

The interface should present one primary working surface at a time. Global navigation, context, and status move into accessible mobile patterns without changing labels or losing state.

### Focus Modes

Lessons, editors, assessments, presentations, or accessibility needs may justify temporarily reducing visible shell regions. A focus mode must preserve access to orientation, exit, essential status, help, and safety controls.

### Responsive Rules

- Prioritize task completion over visual parity
- Preserve information hierarchy and reading order
- Avoid horizontal scrolling except for inherently two-dimensional content
- Maintain touch target size, spacing, and reachable controls
- Keep primary actions visible without covering content
- Preserve scroll, selection, drafts, and panel state across layout changes
- Do not make mobile users perform more conceptual navigation decisions
- Test zoom, text resizing, orientation change, virtual keyboards, and safe areas

Responsive behavior should be defined by available space and content needs, not by assumptions about device type or user ability.

---

## 9. Accessibility Principles

The application shell should provide a stable, perceivable, operable, understandable, and robust frame for every LearningOS experience.

### Semantic Landmarks

Use appropriate landmarks for banner, navigation, main content, complementary context, and content information or status. Landmarks should have clear accessible names when more than one of a type exists.

### Keyboard Operation

Every shell control must be reachable and operable by keyboard. Focus order should follow visual and semantic order. Collapsed regions, menus, panels, and dialogs should manage focus predictably.

### Skip and Direct Access

Provide skip links or equivalent mechanisms to move directly to Main Workspace, primary navigation, and relevant contextual regions without traversing repeated controls.

### Visible Focus and Active State

Keyboard focus, selected navigation, current page, expanded regions, and active modes must be visually distinct and programmatically available.

### Page and Region Identity

Document titles, page headings, breadcrumbs, landmarks, and active navigation should agree. Route changes and significant context changes should be announced appropriately.

### Adaptable Presentation

The shell should support zoom, text resizing, high contrast, reduced motion, color preferences, screen readers, voice control, magnification, and different input methods without loss of information or function.

### Understandable Status

Saving, loading, errors, connectivity, background work, and completion should be communicated without color-only meaning. Announcements should be timely but not disruptive.

### Consistent Help and Error Recovery

Help should remain in a consistent location. Errors should identify what happened, what is affected, how to recover, and whether work was preserved.

Accessibility is part of the shell contract. Individual pages should inherit a strong accessible foundation rather than recreate basic navigation and landmark behavior independently.

---

## 10. Product & Engineering Implications

### Establish a Shared Shell Contract

Product, design, engineering, content, and accessibility teams should share definitions for the five regions, their responsibilities, allowed content, responsive behavior, and ownership.

### Use Route and Page Metadata

Routes should declare domain, page title, breadcrumbs, workspace context, allowed shell modes, primary action, Context Panel availability, and relevant status behavior where practical.

### Build Composable Region Interfaces

The shell should expose stable slots or interfaces for page identity, navigation state, primary content, contextual tools, and status without allowing pages to replace global behavior arbitrarily.

### Preserve State across Navigation

Drafts, scroll position, selected objects, collapsed regions, Context Panel state, and organization context should survive expected navigation and responsive changes where safe and useful.

### Separate Global, Domain, and Object State

The Top Bar and Left Navigation should not depend on page-specific implementation. Main Workspace and Context Panel state should remain scoped to the current domain and object. Status should identify its source and lifecycle.

### Enforce Authorization beyond Visibility

The shell may hide unavailable destinations and actions, but services and routes must enforce permissions independently. Context switching should invalidate or refresh access-sensitive state.

### Protect Performance

The shell should render quickly, avoid unnecessary layout shifts, lazy-load nonessential contextual tools, and keep the Main Workspace interactive during background activity whenever possible.

### Instrument without Surveillance

Teams may measure navigation success, panel use, recovery, task continuation, errors, and responsive behavior while minimizing data and protecting privacy. Metrics should improve clarity, not manipulate attention.

### Test the Shell as Infrastructure

Automated and manual verification should cover landmarks, keyboard operation, focus, active navigation, deep links, permissions, responsive transitions, saving state, connectivity, errors, and critical journeys across roles.

### Govern Exceptions

Pages that hide, reorder, or fundamentally change shell regions should document why the exception is necessary, how orientation and accessibility are preserved, and when normal shell behavior returns.

### Evolve Consistently

Shell changes affect every domain. They require cross-product review, migration planning, design-system updates, analytics continuity, accessibility validation, and communication proportional to impact.

---

## Canonical Status

The Application Shell is Canonical Blueprint 013 and the authoritative Project Genesis reference for the permanent frame that creates a consistent LearningOS experience.

Future pages, workflows, responsive layouts, navigation components, contextual tools, and system-status patterns should be evaluated by whether they preserve the five permanent regions, keep the Main Workspace primary, answer what the person should do next, and create confidence through consistency.
