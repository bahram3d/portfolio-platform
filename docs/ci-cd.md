# CI/CD

Status: stub — expands as workflows are added.

## Current workflows (Phase 0)

- `ci-web.yml` — lint + typecheck for `apps/web` and `apps/admin`
- `ci-api.yml` — lint (ruff) + typecheck (mypy) + tests (pytest) for `apps/api`
- `ci-terraform.yml` — `terraform fmt -check` + `terraform validate`

## Planned (Phase 1+)

- CD workflow: build Docker images → push → deploy to Oracle VM → health check
- Security/dependency scanning workflow (Phase 9)
