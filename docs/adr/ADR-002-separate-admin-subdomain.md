# ADR-002: Separate admin subdomain instead of embedded admin routes

**Status:** Accepted
**Date:** 2026-08-10

## Context

Content management needs auth, forms, and dynamic rendering — the opposite of
what the public site optimizes for. Both could live in one Next.js app under
`/admin`, or be split into a separate application.

## Decision

Admin lives as its own app at `admin.bahramakbari.com`, deployed and scaled
independently from the public site.

## Alternatives considered

- **`/admin` routes inside the public Next.js app** — would pull
  authenticated, dynamic rendering into a codebase optimized for static
  export, complicating the build and increasing the public site's attack
  surface.

## Trade-offs

Gain: clean separation of concerns, independent deploy cadence, smaller blast
radius if the admin app has a bug or vulnerability — it can't take down the
public site.
Give up: some duplicated tooling/config (two Next.js apps instead of one).

## Interview angle

"Public and admin have fundamentally different security and rendering needs,
so I split them at the application boundary rather than the route level —
that also means a bug in the admin app can never take the public site down."
