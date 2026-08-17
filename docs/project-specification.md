# Project specification

## Goal

Build a production-style technical portfolio platform demonstrating real
skills across Azure, AWS, GCP, Oracle Cloud, data engineering, data
analytics, AI/generative AI, Python, SQL, DevOps, Docker, Terraform, CI/CD,
cloud architecture, and software engineering. The platform itself is a
portfolio project.

## Components

- **Public site** (`bahramakbari.com`) — static-first Next.js.
- **Admin portal** (`admin.bahramakbari.com`) — content management.
- **API** (`api.bahramakbari.com`) — FastAPI + PostgreSQL.
- **Labs** — data engineering, cloud, and AI, spread across four clouds.

## Static + dynamic split

Mostly static: home, about, general skills, architecture explanations,
resume layout, certification presentation.

Dynamic (admin-managed): projects, blog posts, screenshots, architecture
diagrams, certifications, selected resume info, AI workflow gallery.

## Multi-cloud allocation

See [ADR-009](adr/ADR-009-multicloud-allocation.md).

## Development phases

| Phase | Focus |
|---|---|
| 0 | Planning & foundation |
| 1 | Infrastructure (Oracle VM, Docker, Cloudflare, first deploy) |
| 2 | Public frontend |
| 3 | Backend (FastAPI, PostgreSQL, auth foundation) |
| 4 | Admin portal |
| 5 | Dynamic publishing (admin → API → DB → public site) |
| 6 | Data/cloud labs |
| 7 | AI lab (ComfyUI, AWS) |
| 8 | Multi-cloud expansion |
| 9 | Production hardening |
| 10 | Interview mode |

Full detail on each phase lives in this doc's history and in `docs/adr/` for
the decisions behind them. The guiding rule: every phase ends with something
working — plan → build → test → deploy → document → learn → next phase.

## Non-goals

- Kubernetes, unless a genuine scaling need emerges (see
  [ADR-007](adr/ADR-007-docker-compose-not-kubernetes.md)).
- Tools or patterns adopted purely for resume/aesthetic value.
