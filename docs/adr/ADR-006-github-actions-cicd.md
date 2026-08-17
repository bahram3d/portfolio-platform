# ADR-006: GitHub Actions for CI/CD

**Status:** Accepted
**Date:** 2026-08-10

## Context

Need CI (lint, type check, test, terraform validate) and eventually CD
(build → push image → deploy to the Oracle VM), tightly integrated with the
GitHub-hosted monorepo, at no additional cost.

## Decision

Use GitHub Actions for both CI and CD.

## Alternatives considered

- **GitLab CI / CircleCI / Jenkins** — would require hosting the repo
  elsewhere (GitLab) or adding a separate CI vendor with its own
  auth/secrets management, for no functional gain given GitHub already hosts
  the code.
- **Self-hosted runner from day one** — unnecessary operational overhead for
  a low-traffic portfolio project; GitHub-hosted runners are sufficient and
  free for a public/personal repo.

## Trade-offs

Gain: zero extra vendor, native GitHub integration (status checks, branch
protection, PR gating), directly demonstrates a widely-used CI/CD tool.
Give up: some vendor lock-in to GitHub's workflow syntax.

## Interview angle

"CI/CD is a first-class part of this project, not an afterthought — GitHub
Actions gates every PR with lint/type/test checks, and later handles building
and deploying the Docker image to the Oracle VM."
