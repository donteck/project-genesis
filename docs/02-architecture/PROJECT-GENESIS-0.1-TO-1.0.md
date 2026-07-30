# Project Genesis — Architecture Record

**Product:** Uwebbz LearningOS  
**Category:** AI Education Operating System  
**Founder:** Emmanuel Tuffet  
**Parent Organization:** Merchay Global Vision  
**Strategic Frameworks:** Uwebbz Technology Master Blueprint (UTMB) and Producer Development Method (PDM)  
**Internal Codename:** Project Genesis  
**Platform Tagline:** Learn. Build. Master.  
**Core Promise:** Create once. Teach forever.

## Mission

Transform knowledge into opportunities through AI-powered education.

## Founding Vision

Uwebbz LearningOS will transform one idea into an interconnected collection of educational and digital assets:

```text
Idea
→ Roadmap
→ Course
→ Google Drive
→ Student
→ Certificate
→ Book
→ Video
→ Blog
→ GitHub Project
```

The platform is not intended to be a traditional learning management system. It is an operating system for education businesses, academies, instructors, creators, universities, churches, companies, consultants, and organizations that teach.

> Do not build a course. Build a course factory.

---

# Genesis 0.1 — Vision and Mission

## Objective

Define the purpose, mission, identity, promise, and long-term direction of Uwebbz LearningOS.

## Core Decisions

- Product name: **Uwebbz LearningOS**
- Category: **AI Education Operating System**
- Internal codename: **Project Genesis**
- Founder: **Emmanuel Tuffet**
- Parent organization: **Merchay Global Vision**
- Core promise: **Create once. Teach forever.**
- Mission: Transform knowledge into opportunities through AI-powered education.

## Founding Principles

1. AI first
2. Human approval before publishing
3. Everything reusable
4. Modular architecture
5. World-class user experience
6. Security by design
7. Original knowledge and intellectual property
8. Build for scale
9. Document major decisions
10. Nothing important lives only in conversation

## Founding Quote

> Knowledge is powerful. Shared knowledge is transformational. Organized knowledge can change the world.

**Status:** Complete

---

# Genesis 0.2 — System Architecture

## Objective

Define the high-level technical architecture and the major product modules.

## Core Architecture

```text
Users
  ↓
Next.js Application
  ↓
API and Service Layer
  ↓
Supabase
  ↓
PostgreSQL Database
  ↓
External Services
  ├── OpenAI
  ├── Google Drive
  ├── GitHub
  ├── WordPress
  └── Payment Providers
```

## Official Technology Stack

### Frontend

- Next.js
- TypeScript
- React
- Tailwind CSS
- React Flow

### Backend

- Supabase
- PostgreSQL
- Supabase Edge Functions

### Authentication

- Supabase Auth

### Artificial Intelligence

- OpenAI initially
- Provider-independent architecture for future models

### Content Storage

- Google Drive API

### Version Control

- GitHub

### Deployment

- Vercel

### Future Integrations

- WordPress REST API
- Elementor
- WooCommerce
- Additional storage providers
- Enterprise identity providers

## Major Product Modules

- Roadmap Builder
- AI Course Builder
- Google Drive Content System
- Publishing Engine
- Student Portal
- Instructor Portal
- Content Transformation Engine
- AI Studio
- Analytics
- Certificates
- Administration

## Architectural Principle

> Vision inspires. Architecture delivers.

**Status:** Complete

---

# Genesis 0.3 — Database Architecture

## Objective

Design a scalable relational data model for identity, organizations, learning, AI, content, commerce, analytics, community, and administration.

## Business Domains

- Identity
- Organization
- Learning
- Assessment
- AI
- Content
- Commerce
- Analytics
- Community
- Administration

## Important Tables

### Identity and Organizations

- profiles
- roles
- permissions
- organizations
- organization_memberships
- academies
- academy_memberships

### Roadmaps and Learning

- roadmaps
- roadmap_versions
- roadmap_stages
- roadmap_nodes
- roadmap_edges
- courses
- course_versions
- modules
- lessons

### Assessment and Progress

- enrollments
- lesson_progress
- quizzes
- quiz_attempts
- assignments
- assignment_submissions
- grades
- certificates

