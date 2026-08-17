# ADR-005: Cloudflare as the DNS/CDN/edge layer

**Status:** Accepted
**Date:** 2026-08-10

## Context

Three subdomains (public, admin, API) need DNS, TLS, and protection from basic
abuse, ideally at low/no cost given the project runs on an Oracle Free Tier VM.

## Decision

Route all traffic through Cloudflare: DNS, HTTPS/TLS termination, CDN caching
for the static site, and basic WAF/edge protection.

## Alternatives considered

- **Cloud-provider-native CDN (e.g. AWS CloudFront)** — ties the edge layer to
  one cloud, working against the multi-cloud goal, and doesn't natively cover
  a single-VM Oracle origin as cleanly.
- **No CDN/edge layer, direct-to-VM** — exposes the origin VM directly to the
  internet with no caching or basic attack mitigation.

## Trade-offs

Gain: free tier covers this use case fully, cloud-agnostic edge layer fits
the multi-cloud architecture, meaningful caching for the static site.
Give up: another vendor/config surface to manage and document.

## Interview angle

"Cloudflare sits in front of every subdomain regardless of which cloud serves
it, which keeps the edge layer decoupled from the multi-cloud backend — a
cloud migration behind it wouldn't require a DNS/TLS change."
