# ADR-001: Static-first Next.js for the public site

**Status:** Accepted
**Date:** 2026-08-10

## Context

The public site is the primary artifact recruiters will see. It needs to load
fast, rank well in search, stay cheap to host, and survive traffic spikes
(e.g. a link shared on LinkedIn) without extra ops effort.

## Decision

Build the public site with Next.js (App Router), statically generated where
possible. Content that changes often (projects, blog posts) is fetched at
build/publish time from the API rather than rendered per-request.

## Alternatives considered

- **Full SSR on every request** — unnecessary load and latency for content
  that changes at most a few times a week.
- **Plain static site generator (Hugo/Astro) with no dynamic layer at all** —
  would force manual rebuilds/edits for every project or blog update,
  contradicting the admin-portal goal.
- **Client-side rendered SPA** — worse SEO, worse first paint.

## Trade-offs

Gain: speed, cheap Cloudflare caching, strong SEO, high reliability.
Give up: true real-time updates — publishing a change requires a rebuild or
on-demand revalidation, not instant reflection. Acceptable for a portfolio.

## Interview angle

"I chose static-first because 95% of this site's content changes infrequently
— treating it as SSR-by-default would have added latency and hosting cost for
no benefit. The dynamic 5% is isolated to an admin-triggered publish step."