### AI

- ai_providers
- ai_models
- ai_agents
- ai_prompts
- ai_prompt_versions
- ai_generation_jobs
- ai_generations
- ai_usage_records

### Google Drive and Content

- drive_connections
- drive_folders
- drive_files
- drive_permissions
- content_assets
- asset_versions
- publishing_targets

## Database Standard

Every tenant-owned record should include appropriate ownership fields such as:

```text
organization_id
academy_id
created_by
updated_by
```

## North-Star Database Question

> Will this still make sense when we have one million students?

**Status:** Complete

---

# Genesis 0.4 — Enterprise API Architecture

## Objective

Create a versioned API layer that separates user interfaces, business rules, database operations, AI services, content providers, and external integrations.

## API Structure

```text
/api/v1
```

## API Domains

- Authentication
- Users
- Organizations
- Academies
- Roadmaps
- Courses
- Lessons
- Assessments
- Progress
- Certificates
- AI
- Storage
- Publishing
- GitHub
- Commerce
- Analytics
- Administration

## Example Endpoints

```text
POST   /api/v1/roadmaps/generate
GET    /api/v1/roadmaps/{id}
PATCH  /api/v1/roadmaps/{id}
POST   /api/v1/courses/from-roadmap
GET    /api/v1/courses/{id}
POST   /api/v1/drive/connect
POST   /api/v1/drive/folders
POST   /api/v1/enrollments
PATCH  /api/v1/progress/{id}
POST   /api/v1/certificates/{id}/revoke
```

## Human Approval Workflow

```text
User Request
  ↓
AI Draft
  ↓
Draft Saved
  ↓
Human Review
  ↓
Approval
  ↓
Publication
```

## Standard Status Values

```text
queued
generating
draft
under_review
approved
published
failed
archived
```

## Initial Roles

- platform_owner
- platform_admin
- organization_owner
- academy_admin
- instructor
- content_editor
- reviewer
- student
- support_agent

## Permission Examples

- course:create
- course:edit
- course:approve
- course:publish
- roadmap:generate
- student:invite
- drive:connect
- certificate:issue
- analytics:view

**Decision #004:** Use a versioned, domain-based enterprise API with server-side authorization and multi-tenant enforcement.

**Status:** Complete

---

# Genesis 0.5 — UI/UX Design System

## Objective

Design a professional, calm, trustworthy, student-first interface that makes complex technology feel clear.

## Design Principle

> Complex technology. Clear experience.

## Role-Based Experiences

- Founder Dashboard
- Organization Owner Dashboard
- Academy Administrator Dashboard
- Instructor Dashboard
- Content Editor Dashboard
- Student Dashboard
- Support Dashboard

## Founder Dashboard

- Total students
- Total courses
- Total academies
- Monthly recurring revenue
- AI usage
- Platform health
- Recent activity
- Risk alerts

## Instructor Dashboard

- Assigned courses
- Draft content
- Content awaiting review
- Grading tasks
- Publishing status
- Student progress

## Student Dashboard

- Continue learning
- My courses
- Current roadmap
- Assignments
- Progress
- Certificates

## Roadmap Builder

- Draggable nodes
- Visual prerequisite connections
- Stage organization
- Node editing
- Version history
- Approval controls

## Course Builder

Three-panel layout:

```text
Course Map | Content Editor | AI Assistant
```

## Content Factory

A single approved course can become:

- Book
- Workbook
- Blog
- Video script
- Presentation
- Social posts
- GitHub project
- Marketing page

## AI Studio Functions

- Generate roadmap
- Generate course
- Generate lesson
- Generate quiz
- Generate assignment
- Generate project
- Generate book
- Generate workbook
- Generate video script
- Generate blog
- Translate
- Improve

## Design System Requirements

- Reusable design tokens
- Accessible contrast
- Keyboard navigation
- Screen-reader support
- Responsive layouts
- White-label logos and colors
- Command palette using Ctrl+K

**Decision #005:** Build role-aware, modular interfaces using a shared design system and reusable product patterns.

**Status:** Complete

---

