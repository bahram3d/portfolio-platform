# Security

Status: stub — expanded incrementally as each phase adds a new surface.

Security is treated as part of every phase, not a final pass. Baseline
commitments:

- HTTPS everywhere (via Cloudflare)
- Admin authentication + role-based authorization
- Database never publicly exposed
- Firewall restrictions on the Oracle VM
- Secrets via environment variables / GitHub Secrets, never committed
- Input validation on all API endpoints
- Secure file upload handling (media)
- Audit logging on admin actions
- Dependency and container image scanning in CI
- Documented backup and recovery procedure

## TODO

- [ ] Threat model for the admin portal (Phase 4)
- [ ] Auth implementation details (Phase 3)
- [ ] Dependency scanning workflow (Phase 9)
