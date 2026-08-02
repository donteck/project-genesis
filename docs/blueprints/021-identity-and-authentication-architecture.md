# Canonical Blueprint 021

## Identity & Authentication Architecture

| Record | Details |
|---|---|
| Blueprint number | 021 |
| Status | Canonical |
| Date established | August 2, 2026 |
| Authority | Project Genesis |
| Steward | Merchay Global Vision |
| Scope | LearningOS discovery, registration, authentication, verification, onboarding, profiles, preferences, consent, organizations, roles, learning identity, account security, and lifecycle management |
| Purpose | Define the complete identity lifecycle, authentication model, onboarding experience, privacy principles, and learner profile architecture for LearningOS. |

---

## Purpose and Authority

Identity is the durable relationship through which LearningOS recognizes a person, protects access, remembers authorized context, supports learning, attributes work, verifies evidence, and preserves growth across time. Authentication is one essential part of that relationship, but it is not the whole identity.

LearningOS should know enough to serve each learner responsibly without claiming ownership of the person or collecting information without purpose. Identity architecture must hold security and personalization together: prove access appropriately, keep organizations separated, preserve learner control, and allow a profile to grow through authentic activity and contribution.

This blueprint defines the identity philosophy, lifecycle, eight components, authentication flow, privacy and consent, security, lifelong identity, and product and engineering requirements for LearningOS.

> "Authentication grants access. Identity creates understanding."

---

## 1. Why Identity Matters

Learning is personal and cumulative. A learner returns to goals, courses, projects, reflections, assessments, credentials, portfolios, communities, and mentorship relationships over time. Without coherent identity, that continuity fragments. Without trustworthy authentication, the continuity cannot be protected.

Identity matters because it:

- Protects access to personal and organizational information
- Preserves learning continuity across sessions and devices
- Attributes projects, evidence, feedback, and contribution accurately
- Connects learners to organizations, cohorts, roles, and permissions
- Supports preferences, accessibility, language, and communication choices
- Enables responsible personalization and AI context
- Provides provenance for assessment and credentials
- Gives learners control over profiles, portfolios, sharing, and consent
- Supports recovery, correction, export, transition, and account closure
- Creates the foundation for trust among learners, educators, mentors, and institutions

Identity errors have human consequences. A duplicated account can split a learning record. An incorrect role can expose private data or block opportunity. Weak recovery can permanently separate a learner from years of evidence. Excessive personalization can become surveillance.

Identity should therefore be treated as human and institutional infrastructure, not merely a login form or user table.

---

## 2. The Identity Philosophy

The LearningOS identity system is governed by the following principles.

### One Person, Contextual Identities

A person should have one durable platform identity where appropriate while participating through distinct organization memberships, roles, profiles, and visibility settings. Context should not require unnecessary duplicate accounts.

### Authentication Is Proportionate

The strength of authentication should reflect the sensitivity and consequence of the action. Reading a public page, editing a profile, issuing a credential, and administering an organization do not require identical assurance.

### Personalization Requires Purpose

Identity data should be collected and used only for a defined learning, security, accessibility, operational, legal, or learner-selected purpose.

### The Learner Can See and Correct the Record

People should be able to understand important identity data, correct inaccuracies, manage appropriate visibility and consent, and challenge consequential interpretations.

### Roles Are Context, Not Personal Worth

Learner, builder, mentor, educator, creator, reviewer, administrator, and steward are scoped responsibilities. A person may hold several roles and should not be permanently defined by any one of them.

### Learning Identity Is Earned through Evidence

Capabilities, credentials, projects, reputation, and contribution should emerge from attributable activity and governed evidence rather than unsupported profile claims or hidden prediction.

### Privacy Is the Default Boundary

New personal information and learning records should begin with the narrowest appropriate visibility. Sharing should be understandable and deliberate.

### Identity Must Be Portable and Recoverable

Learners should be able to retain meaningful records across devices, organizational transitions, and platform evolution without weakening security or third-party rights.

> "Trust is the first lesson every platform should teach."

---

## 3. The Identity Lifecycle

The canonical identity lifecycle is:

```text
Discover
  ↓
Register
  ↓
Verify
  ↓
Onboard
  ↓
Personalize
  ↓
Learn
  ↓
Build
  ↓
Grow
  ↓
Mentor
```

### Discover

A person encounters public LearningOS content, understands the platform's purpose, and can evaluate relevant opportunities before creating an account. Nonessential tracking should not be a condition of discovery.

### Register

The person creates or accepts an account relationship using the minimum required information, clear terms, and an available authentication method appropriate to context.

### Verify

LearningOS establishes control of the chosen authentication channel and, when necessary, verifies additional identity or organization claims proportional to their consequence.

### Onboard

The learner understands the product, privacy choices, active organization, expected conduct, available support, and the immediate path to value.

### Personalize

The learner chooses goals, preferences, accessibility, language, communication, and profile information that improve the experience. Personalization remains editable and should not require unnecessary disclosure.

### Learn

The identity begins accumulating authorized learning continuity: enrollments, journey state, practice, feedback, and approved AI context.

### Build

Projects, artifacts, decisions, collaboration, authorship, and contribution become attributable to the learner and relevant team contexts.

### Grow

Evidence, assessments, capabilities, credentials, reflections, portfolio records, and goals form a longitudinal learning identity under learner and institutional governance.

### Mentor

The person may assume verified responsibility for helping others, with explicit role readiness, boundaries, safeguarding, accountability, and continuing review.

The lifecycle does not end at Mentor and does not require every person to follow the same path. Mentors continue learning, roles change, organizations change, and identity should support repeated cycles of growth.

---

## 4. The Eight Identity Components

### Component I — Account

The Account is the durable platform-level record representing the person's relationship with LearningOS.

It includes:

- Stable internal identifier
- Account status and lifecycle dates
- Primary authentication relationships
- Recovery and security state
- Applicable terms and required policy acknowledgments
- Account closure, restriction, and transition status

The account identifier should not expose sensitive or sequential information publicly.

### Component II — Authentication

Authentication establishes that the current actor controls an approved credential or identity-provider relationship.

It includes:

- Passwordless, password, passkey, or federated methods as supported
- Multi-factor enrollment and challenge
- Verified email, phone, or provider claims where used
- Sessions, devices, refresh, revocation, and recent authentication
- Recovery methods and risk events
- Authentication assurance level

Authentication secrets should remain isolated from profile and learning data.

### Component III — Profile

The Profile contains learner-controlled identity and presentation information.

It may include:

- Preferred name and pronouns where voluntarily provided
- Avatar or image
- Headline, biography, interests, and direction
- Language, locale, time zone, and location at appropriate precision
- Public or community-facing links
- Audience-specific visibility settings

Legal or verified identity should remain separate from public presentation when possible.

### Component IV — Memberships & Roles

Memberships connect a person to organizations, academies, cohorts, groups, teams, and mentorship relationships.

They include:

- Tenant and community context
- Role, status, scope, start, and end dates
- Invitation and acceptance provenance
- Permissions and delegated authority
- Program, cohort, team, or group relationships
- Suspension, removal, and transition records

Roles should be scoped and least-privileged rather than stored as one global status.

### Component V — Preferences & Accessibility

Preferences express how the learner chooses to experience LearningOS.

They may include:

- Language and regional formatting
- Accessibility and assistive preferences
- Communication channels, frequency, and quiet hours
- Display, motion, contrast, caption, and reading preferences
- AI interaction and personalization settings
- Calendar, time, and reminder choices

Sensitive accommodation records should be separated from ordinary interface preferences and accessed only as necessary.

### Component VI — Privacy & Consent

Privacy & Consent records which uses, sharing, terms, and optional experiences the learner has accepted, declined, changed, or withdrawn.

It includes:

- Purpose and data categories
- Policy and notice version
- Choice, time, actor, and context
- Required versus optional basis
- Withdrawal and downstream effect
- Age, guardian, or organizational authority where applicable

Consent should not be used where a different legal or institutional basis is the honest governing mechanism.

### Component VII — Learning Identity

Learning Identity is the longitudinal, evidence-connected record of development.

It may include:

