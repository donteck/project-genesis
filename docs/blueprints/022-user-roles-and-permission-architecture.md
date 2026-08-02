# Canonical Blueprint 022

## User Roles & Permission Architecture

| Record | Details |
|---|---|
| Blueprint number | 022 |
| Status | Canonical |
| Date established | August 2, 2026 |
| Authority | Project Genesis |
| Steward | Merchay Global Vision |
| Scope | LearningOS visitors, learners, contributors, mentors, instructors, organizations, administrators, platform stewards, permissions, delegation, trust, and governance |
| Purpose | Define the complete role hierarchy, permission model, trust model, and governance architecture for LearningOS. |

---

## Purpose and Authority

LearningOS enables people and institutions to learn, build, assess, mentor, publish, govern, and steward knowledge. Each responsibility requires appropriate authority. Too little permission prevents meaningful contribution; too much permission exposes people, evidence, organizations, and the platform to avoidable risk.

This architecture defines roles as scoped responsibilities granted for a purpose, within a context, for an appropriate period. Roles are not measures of personal worth and do not automatically form a universal rank. A person may be a learner in one domain, contributor in another, mentor in a specific community, and administrator only within one organization.

This blueprint establishes the identity pyramid, role responsibilities, permission categories, Trust Ladder, product requirements, engineering model, and governance through which LearningOS distributes authority safely.

> "Responsibility should grow with demonstrated trust."

---

## 1. Why Roles Matter

Roles translate human responsibility into understandable product behavior and enforceable system policy. They help a person know what they may do, why they may do it, where that authority applies, and what accountability accompanies it.

Roles matter because they:

- Protect private and sensitive information
- Separate organizational tenants and communities
- Give learners safe access to appropriate experiences
- Enable contributors to create and share useful work
- Establish boundaries for mentorship and instruction
- Protect assessment and credential integrity
- Delegate organizational work without granting platform-wide power
- Make approvals, review, moderation, and escalation accountable
- Support temporary, progressive, and revocable responsibility
- Create paths from participation to stewardship

A role name alone is not enough to authorize an action. The system must also consider the active organization, relationship to the resource, ownership, object state, trust level, authentication assurance, policy, and any explicit restrictions.

Good role architecture enables service without creating unnecessary hierarchy. It makes contribution easier, privilege visible, and high-impact authority difficult to misuse.

---

## 2. The Identity Pyramid

The canonical responsibility progression is:

```text
Visitor
  ↓
Learner
  ↓
Contributor
  ↓
Mentor
  ↓
Instructor
  ↓
Organization
  ↓
Administrator
  ↓
Platform Steward
```

The progression expresses increasing scope and institutional responsibility:

```text
                       /\
                      /  \
                     / PLATFORM STEWARD \
                    /--------------------\
                   /    ADMINISTRATOR     \
                  /------------------------\
                 /      ORGANIZATION        \
                /----------------------------\
               /       INSTRUCTOR             \
              /--------------------------------\
             /          MENTOR                  \
            /------------------------------------\
           /         CONTRIBUTOR                  \
          /----------------------------------------\
         /            LEARNER                       \
        /--------------------------------------------\
       /              VISITOR                         \
      /________________________________________________\
```

The pyramid is a governance model, not a mandatory career path. Contributor, Mentor, and Instructor can be distinct responsibilities rather than automatic promotions. Organization represents institutional authority exercised by designated people or services; it is not a human identity. Administrator and Platform Steward roles should remain narrow, reviewed, and separated from ordinary participation.

Every higher responsibility retains the obligation to respect the boundaries of lower roles. Increased authority should create greater accountability, not greater personal importance.

---

## 3. Visitor

A Visitor is a person who interacts with public or explicitly shared LearningOS experiences without an authenticated learner account or current session.

### Visitor Purpose

- Discover LearningOS and its mission
- Explore public learning opportunities
- Review public projects, portfolios, credentials, events, and community knowledge
- Understand privacy, terms, conduct, accessibility, and support
- Begin registration, sign-in, invitation acceptance, or account recovery

### Typical Permissions

A Visitor may:

- Read publicly published content
- Search publicly indexed resources
- Verify a credential through an approved public view
- View public portfolio or project snapshots
- Register interest or begin account creation
- Access public help and security information

### Boundaries

