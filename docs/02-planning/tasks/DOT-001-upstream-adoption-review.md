---
id: DOT-001
title: Complete upstream adoption and security boundary review
status: in_progress
priority: high
owner: owner
reviewer: codex
module: upstream
task_type: discovery
source_refs:
  - README.md
  - SECURITY.md
  - docs/SETUP.md
  - package.json
  - docs/00-start-here.md
created: 2026-10-04
updated: 2026-10-04
---

# DOT-001 Complete Upstream Adoption And Security Boundary Review

## Summary

Review the pinned OpenDots base before treating any included feature as part of
the new product. Identify inherited components, license obligations, trust
boundaries, multi-user gaps, and upstream-sync risks.

## Scope

- In: upstream code/docs/license/workflow inventory, dependency audit,
  authentication and owner scoping, computer isolation, persistence, voice,
  Slack, and learning integrations.
- Out: production hardening, deployment, dependency upgrades, model-provider
  implementation, and claims that this review is a security audit.

## Acceptance Criteria

- [ ] Record the exact upstream commit and license in the decision log.
- [ ] Map upstream modules to keep, adapt, replace, or defer.
- [ ] Identify every single-owner or shared-service assumption relevant to a
  multi-user product.
- [ ] Review workflows, dependency advisories, secrets, and SECURITY policy;
  record access-limited checks honestly.
- [ ] Record upstream update/merge policy and verify no private Context Kit
  files are tracked.
- [ ] Produce a security/architecture gap list that feeds DOT-003 through
  DOT-007.

## Evidence So Far

- Base commit: `c2569bb6a13a22e565cf3eb791c62267d06babb1`.
- Upstream `LICENSE` identifies MIT.
- Upstream `SECURITY.md` states the template is under development, not audited,
  and local prototype is single-owner.
- `docs/SETUP.md` says the Slack path maps permitted users to one owner and the
  template does not include multi-user page sharing.
- `npm audit --package-lock-only --audit-level=high` returned zero known npm
  vulnerabilities on 2026-10-04; dependencies were not installed.
- The upstream CI workflow has `contents: read` and runs checkout, npm checks,
  tests, and build. GitHub Dependabot alerts could not be read: current token
  returned HTTP 403 because it lacks the required scope.
- The project-local context health check passed after its security smoke
  refresh. This is not a full code audit or provider approval.

## Validation

- [x] Exact upstream commit recorded.
- [x] License and security policy read.
- [x] Lockfile-level npm audit completed without installing packages.
- [x] CI workflow reviewed.
- [ ] Source-level authorization and computer sandbox review completed.
- [ ] GitHub alerts checked by an authorized maintainer.
- [ ] Keep/adapt/replace decision reviewed by owner.