# Genesis 0.6 — AI Engine Architecture

## Objective

Design a modular AI system that generates structured, reusable, reviewable educational assets.

## AI Principle

> AI creates the first draft. Architecture protects the quality. Humans approve the final result.

## AI Layers

```text
User Interface
  ↓
AI Orchestrator
  ↓
Specialized AI Agents
  ↓
Prompt and Template Library
  ↓
Knowledge and Context Layer
  ↓
Model Providers
  ↓
Validation and Quality Layer
  ↓
Human Review
```

## Specialized AI Agents

- Research Agent
- Roadmap Architect
- Curriculum Designer
- Lesson Writer
- Assessment Designer
- Project Architect
- Rubric Designer
- Content Reviewer
- Accessibility Reviewer
- Book Transformer
- Video Script Writer
- Blog Writer
- GitHub Project Builder
- SEO Agent
- Translation Agent

## MVP AI Agents

- Roadmap Architect
- Curriculum Designer
- Lesson Writer
- Assessment Designer
- Project Architect
- Content Reviewer

## Structured Generation

AI output must follow validated schemas rather than unstructured paragraphs. Structured generation allows the platform to render roadmaps, create database records, edit sections, validate completeness, and preserve version history.

## Course Generation Pipeline

```text
Course Idea
  ↓
Course Brief
  ↓
Audience Definition
  ↓
Learning Outcomes
  ↓
Roadmap
  ↓
Course Outline
  ↓
Modules
  ↓
Lessons
  ↓
Assessments
  ↓
Projects
  ↓
Quality Review
  ↓
Human Approval
```

## AI Governance

- Progressive generation
- Prompt versioning
- Model routing
- Cost tracking
- Source attribution
- Hallucination controls
- Quality scoring
- Complete content lineage
- Failure recovery
- Tenant-isolated context retrieval

## First AI Workflows

1. AI Roadmap Generator
2. Roadmap-to-Course Generator

**Decision #006:** Use a modular, multi-agent AI orchestration system with structured generation, human approval, versioned prompts, quality controls, and provider independence.

**Status:** Complete

---

# Genesis 0.7 — Google Drive Content Architecture

## Objective

Use Google Drive as the primary instructor content repository while Supabase manages metadata, permissions, relationships, learning state, and analytics.

## Storage Principle

> The LMS never owns the files. It owns the intelligence about the files.

## Architecture

```text
Instructor
  ↓
Uwebbz LearningOS
  ├── Supabase: metadata, permissions, analytics, versions
  └── Google Drive: PDFs, videos, images, documents, archives
```

## Standard Course Folder Structure

```text
Course Name
├── 00 Course Overview
├── 01 Module One
├── 02 Module Two
├── Assignments
├── Quizzes
├── Projects
├── Certificates
├── Downloads
└── Instructor Only
```

## Required Capabilities

- Automatic folder creation
- Secure OAuth connection
- Folder and file ID storage
- File metadata synchronization
- Lesson-resource attachments
- Visibility controls
- Missing-file detection
- Version history
- Controlled previews
- Student access through LearningOS, not unrestricted Drive browsing

## File Visibility States

- Draft
- Instructor
- Reviewer
- Student
- Public
- Archived

## Content Lineage

Every approved file can generate derived assets such as quizzes, workbooks, video scripts, presentations, blogs, and books. If the source changes, derived assets should be flagged for review.

## Future Storage Providers

- OneDrive
- Dropbox
- Amazon S3
- Azure Blob Storage
- Cloudflare R2
- Enterprise storage

**Decision #007:** Google Drive is the first storage provider, but the content service layer must remain provider-independent.

**Status:** Complete

---

# Genesis 0.8 — Education Workflow and Automation Engine

## Objective

Connect students, instructors, AI, Google Drive, GitHub, WordPress, payments, analytics, and administration through event-driven workflows.

## Automation Principle

> If a task is repeated, automate it.

## Event-Driven Architecture

Every major action should produce an event, such as:

```text
course.created
course.approved
course.published
lesson.completed
quiz.passed
quiz.failed
assignment.submitted
student.enrolled
certificate.issued
payment.completed
drive.file.uploaded
repository.created
blog.published
```