A Visitor may not access private learning records, organization workspaces, restricted community spaces, unpublished projects, assessment content, personal profiles beyond chosen visibility, or privileged operations.

Public access should not require unnecessary tracking or account creation. Public forms need abuse protection, data minimization, clear consent, and rate limiting.

---

## 4. Learner

A Learner is an authenticated person who uses LearningOS to pursue goals, develop capability, build evidence, and participate within granted communities and organizations.

### Learner Purpose

- Learn, practice, build, reflect, and demonstrate capability
- Manage personal journeys, projects, evidence, portfolio, and profile
- Participate in authorized cohorts, groups, events, and discussions
- Receive feedback, mentoring, and AI support
- Control appropriate privacy, consent, sharing, and account settings

### Typical Permissions

A Learner may:

- Enroll in or access assigned learning
- Complete lessons and practice
- Create personal projects and drafts
- Submit work for assessment
- View authorized results and feedback
- Manage learner-authored reflections
- Curate portfolio and Learning Passport views
- Participate in permitted community spaces
- Request help, feedback, or mentorship
- Export eligible learner-owned records

### Boundaries

A Learner may not alter assessment criteria or results, access another learner's private records, assign organization roles, publish restricted content, issue credentials, moderate beyond granted scope, or act as an authority without explicit role assignment.

Learner is the foundational authenticated role. Every other human role should retain the ability to participate as a learner where appropriate.

---

## 5. Contributor

A Contributor is a learner or member granted responsibility to add value to shared knowledge, content, projects, or communities.

### Contributor Purpose

- Create and improve reusable knowledge
- Participate meaningfully in shared projects
- Answer questions and provide structured feedback
- Submit resources, templates, translations, corrections, or examples
- Help maintain the quality and usefulness of community assets

### Typical Permissions

A Contributor may, within granted scope:

- Create draft shared resources
- Propose edits or corrections
- Contribute to team projects
- Review peer work using defined criteria
- Answer and curate questions
- Submit content for approval or publication
- Receive attribution and contribution evidence
- Access contributor tools and guidelines

### Boundaries

Contribution does not automatically grant publication, moderation, assessment, credential, user-management, or administrative authority. Shared work requires clear ownership, licensing, provenance, collaboration, and review.

Contributor readiness may be based on orientation, conduct, relevant capability, verified work, or invitation. Contributions should remain attributable and reversible through governed workflows.

> "Permissions enable meaningful contribution."

---

## 6. Mentor

A Mentor is a trusted person authorized to support the development of one or more learners within a defined domain, relationship, organization, and period.

### Mentor Purpose

- Help learners clarify goals and next steps
- Ask questions that develop judgment
- Review work and provide formative feedback
- Support reflection, confidence, and independence
- Connect learners with resources, people, and opportunities
- Model responsible building and contribution

### Typical Permissions

A Mentor may, within an active mentorship relationship:

- View learner-shared journey and project context
- Review selected artifacts and evidence
- Provide feedback and action items
- Manage agreed mentorship sessions and availability
- Record mentor-authored or mutually approved notes
- Recommend resources, projects, or next steps
- Escalate support or safety concerns through governed paths
- Receive evidence of mentorship contribution

### Boundaries

A Mentor does not automatically receive access to private reflections, assessment items, accommodations, security information, unrelated learning history, or organization administration. Mentors cannot issue formal credentials or override accountable assessment unless separately authorized.

Mentorship requires role readiness, conduct agreement, boundaries, safeguarding appropriate to context, workload limits, feedback, periodic review, and a clear way to end or reassign the relationship.

---

## 7. Instructor

An Instructor is a person authorized to design, deliver, facilitate, evaluate, or govern learning experiences within a defined organization, academy, program, course, or capability domain.

### Instructor Purpose

- Create and maintain learning experiences
- Guide cohorts and facilitate active learning
- Define appropriate projects and assessments
- Provide accountable feedback and evaluation
- Monitor learning outcomes and improve instruction
- Develop contributors, mentors, and future instructors

### Typical Permissions

An Instructor may, within assigned scope:

- Author and revise course content
- Manage modules, lessons, resources, and schedules
- Create assignments, rubrics, and assessments
- Enroll or manage assigned learners where policy permits
- View necessary learner progress and submissions
- Grade or review authorized evidence
- Provide feedback and approve reassessment
- Facilitate cohort and event spaces
- Publish approved learning versions
- Review aggregated learning analytics

