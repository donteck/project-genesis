# ADR-004: Google Drive Content Strategy

- **Status:** Accepted for initial architecture
- **Date:** 2026-07-30
- **Decision owner:** Emmanuel Tuffet

## Decision

Google Drive will serve as an external content repository for approved course files and instructor resources.

The application database remains the authoritative source for users, permissions, course structure, progress, and file metadata.

## Rules

- Students do not browse the administrator's personal Drive.
- The application exposes only approved resources.
- Drive file identifiers and synchronization status are stored in PostgreSQL.
- Permissions are controlled through the platform and the Google Drive API.
- Failed synchronization operations must be retryable and auditable.

## Course Folder Pattern

```text
Course
├── Overview
├── Module 01
├── Module 02
├── Module 03
├── Quizzes
├── Assignments
├── Projects
├── Workbook
├── Instructor Guide
└── Certificates
```

## Consequences

Google Drive is an integration, not the system database. The product must remain functional and understandable even when Drive synchronization is temporarily unavailable.