- Aspirations, journeys, and learner-selected goals
- Enrollments, progress, practice, and projects
- Feedback, reflections, assessments, and capabilities
- Credentials and Learning Passport records
- Portfolio evidence and contribution
- Mentorship received and provided

Each domain remains the source of truth for its records. Learning Identity is a governed relationship layer, not one unrestricted profile document.

### Component VIII — Trust & Verification

Trust & Verification represents the assurance and status of particular claims and responsibilities.

It may include:

- Verified contact methods
- Identity-proofing level where required
- Organization-verified affiliation
- Credential and issuer verification
- Mentor, reviewer, educator, or administrator readiness
- Security restrictions and risk state
- Disputed, corrected, expired, or revoked claims

Trust should be contextual and explainable. It should not become a secret universal score of a person.

---

## 5. Authentication Flow

Authentication should be secure, accessible, comprehensible, and proportionate to the requested action.

### Canonical Sign-In Flow

```text
Access Request
  ↓
Identify Account or Approved Provider
  ↓
Authenticate Primary Method
  ↓
Evaluate Risk and Required Assurance
  ↓
Perform Additional Verification When Required
  ↓
Create or Refresh Scoped Session
  ↓
Resolve Organization, Role, and Permissions
  ↓
Continue to Intended Destination
  ↓
Monitor, Renew, Step Up, or Revoke
```

### Authentication Methods

LearningOS may support:

- Passkeys
- Verified magic links or one-time codes
- Passwords with secure controls where needed
- Authenticator applications or hardware-backed factors
- Approved social or enterprise identity providers
- Organization single sign-on
- Recovery codes and governed assisted recovery

Method availability should consider audience, region, age, organization policy, accessibility, security, and recovery. The system should prefer phishing-resistant methods where practical without excluding people who cannot use them.

### Session Principles

- Issue short-lived, scoped access with securely managed renewal
- Rotate or revoke credentials and sessions after material risk
- Bind organization context explicitly
- Require recent or stronger authentication for sensitive actions
- Display active sessions and meaningful device information
- Support remote revocation and account-wide sign-out
- Protect against fixation, replay, theft, cross-site attacks, and token leakage
- Avoid exposing secrets in URLs, logs, analytics, or client storage

### Account Recovery

Recovery must not be weaker than the account it protects. It should use multiple signals proportional to risk, notify the account holder, invalidate compromised sessions, provide delay or human review for high-impact changes where appropriate, and avoid knowledge questions based on discoverable personal facts.

Authentication errors should protect against account enumeration while still giving legitimate users a usable recovery path.

---

## 6. Privacy & Consent

Privacy gives learners meaningful boundaries around identity, learning, relationships, and future opportunity. Consent is one mechanism through which appropriate choices are expressed and recorded.

### Privacy Principles

- Collect the minimum data necessary for a defined purpose
- Explain what is collected, why, who can access it, and how long it remains
- Keep security, profile, learning, assessment, community, and commercial purposes distinct
- Use private or narrow visibility by default
- Prevent cross-organization use without authority
- Avoid sensitive inference unless necessary, governed, and disclosed
- Give learners appropriate access, correction, export, deletion, and restriction paths
- Protect private reflection, mentorship, assessment, and accommodation information
- Review vendors, models, integrations, and exports for downstream use
- Apply age-appropriate design and guardian processes where required

### Consent Experience

A valid consent experience should be:

- Specific to an understandable purpose
- Presented before optional processing begins
- Separated from unrelated choices
- Freely chosen where consent is the basis
- Recorded by version and context
- Easy to revisit and withdraw
- Honest about effects and technical limitations of withdrawal
- Accessible in language and interaction

### AI and Personalization

Learners should understand which identity, journey, project, assessment, reflection, and community data may inform AI features. Optional durable AI memory should have clear controls. Model training or unrelated reuse requires separate authority and should not be hidden inside general personalization.

### Visibility

Profile, community identity, portfolio, credentials, Learning Passport, presence, and contact information should have explicit audience models. Public profile status should not automatically make learning records public.

> "Every learner deserves a secure and personalized beginning."

---

