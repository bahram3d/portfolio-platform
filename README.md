# Multi-Cloud Data & AI Portfolio Platform

A production-style technical portfolio that demonstrates real-world skills in cloud
architecture, data engineering, and applied AI — not just a resume site, but a live
system you can point at.

> "Don't just tell recruiters what I know. Let them see me actually build it."

## What this is

- **Public site** (`bahramakbari.com`) — static-first Next.js site: home, about,
  resume, certifications, projects, blog, labs.
- **Admin portal** (`admin.bahramakbari.com`) — manage projects, blog posts, and
  certifications without touching code.
- **API** (`api.bahramakbari.com`) — FastAPI + PostgreSQL backend serving both.
- **Labs** — real, working demonstrations across Azure, AWS, GCP, and Oracle Cloud:
  a data engineering pipeline, a cloud architecture lab, and an AI workflow lab
  built around ComfyUI.

## Architecture

```
                 ┌───────────────┐
                 │   Cloudflare  │
                 └───────┬───────┘
                         │
              ┌──────────┴──────────┐
              │                     │
        Public Website          Admin Portal
              │                     │
              │                  FastAPI
              │                     │
              │                PostgreSQL
              │
        Portfolio / Labs
              │
       ┌──────┼───────┬───────┐
       │      │       │       │
     Azure   AWS     GCP   Oracle
```

Full details: [`docs/architecture.md`](docs/architecture.md).

## Repository layout

```
apps/
  web/      Next.js public site
  admin/    Admin portal
  api/      FastAPI backend
infra/
  terraform/  Infrastructure as code, per cloud
  docker/     Local dev + VM deployment via Docker Compose
docs/         Specification, architecture, ADRs, runbooks
```

## Status

This project is built incrementally, phase by phase. See
[`docs/project-specification.md`](docs/project-specification.md) for the full
roadmap. Currently: **Phase 0 — Planning & Foundation**.

## Local development

Setup instructions land here once `apps/api` and `apps/web` have working
skeletons (Phase 1–3).

## Documentation

- [Project specification](docs/project-specification.md)
- [Architecture](docs/architecture.md)
- [Deployment](docs/deployment.md)
- [Security](docs/security.md)
- [Database schema](docs/database.md)
- [API reference](docs/api.md)
- [CI/CD](docs/ci-cd.md)
- [Interview guide](docs/interview-guide.md)
- [Architecture Decision Records](docs/adr/)

## License

See [LICENSE](LICENSE).

