---
id: DOT-006
title: Define multi-user identity and tenant threat model
status: planned
priority: high
owner: owner
reviewer: codex
module: identity
task_type: security-architecture
source_refs:
  - docs/01-product/requirements.md
  - docs/02-planning/roadmap.md
  - SECURITY.md
created: 2026-10-04
updated: 2026-10-04
---

# DOT-006 Define Multi-User Identity And Tenant Threat Model

## Summary

Define who owns every object and credential, how users are invited, and how
each request is authorized before exposing a second account to the product.

## Acceptance Criteria

- [ ] Define user, tenant, membership, role, Dot, conversation, data, job,
  credential, and device ownership.
- [ ] Choose an identity provider and secure invite/recovery lifecycle.
- [ ] Define tenant-scoped database access and background-job identity.
- [ ] Threat-model cross-tenant reads/writes, confused deputy behavior, prompt
  injection, provider-token theft, and malicious Dot instructions.
- [ ] Specify automated cross-tenant deny tests and independent review gates.
- [ ] No multi-user release until all tests pass and owner accepts the review.