## 7. Security Principles

Identity security protects people, organizations, learning evidence, and the trustworthiness of LearningOS.

### Least Privilege

Grant the minimum role and permission needed for the current context. Privilege should expire, be reviewable, and require explicit delegation.

### Tenant Isolation

Organization identity, membership, data, and policy boundaries must be enforced at every relevant layer. A user with access to multiple organizations must have an explicit active context.

### Defense in Depth

Use secure identity-provider configuration, application authorization, database controls, network protection, monitoring, rate limiting, audit, secrets management, and incident response rather than relying on one control.

### Strong Defaults

Secure session handling, private profiles, verified redirect destinations, minimal scopes, safe recovery, and protected administrative actions should be defaults.

### Reauthentication and Step-Up

Require recent or stronger authentication for credential issuance, role elevation, security changes, sensitive exports, organization administration, destructive actions, and other high-impact operations.

### Separation of Duties

High-impact identity proofing, administrator grants, credential issuance, safeguarding access, and recovery overrides may require multiple authorities or independent review.

### Audit with Restraint

Record consequential identity, role, consent, security, verification, export, and account-lifecycle events. Protect logs from tampering and sensitive overcollection.

### Abuse Resistance

Protect registration, verification, invitation, recovery, session, API, and messaging flows against automation, enumeration, spam, impersonation, takeover, privilege escalation, and social engineering.

### Secure Failure

When identity systems are unavailable or uncertain, deny sensitive access, preserve work safely, communicate status clearly, and provide a recoverable path without bypassing controls.

### Incident Readiness

Maintain processes for session revocation, credential rotation, affected-user communication, forensic preservation, recovery, correction, and lessons learned.

Security should be evaluated through threat modeling, code and configuration review, automated testing, penetration testing proportional to risk, and recurring access review.

---

## 8. Lifelong Identity

Lifelong Identity allows a learner's meaningful evidence and relationships to remain coherent as goals, roles, organizations, technologies, and life stages change.

### Lifelong Continuity

The system should support:

- Changes to preferred and verified identity through governed processes
- Multiple organizations without fragmenting the person
- Movement from learner to builder, mentor, educator, and leader
- Longitudinal journeys, projects, capabilities, and credentials
- Recognition of external learning with honest provenance
- Portable Learning Passport and portfolio exports
- Organization departure without loss of learner-owned evidence
- Credential expiration, renewal, correction, and revocation
- Account recovery after long inactivity
- Succession from present authentication methods to future methods

### Ownership and Custodianship

Learners should control personal presentation, goals, private reflections, portfolio views, and appropriate exports. Institutions retain authority over their records, credentials, policies, and legally required history. Collaborators and third parties retain applicable rights in shared work.

LearningOS should make these boundaries understandable rather than use the word *ownership* to obscure legitimate shared responsibilities.

### Identity Transition

When a learner leaves an organization, the platform should distinguish:

- Personal records that continue with the learner
- Organization records the learner may retain or reference
- Restricted information that cannot transfer
- Credentials and evidence that remain independently verifiable
- Shared project artifacts governed by collaboration agreements
- Data subject to retention or deletion duties

### Future Portability

Identity architecture should support durable identifiers, interoperable authentication and credential standards, accessible exports, and migrations that do not require a learner to begin again.

> "Identity grows with every project, reflection, and contribution."

---

## 9. Product Implications

### Let People Discover before Registering

Public information should help a person understand value, requirements, privacy, and trust before account creation. Registration gates should protect a real need rather than inflate account metrics.

### Ask for Information Progressively

Collect only what is needed at each stage. A learner can begin with a secure account and add goals, profile, organization, or professional evidence as relevant.

### Make Onboarding Produce Value

Onboarding should confirm security, explain context and privacy, set an appropriate goal, establish accessibility and communication preferences, and lead to a meaningful first action.

### Keep Context Visible

The Application Shell should show active organization and identity when context changes permissions, data, or actions. Switching should be deliberate and recoverable.

### Separate Profile from Security

Public profile editing, authentication methods, verified identity, organization roles, privacy, consent, and learning records should have distinct interfaces and consequences.

