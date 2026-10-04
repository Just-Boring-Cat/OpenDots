---
id: DOT-007
title: Compare hosting and local-inference options
status: planned
priority: medium
owner: owner
reviewer: codex
module: hosting
task_type: architecture
source_refs:
  - docs/03-architecture/hosting-options.md
created: 2026-10-04
updated: 2026-10-04
---

# DOT-007 Compare Hosting And Local-Inference Options

## Summary

Choose a deployment path only after the first workflow, data boundary, device
control model, and expected model workload are known.

## Acceptance Criteria

- [ ] Compare local-only, private single-owner cloud, and multi-tenant hosted
  operation.
- [ ] Compare AWS and at least one managed-container alternative on EU region,
  security controls, operational burden, persistent workers, GPU support,
  cost visibility, and exit/portability.
- [ ] Separate app/control-plane compute from per-user computer workers and
  GPU-backed model inference.
- [ ] Estimate idle and active monthly costs using a representative workload;
  identify GPU shutdown/scale-to-zero behavior.
- [ ] Record a reversible first deployment decision and rollback/backup plan.
