---
id: DOT-004
title: Choose conversation and memory persistence boundary
status: planned
priority: high
owner: owner
reviewer: codex
module: data
task_type: architecture
source_refs:
  - docs/03-architecture/architecture-options.md
  - docs/01-product/requirements.md
created: 2026-10-04
updated: 2026-10-04
---

# DOT-004 Choose Conversation And Memory Persistence Boundary

## Summary

Decide whether to retain CopilotKit Intelligence for conversation threads,
replace it, or put it behind an adapter while adopting a product-owned data
store.

## Acceptance Criteria

- [ ] Compare managed and self-hosted persistence, including licensing,
  pricing, data location, backups, export, deletion, and portability.
- [ ] Define separate schemas/lifecycles for conversations, explicit memories,
  activity receipts, files, and provider credentials.
- [ ] Define per-user and per-tenant access filters and deletion semantics.
- [ ] Ensure model-provider conversation retention is not confused with the
  product's own conversation store.
- [ ] Record the decision and migration path in an ADR.
