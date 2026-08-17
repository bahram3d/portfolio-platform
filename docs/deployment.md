# Deployment

Status: stub — filled in during Phase 1.

## Planned flow

```
GitHub → GitHub Actions → Build → Docker image → Oracle Cloud VM
    → Docker Compose → Deployment → Health check
```

## TODO (Phase 1)

- [ ] Oracle VM provisioning steps (Terraform)
- [ ] SSH hardening
- [ ] Firewall rules
- [ ] Docker Compose file walkthrough
- [ ] Cloudflare DNS + TLS setup
- [ ] First deployment runbook
