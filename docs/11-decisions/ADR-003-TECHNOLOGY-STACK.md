# ADR-003: Initial Technology Stack

- **Status:** Accepted for MVP
- **Date:** 2026-07-30
- **Decision owner:** Emmanuel Tuffet

## Decision

Project Genesis will begin with the following technology direction:

- Next.js
- TypeScript
- Tailwind CSS
- React Flow
- Supabase
- PostgreSQL
- Supabase Auth
- OpenAI through a provider-abstracted AI service
- Google Drive API
- GitHub
- Vercel

## Rationale

This stack supports rapid product development while preserving a professional path to scaling. It also aligns with the founder's broader Uwebbz development ecosystem.

## Architectural Approach

The MVP will use a modular monolith. Clear domain boundaries will allow selected components to become separate services if scale, reliability, or team ownership later requires it.

## Consequences

- TypeScript should be used across the application wherever practical.
- Database access and authorization require explicit security policies.
- AI provider details should not be embedded throughout the product.
- External integrations must be wrapped behind application services.
