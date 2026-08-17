# ADR-003: FastAPI for the backend

**Status:** Accepted
**Date:** 2026-08-10

## Context

Need a Python backend (to match the data engineering/AI skill set being
demonstrated) that's fast to build, has strong typing support, and produces
self-documenting APIs.

## Decision

Use FastAPI for `apps/api`.

## Alternatives considered

- **Django** — batteries-included but heavier than needed for an API-only
  service; ORM/admin features overlap with the purpose-built admin portal.
- **Flask** — lighter, but no built-in validation/typing/OpenAPI generation;
  would require bolting on Pydantic and docs tooling manually.
- **Node/Express** — would break the Python-centric skill narrative
  (data engineering, AI/ML) the platform is meant to showcase.

## Trade-offs

Gain: automatic OpenAPI docs, Pydantic validation, async support, strong type
hints throughout — good match for `mypy --strict`.
Give up: smaller ecosystem of pre-built admin/CMS tooling than Django.

## Interview angle

"FastAPI gave me typed request/response models and free OpenAPI docs, which
mattered because the API is consumed by two separate frontends — the schema
becomes the contract between them."
