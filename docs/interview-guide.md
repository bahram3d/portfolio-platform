# Interview guide

A running log of "why did you build it this way" answers, captured as
decisions are made rather than reconstructed after the fact. Each entry
links back to its ADR for full detail.

## Format

**Q: Why did you choose X?**
A: One or two sentences, interview-ready.
→ See ADR-NNN for full reasoning.

## Entries

**Q: Why static-first instead of full SSR?**
A: Most content changes infrequently; static gets speed, SEO, and cheap
caching for the 95% case, with a publish-triggered rebuild handling the rest.
→ See ADR-001.

**Q: Why didn't you use Kubernetes?**
A: Five containers on one VM don't need a scheduler and control plane —
adding it would be complexity for appearances, not need.
→ See ADR-007.

(More entries added as each phase completes.)
