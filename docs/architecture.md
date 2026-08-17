# Architecture

## System overview

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

## Routing

| Subdomain | Serves |
|---|---|
| `bahramakbari.com` | Public Next.js site (static) |
| `admin.bahramakbari.com` | Admin portal |
| `api.bahramakbari.com` | FastAPI backend |

All three sit behind Cloudflare for DNS, TLS, caching, and basic edge
protection. See [ADR-005](adr/ADR-005-cloudflare-edge-layer.md).

## Data flow: publishing content

```
Admin → API → PostgreSQL → (publish trigger) → Public site rebuild/revalidate
```

The public site stays static-first even though content is dynamic — see
[ADR-001](adr/ADR-001-static-first-nextjs.md).

## Initial infrastructure (Phase 1)

```
Oracle Cloud VM
      │
    Docker
      │
Docker Compose
      │
 ┌────┼──────────┐
 │    │          │
Web  API      Database
 │    │
Nginx FastAPI
```

## Multi-cloud roles

See [ADR-009](adr/ADR-009-multicloud-allocation.md) for the full rationale.

- **Oracle Cloud** — primary hosting
- **Azure** — data/analytics lab
- **AWS** — AI lab (ComfyUI)
- **GCP** — BigQuery/Vertex AI lab

## TODO

- [ ] Detailed database schema (Phase 3) → `docs/database.md`
- [ ] API contract (Phase 3) → `docs/api.md`
- [ ] Per-lab architecture diagrams (Phase 6–7)