### Boundaries

An Instructor may not access unrelated organization data, change platform security, grant their own authority, view unnecessary sensitive records, alter credential history improperly, or use learner data outside approved educational purposes.

High-stakes assessment, credential issuance, accommodation access, and safeguarding information may require separate permissions, training, or review beyond the Instructor role.

---

## 8. Organization

Organization represents the institutional context through which an academy, school, business, nonprofit, team, or other governed entity manages membership, learning, data, policies, and delegated authority.

Organization is not a person role. Its powers are exercised by authorized members, service identities, and workflows within tenant boundaries.

### Organization Purpose

- Establish a governed LearningOS tenant
- Manage institutional identity and configuration
- Define programs, academies, cohorts, groups, and policies
- Assign scoped responsibilities to members
- Protect organization data and fulfill obligations
- Issue or sponsor approved learning and credentials
- Measure outcomes and maintain institutional continuity

### Organization Capabilities

An Organization may, through authorized actors:

- Configure identity provider, domain, branding, and settings
- Invite and manage memberships
- Define custom roles within allowed boundaries
- Create and govern academies, programs, and communities
- Assign content, journeys, projects, and assessments
- Establish retention, consent, privacy, and access policies
- Issue credentials under verified authority
- Access organization-scoped reporting
- Manage approved integrations and data exports
- Delegate and review administrative responsibility

### Boundaries

An Organization cannot claim ownership of all personal learner identity, private reflections, unrelated learning, or credentials issued by others. It cannot cross tenant boundaries, bypass platform safety, redefine platform-wide authority, or retain information beyond legitimate obligations.

Organization membership, data rights, portability, and departure should follow the Identity & Authentication Architecture and applicable agreements.

---

## 9. Administrator

An Administrator is a person or tightly governed service identity delegated operational authority within a specific scope.

### Administrator Types

- Organization Administrator
- Academy or Program Administrator
- Community Administrator
- Content Administrator
- Assessment Administrator
- Credential Administrator
- Security or Identity Administrator
- Billing or Integration Administrator

The system should prefer narrow administrator types over a single unrestricted organization administrator.

### Administrator Purpose

- Configure and operate approved institutional capabilities
- Manage memberships, roles, resources, and workflows
- Enforce policy and respond to operational needs
- Maintain service continuity and accountable records
- Support users within appropriate boundaries

### Typical Permissions

An Administrator may, according to assigned type:

- Manage selected settings and resources
- Invite, suspend, or remove memberships
- Grant roles they are authorized to delegate
- Configure programs, content, assessments, or credentials
- Review organization-scoped audit and operational information
- Resolve support and workflow issues
- Manage approved integrations, billing, or exports
- Conduct access reviews and continuity operations

### Boundaries

Administrators should not read learner content merely because they can manage the tenant. Sensitive-data access should be purpose-specific, logged, time-bounded where practical, and subject to policy.

Administrators cannot grant authority equal to or greater than their delegation, approve their own conflicting high-impact action, remove audit history, bypass tenant isolation, or assume Platform Steward authority.

---

## 10. Platform Steward

A Platform Steward is a highly restricted Project Genesis role responsible for the security, integrity, continuity, governance, and long-term mission of LearningOS across tenants.

### Platform Steward Purpose

- Protect platform-wide identity, authorization, safety, and reliability
- Govern platform policy and privileged operations
- Respond to severe incidents and systemic abuse
- Maintain tenant isolation and institutional trust
- Approve high-impact platform changes
- Preserve auditability, knowledge, and succession

### Stewardship Functions

Platform stewardship should be divided among specialties such as:

- Platform operations
- Security and incident response
- Privacy and data governance
- Trust and safety
- Identity and access governance
- Credential issuer governance
- Compliance and legal operations
- Platform policy and institutional stewardship

### Boundaries

Platform Stewards should not have routine unrestricted access to all learner and organization content. Privileged access requires purpose, approval proportional to impact, strong authentication, just-in-time or time-limited elevation where practical, audit, and post-use review.

Critical actions should use separation of duties, break-glass controls, independent notification, and immutable audit. Stewardship cannot be self-granted and should undergo recurring review and succession planning.

> "Leadership begins with service."

---

## 11. Permission Categories

