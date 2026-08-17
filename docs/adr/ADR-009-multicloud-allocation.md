# ADR-009: Multi-cloud allocation rationale

**Status:** Accepted
**Date:** 2026-08-10

## Context

Using four clouds risks looking scattered or resume-padded unless each one
has a distinct, justified purpose.

## Decision

Assign each cloud a specific role tied to a specific skill set being
demonstrated:

- **Oracle Cloud** — primary low-cost hosting (Always Free VM) for the core
  platform.
- **Azure** — data/analytics portfolio: Fabric, Azure data services, SQL,
  AI-enabled database work.
- **AWS** — AI/cloud engineering demonstrations, primarily the ComfyUI AI lab.
- **GCP** — BigQuery, Vertex AI, data analytics, cloud architecture.

## Alternatives considered

- **Single cloud for everything** — simpler ops, but doesn't demonstrate
  breadth across the providers relevant to the target roles (which span
  Azure, AWS, and GCP job postings).
- **Even split with no clear rationale per cloud** — "resume padding" risk;
  reviewers can tell when a cloud is used for no functional reason.

## Trade-offs

Gain: each cloud maps directly to a resume line and an interview story;
avoids the "four clouds for no reason" critique.
Give up: more operational surface area (four sets of credentials, billing,
IAM) than a single-cloud setup.

## Interview angle

"Each cloud has a specific job tied to the skills I'm demonstrating — Oracle
for cost-efficient hosting, Azure for the data/analytics story, GCP for
BigQuery and Vertex AI, AWS for the AI lab. It's not four clouds for the sake
of four logos."