### Design Recovery as a First-Class Journey

Recovery should be accessible, understandable, secure, status-aware, and supported by human escalation for exceptional cases. Learners should know what was recovered and which sessions or methods changed.

### Provide an Identity Center

Account should provide coherent access to profile, organizations, roles, authentication, sessions, devices, privacy, consent, AI memory, notifications, exports, connected services, and account lifecycle.

### Support Trust without Surveillance

Verification markers should name the claim and authority. Avoid universal trust scores, covert risk labels, or behavioral identity presented as objective truth.

### Design for Account Transition and Closure

Learners should understand the effects of leaving an organization, deleting an account, retaining credentials, transferring projects, removing public profiles, and satisfying legal retention.

### Measure Successful Beginnings

Product review should examine secure registration, verification success, onboarding comprehension, time to meaningful value, recovery success, consent understanding, accessibility, and trust—not signup volume alone.

---

## 10. Engineering Implications

### Separate Identity Domains

Authentication credentials, platform account, profile, organization membership, authorization, preferences, consent, learning identity, and verification should have explicit models and service boundaries.

### Use Stable Internal Identifiers

Relationships should use non-guessable, immutable internal identifiers. Email, phone, username, provider subject, and display name can change and should not become permanent relational keys.

### Model External Identities Safely

Store provider, issuer, subject, assurance, verification, scopes, and lifecycle. Prevent unsafe automatic linking based solely on unverified or recycled contact information.

### Enforce Authorization Server-Side

Every protected operation should evaluate authenticated actor, active tenant, membership, role, resource ownership, relationship, object state, policy, and required assurance. Interface hiding is not authorization.

### Protect Session and Token Lifecycles

Use secure cookies or equivalent protected mechanisms, short-lived access, rotation, replay detection where appropriate, revocation, verified redirect allowlists, CSRF protection, and careful logging.

### Build Policy-Aware Onboarding

Onboarding should be resumable, versioned, organization-aware, and idempotent. Required steps and optional personalization must remain distinguishable.

### Model Consent as Immutable Events

Record subject, purpose, notice version, choice, basis, time, context, actor, and withdrawal. Derive current state without erasing historical accountability.

### Protect Data by Classification

Classify authentication secrets, contact information, profile data, organization records, learning data, assessments, reflections, accommodations, safeguarding records, and public evidence. Apply distinct access, encryption, retention, and logging rules.

### Engineer Account Linking and Merge Conservatively

Duplicate detection, provider linking, account merge, and record transfer require proof, preview, conflict handling, audit, rollback strategy, and protection against takeover.

### Support Export, Transition, and Deletion

Lifecycle workflows should coordinate domain-owned records, third-party systems, retention holds, anonymization, credential continuity, public-cache removal, and completion status through reliable background processing.

### Make Security Events Observable

Monitor authentication failures, suspicious registration, verification abuse, recovery, provider changes, MFA changes, session anomalies, role elevation, cross-tenant denial, sensitive exports, and administrative overrides.

### Minimize Sensitive Observability

Logs and traces should identify events and correlation without storing secrets, raw tokens, unnecessary personal content, or sensitive learning records.

### Test the Complete Identity Lifecycle

Verification should cover registration, verification, sign-in, passkeys, MFA, federated identity, SSO, invitations, multiple organizations, role changes, consent, recovery, session revocation, account linking, export, organization departure, closure, deletion, and restoration constraints.

### Prepare for Provider and Standard Change

Authentication, credentials, and portability should use replaceable adapters, documented contracts, migration paths, key rotation, and provider-exit plans. A learner's identity must not be trapped by one authentication vendor.

---

## Canonical Status

Identity & Authentication Architecture is Canonical Blueprint 021 and the authoritative Project Genesis reference for the LearningOS identity lifecycle, authentication model, onboarding, privacy, consent, security, learner profile, and lifelong identity.

Future registration, authentication, onboarding, profiles, roles, personalization, AI memory, learning records, credentials, mentorship, and account-lifecycle features should be evaluated by whether they create a secure beginning, preserve trustworthy continuity, and help identity grow through authentic learning and contribution.
