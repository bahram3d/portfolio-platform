# ADR-007: Docker Compose initially, not Kubernetes

**Status:** Accepted
**Date:** 2026-08-10

## Context

The platform runs a handful of containers (web, admin, api, postgres, nginx)
on a single Oracle Free Tier VM. Kubernetes is a common resume keyword, which
creates temptation to adopt it regardless of fit.

## Decision

Use Docker Compose for orchestration. Kubernetes is not adopted unless a
genuine scaling or multi-node requirement emerges later (Phase 8+).

## Alternatives considered

- **Kubernetes (k3s/EKS/GKE/AKS) from the start** — massive operational
  overhead (cluster management, networking, secrets, ingress controllers) for
  a workload that fits comfortably on one VM. Would violate the project's
  core principle of not adding complexity for appearances.

## Trade-offs

Gain: dramatically simpler ops, faster iteration, lower cost, still fully
demonstrates containerization skills.
Give up: doesn't showcase Kubernetes specifically — mitigated by documenting
this decision explicitly (this ADR) so it reads as a deliberate engineering
call, not a skill gap.

## Interview angle

"I deliberately didn't reach for Kubernetes — five containers on one VM don't
need a scheduler and control plane. If a real scaling need shows up later,
I've documented what would trigger that migration, but I won't add
complexity just to have it on a resume."