Permissions should be expressed as actions on resources within scope rather than inferred only from broad role names.

### Category I — Discovery & Public Access

View, search, verify, register interest, and access publicly shared content.

### Category II — Personal Identity & Account

Manage own profile, authentication, sessions, preferences, privacy, consent, exports, connected services, and account lifecycle.

### Category III — Learning

Enroll, access, participate, practice, resume, reflect, receive feedback, and manage learner-selected goals.

### Category IV — Projects & Content

Create, edit, collaborate, review, version, submit, approve, publish, archive, and transfer project or content artifacts.

### Category V — Assessment & Credentials

Author, schedule, attempt, proctor where lawful and appropriate, grade, review, appeal, decide, issue, verify, correct, revoke, and report.

### Category VI — Community & Mentorship

Join, post, answer, collaborate, invite, mentor, facilitate, moderate, report, appeal, curate, and steward.

### Category VII — Organization & Membership

Configure tenant, invite members, assign scoped roles, manage groups, enforce policy, review access, and handle membership lifecycle.

### Category VIII — Data & Analytics

View personal or aggregated insights, create reports, export governed data, access audit information, and administer retention according to purpose.

### Category IX — Integrations & Commerce

Connect services, authorize scopes, manage secrets through protected systems, configure billing, products, orders, subscriptions, and financial reports.

### Category X — Platform Governance

Operate platform infrastructure, manage policy, respond to incidents, govern issuers, review abuse, execute break-glass access, and perform platform-wide continuity actions.

### Permission Evaluation

Every authorization decision should be able to consider:

```text
Authenticated Actor
  + Active Tenant
  + Assigned Role
  + Requested Action
  + Resource and Owner
  + Relationship
  + Object State
  + Trust and Assurance
  + Policy and Restrictions
  + Time and Environment
  = Permit or Deny with Reason
```

Deny should be the default. A permit should be explainable from current policy and attributable assignments.

> "Every role exists to help learners succeed."

---

## 12. Trust Ladder

Trust is demonstrated confidence for a specific responsibility. It should grow through evidence, training, conduct, review, and accountable service—not popularity or personal proximity to authority.

### Trust Level 0 — Public

No authenticated relationship. Access is limited to public resources and protected entry points.

### Trust Level 1 — Verified Account

Control of an approved authentication method is verified. The person may use personal LearningOS capabilities.

### Trust Level 2 — Established Participant

The member has accepted relevant conduct and organization terms and has a record of appropriate participation within a defined context.

### Trust Level 3 — Demonstrated Contributor

The member has produced attributable, useful work or knowledge and has shown reliability within a contribution scope.

### Trust Level 4 — Trusted Guide

The member has demonstrated relevant capability, completed required preparation, and is approved to mentor, review, facilitate, or instruct within boundaries.

### Trust Level 5 — Delegated Leader

The member has documented readiness, accountable authority, and responsibility for people, programs, communities, or organization operations.

### Trust Level 6 — Institutional Steward

The person holds narrow, high-impact authority governed by separation of duties, strong assurance, recurring review, audit, and succession.

### Trust Decisions

Movement up the Trust Ladder may require:

- Verified identity or affiliation appropriate to consequence
- Demonstrated capability and contribution
- Training, certification, or policy acknowledgment
- Conduct and safety record with due process
- Review by authorized people
- Defined scope, start, expiration, and review date
- Stronger authentication and security controls
- Conflict-of-interest disclosure
- Successful supervised or limited responsibility
- Continuing performance and community feedback

Trust can be reduced, suspended, expired, or revoked when conditions change. Actions must follow clear policy, evidence, communication, proportionality, appeal, and restoration paths where appropriate.

Trust is contextual. A trusted software mentor is not automatically qualified to assess teaching, administer an organization, or access safeguarding records.

---

## 13. Product Implications

### Make Roles Understandable

People should be able to see their active context, roles, scope, important responsibilities, and available escalation path without reading internal access-control terminology.

### Make Permission Requests Purposeful

When a capability is unavailable, the product should explain whether it requires a role, relationship, object state, stronger authentication, approval, or organization policy—without exposing sensitive security detail.

### Support Context Switching Safely

The Application Shell should display active organization and relevant role. Switching context should refresh permissions, data, navigation, AI context, search, and notifications.

### Provide Role-Specific Workspaces