## Example Student Workflow

```text
Student Enrolls
  ↓
Create Enrollment
  ↓
Unlock Course
  ↓
Send Welcome Message
  ↓
Create Dashboard State
  ↓
Notify Instructor
  ↓
Start Progress Tracking
```

## Example Content Workflow

```text
File Uploaded
  ↓
Create Summary
  ↓
Generate Quiz
  ↓
Generate Flashcards
  ↓
Generate Workbook
  ↓
Generate Video Script
  ↓
Notify Reviewer
```

## Future Workflow Builder

The long-term platform should support a no-code builder containing:

- Trigger
- Condition
- Action
- Delay
- Loop
- AI action
- Human approval
- Publication

## Automation Categories

- Student
- Instructor
- AI
- Content
- Publishing
- Analytics
- Commerce
- Security
- Administration
- Integrations

**Decision #008:** Use an event-driven automation engine with reusable templates, scheduled jobs, approval gates, monitoring, and future no-code workflow design.

**Status:** Complete

---

# Genesis 0.9 — Enterprise Security, Identity and Multi-Tenancy

## Objective

Protect student identities, academic records, course intellectual property, Google Drive connections, AI context, organization data, certificates, and administrative controls.

## Security Principle

> Trust is earned through architecture, not promises.

## Identity Flow

```text
User
  ↓
Authentication
  ↓
Identity Confirmed
  ↓
Permission Check
  ↓
Tenant Boundary Check
  ↓
Resource Access Decision
```

## Authentication Requirements

- Email and password
- Email verification
- Password reset
- Magic-link support
- Google sign-in
- Multi-factor authentication for privileged users
- Future enterprise SSO

## Multi-Tenant Model

```text
Uwebbz LearningOS
├── Organization A
│   ├── Academy A1
│   └── Academy A2
├── Organization B
│   └── Academy B1
└── Uwebbz Internal Academies
```

## Security Controls

- Supabase Row-Level Security
- Server-side permission enforcement
- Organization and academy isolation
- Role-based access control
- Permission scopes
- Secure secret management
- Encrypted OAuth credentials
- Audit logging
- Rate limiting
- Login monitoring
- Webhook verification
- Secure file validation
- AI context isolation
- Backup and recovery
- Incident response

## Initial Roles

- platform_owner
- platform_admin
- security_admin
- support_admin
- organization_owner
- organization_admin
- academy_admin
- billing_admin
- instructor
- teaching_assistant
- content_editor
- content_reviewer
- student
- guardian
- auditor

## Critical Acceptance Tests

- Student A cannot access Student B's records.
- Academy A cannot access Academy B's courses.
- An unauthorized instructor cannot publish.
- A removed user cannot reuse an old session.
- Changing organization_id in a browser request does not grant access.
- Private Drive files are never exposed without authorization.
- AI cannot retrieve unauthorized academy content.
- Invitation tokens cannot be reused.
- Revoked certificates no longer verify as valid.
- Administrative changes are audited.

**Decision #009:** Enforce identity-aware, permission-based, multi-tenant security at both application and database layers.

**Status:** Complete

---

# Genesis 1.0 — MVP Product Blueprint

## Objective

Convert the architecture into the smallest complete product that proves the largest vision.

## Official MVP Journey

```text
Idea
  ↓
AI Roadmap
  ↓
Visual Editing
  ↓
Course Generation
  ↓
Google Drive
  ↓
Student Learning
  ↓
Progress Tracking
```

## MVP Promise

> Turn an idea into an organized, AI-assisted learning experience.

## Initial Users

- Founder
- Instructor
- Student

## Core MVP Modules

1. Authentication
2. Founder Dashboard
3. Academy Management
4. AI Roadmap Generator
5. Visual Roadmap Editor
6. Roadmap-to-Course Generator
7. Google Drive Integration
8. Student Learning Portal
9. Progress Tracking

## MVP Definition of Done

Genesis 1.0 is complete only when:

- A founder can create an academy.
- An instructor can generate a roadmap.
- The roadmap can be visually edited.
- The roadmap can become a course.
- The course can be edited and approved.
- Google Drive folders can be generated.
- A student can be enrolled.
- The student can access lessons.
- The student can complete lessons.
- Progress can be viewed by the student and instructor.
- Tenant boundaries are secure.
- Critical actions are audited.
- The full workflow works without manual database editing.

## Initial Repository Structure

```text
uwebbz-learning-os/
├── apps/
│   └── web/
├── packages/
│   ├── ui/
│   ├── database/
│   ├── auth/
│   ├── ai/
│   ├── drive/
│   ├── validation/
│   └── shared/
├── supabase/
│   ├── migrations/
│   ├── functions/
│   ├── seed/
│   └── tests/
├── docs/
├── tests/
└── .github/workflows/
```

## Build Phases

1. Foundation
2. Organizations and Academies
3. Roadmap System
4. Course System
5. Google Drive Integration
6. Student Portal
7. Stabilization

## Official Build Order

1. Create the product repository.
2. Initialize Next.js.
3. Configure TypeScript and Tailwind.
4. Create the Supabase project.
5. Add environment validation.
6. Create database migrations.
7. Implement authentication.
8. Build the protected dashboard.
9. Implement organizations and academies.
10. Implement roles and permissions.
11. Build the roadmap creation form.
12. Build the AI roadmap endpoint.
13. Save generated roadmap data.
14. Build the roadmap viewer and visual editor.
15. Build roadmap-to-course conversion.
16. Build the course editor.
17. Connect Google Drive.
18. Build the student portal.
19. Implement progress tracking.
20. Test tenant isolation.
21. Begin the internal alpha.

## Pilot Course

**Mastering the AI-Powered Modern Development Pipeline**  
**Subtitle:** From Lovable and ChatGPT to VS Code, Git, GitHub, Vercel, WordPress, Elementor Pro, and Production Websites  
**Author:** Emmanuel Tuffet

## MVP Exclusions

The following are intentionally deferred:

- Native mobile applications
- Complex marketplace
- Live classroom streaming
- Advanced discussion forums
- Full payment marketplace
- Affiliate system
- Multi-provider storage
- AI tutor
- Fully automated grading
- Complete no-code automation builder
- Enterprise SSO
- Public developer API
- WordPress publishing automation
- GitHub project generation
- Full book and video factories

## Pilot Release Strategy

1. Internal alpha: Founder, one instructor, one student
2. Private pilot: 5–20 learners, 1–3 instructors, one academy, one course
3. Closed beta: Multiple courses, multiple instructors, up to 100 invited learners
4. Genesis 1.0 launch: Selected creators and academies

## MVP Principle

> Build the smallest complete system that proves the largest vision.

**Decision #010:** Genesis 1.0 will prove the complete Idea → Roadmap → Course → Drive → Student → Progress journey.

**Status:** Complete

---

# Genesis Progress

| Milestone | Status |
|---|---|
| Genesis 0.1 — Vision and Mission | Complete |
| Genesis 0.2 — System Architecture | Complete |
| Genesis 0.3 — Database Architecture | Complete |
| Genesis 0.4 — Enterprise API Architecture | Complete |
| Genesis 0.5 — UI/UX Design System | Complete |
| Genesis 0.6 — AI Engine Architecture | Complete |
| Genesis 0.7 — Google Drive Content Architecture | Complete |
| Genesis 0.8 — Workflow and Automation Engine | Complete |
| Genesis 0.9 — Security and Multi-Tenancy | Complete |
| Genesis 1.0 — MVP Product Blueprint | Complete |
| Genesis 1.1 — Repository Foundation and Engineering Setup | Next |

---

# Founder Commitment

Project Genesis will be developed as a long-term, scalable education ecosystem rather than a collection of disconnected features.

The platform will prioritize:

- Systems over one-off projects
- Reusable assets over isolated content
- Strong architecture over shortcuts
- Human-centered education over uncontrolled automation
- Security and trust over speed alone
- Documentation over undocumented decisions
- Sustainable execution over temporary excitement

> A dream written down becomes a vision. A vision planned becomes a blueprint. A blueprint executed becomes a platform. A platform that serves people becomes a legacy.
