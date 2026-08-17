# ADR-004: PostgreSQL as the primary database

**Status:** Accepted
**Date:** 2026-08-10

## Context

Content (projects, blog posts, certifications, resume entries) is inherently
relational: projects have sections, media, tags; blog posts have authors and
publish state. The platform also wants to demonstrate SQL skill, which is a
target-role requirement (Data Engineer/Analyst).

## Decision

Use PostgreSQL as the system of record for all structured content.

## Alternatives considered

- **NoSQL (MongoDB/DynamoDB)** — content relationships (project → sections →
  media, tags, certifications) are naturally relational; modeling them as
  documents would mean either heavy duplication or application-side joins.
- **SQLite** — fine for local dev, insufficient for concurrent
  admin+API access in production.

## Trade-offs

Gain: strong consistency, mature migration tooling, directly demonstrates SQL
skills relevant to target roles.
Give up: slightly more upfront schema design work than a schemaless store.

## Interview angle

"The content model is relational by nature — a project has many sections and
media items, tagged and cross-referenced — so Postgres was the natural fit,
and it doubles as a SQL skill demonstration."