Learners, contributors, mentors, instructors, administrators, and stewards need different actions and dashboards inside the same canonical information architecture. Role capability should not fragment the product into unrelated systems.

### Design Delegation and Expiration

Role assignment should require scope, grantor authority, reason, start, expiration or review, and notification. Temporary access should expire automatically.

### Protect High-Impact Actions

Role grants, assessment decisions, credential issuance, sensitive exports, identity changes, moderation actions, and platform operations may require reauthentication, confirmation, second approval, or cooling-off periods.

### Make Contribution a Pathway

The product should show how learners can become contributors, mentors, or instructors through explicit capability, conduct, preparation, and service—not hidden invitation alone.

### Support Appeal and Restoration

Role denial, suspension, trust change, moderation, and revoked authority should have understandable reasons and governed appeal paths where appropriate.

### Avoid Authority Theater

Badges, titles, colors, and profile prominence should not imply powers a person does not have. Visible authority should be scoped, current, and verifiable.

### Measure Responsible Enablement

Product review should examine successful contribution, permission clarity, least privilege, access-review completion, mentorship outcomes, security incidents, appeals, and successor development—not role count alone.

---

## 14. Engineering Implications

### Combine RBAC, ABAC, and Relationship Policy

Use role-based grants for understandable responsibility, attribute-based rules for context and state, and relationship-based checks for ownership, membership, mentorship, assignment, and collaboration.

### Model Assignments Explicitly

Role assignments should include subject, role, scope type, scope identifier, grantor, basis, start, expiration, status, restrictions, and audit metadata. Avoid global booleans for contextual authority.

### Treat Organization as a Tenant Boundary

Tenant context must be explicit in identity, queries, storage, search, events, jobs, analytics, caching, AI context, and authorization. Database and service controls should enforce isolation independently of UI routing.

### Centralize Policy without Creating One Point of Failure

Define governed permission vocabulary and reusable policy evaluation. Services should enforce decisions locally or through resilient policy infrastructure with versioning, caching rules, deny behavior, and observability.

### Authorize Every Request and Side Effect

Check permission at API, service, database, file, background job, event consumer, search, export, and tool boundary. Authorization at page load does not authorize later actions.

### Prevent Privilege Escalation

Enforce grant ceilings, separation of duties, non-self-approval, verified scopes, immutable platform roles, protected service identities, and safe defaults for custom roles.

### Use Step-Up and Just-in-Time Privilege

Sensitive operations should require recent strong authentication and, where practical, time-limited privileged sessions tied to a reason, approval, and audit trail.

### Build Break-Glass Access Carefully

Emergency access should be exceptional, short-lived, strongly authenticated, narrowly scoped, notified, fully audited, and reviewed after use. It must not become routine support access.

### Preserve Policy and Decision History

Store policy version, inputs, outcome, reason code, and material role events for consequential decisions. Logs must protect sensitive data and resist tampering.

### Invalidate Stale Authority

Role change, membership removal, session risk, policy update, organization suspension, and trust revocation should propagate promptly to sessions, caches, tokens, jobs, and real-time connections.

### Secure Service Identities

Background jobs, integrations, AI tools, and automated workflows need non-human identities, minimal scopes, secret rotation, environment boundaries, ownership, expiration, and audit.

### Test Authorization as a Matrix

Verification should cover every sensitive action across role, tenant, ownership, relationship, state, trust, assurance, time, and deny cases. Include cross-tenant attacks, object-reference abuse, stale sessions, custom roles, invitation races, delegation, and revocation.

### Review Access Continuously

Provide organization and platform access reviews, dormant privilege detection, expiring-role workflows, orphaned service-identity checks, and evidence for high-impact role recertification.

### Design for Policy Migration

Permission names, role definitions, and policy logic will evolve. Migrations should preserve intent, simulate effects, identify expanded access, support rollback, and communicate material changes.

---

## Canonical Status

User Roles & Permission Architecture is Canonical Blueprint 022 and the authoritative Project Genesis reference for LearningOS role hierarchy, permissions, demonstrated trust, delegation, and governance.

Future roles, dashboards, memberships, mentorships, instructional tools, organization settings, administrative operations, and platform stewardship should be evaluated by whether they enable meaningful contribution, keep authority scoped and accountable, and direct every responsibility toward learner success.
