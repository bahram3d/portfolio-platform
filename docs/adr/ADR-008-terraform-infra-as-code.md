# ADR-008: Terraform for infrastructure as code

**Status:** Accepted
**Date:** 2026-08-10

## Context

Infrastructure spans multiple clouds (Oracle, Azure, AWS, GCP), each with
different consoles and CLIs. Manual setup is slow to reproduce, easy to
document incorrectly, and doesn't demonstrate IaC skill.

## Decision

Use Terraform for infrastructure that benefits from being reproducible:
networking, compute, and core cloud resources. Not every manual console
action needs to be Terraformed on day one — apply it where it earns its keep.

## Alternatives considered

- **Cloud-native IaC per provider (CloudFormation, ARM/Bicep, Deployment
  Manager)** — would mean learning and maintaining four different tools
  instead of one consistent workflow across providers.
- **Manual console setup only** — fastest to start, but not reproducible,
  not reviewable in a PR, and doesn't demonstrate the skill.

## Trade-offs

Gain: one consistent workflow across four clouds, reviewable infra changes,
a reproducible environment story for interviews.
Give up: upfront learning/setup cost per provider's Terraform provider.

## Interview angle

"I used Terraform specifically because it's provider-agnostic — the same
workflow and mental model applies whether I'm provisioning the Oracle VM or
an AWS resource for the AI lab, which mattered given the multi-cloud scope."
