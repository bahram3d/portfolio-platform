# Contributing / working agreements

This is a solo project, but it follows real team conventions on purpose — the
habits are part of the portfolio.

## Branching

- Trunk-based development off `main`.
- Short-lived feature branches: `feat/...`, `fix/...`, `chore/...`, `docs/...`.
- All changes land via pull request, even solo — PRs are where CI gates run and
  where design decisions get written down in the description.
- `main` is protected: PRs required, status checks must pass before merge.

## Commit messages

[Conventional Commits](https://www.conventionalcommits.org/):

```
feat(api): add project creation endpoint
fix(web): correct static param generation for blog slugs
docs(adr): add ADR-004 postgresql decision
chore(ci): add terraform validate workflow
```

Types: `feat`, `fix`, `docs`, `chore`, `refactor`, `test`, `ci`, `build`.

## Code style

### Python (`apps/api`)

- Formatter/linter: [`ruff`](https://docs.astral.sh/ruff/) (`ruff format`, `ruff check`)
- Type checking: `mypy --strict`
- Tests: `pytest`
- Line length: 100

### TypeScript (`apps/web`, `apps/admin`)

- Linter: `eslint` (Next.js config + recommended rules)
- Formatter: `prettier`
- `tsconfig.json`: `strict: true`
- No `any` without an inline justification comment

### Terraform (`infra/terraform`)

- `terraform fmt` before every commit
- `terraform validate` must pass
- One module per logical resource group; no copy-pasted provider blocks

## Architecture Decision Records

Any decision that would come up in an interview ("why did you choose X over
Y?") gets an ADR in `docs/adr/`. Use `docs/adr/template.md`. Small enough to
write in ten minutes — that's the point.

## Pull requests

Use the PR template. At minimum, confirm:

- [ ] Tests pass locally
- [ ] Linting/formatting clean
- [ ] Docs updated if behavior changed
- [ ] New architectural decision? → ADR added
