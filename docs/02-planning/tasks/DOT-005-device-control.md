---
id: DOT-005
title: Design local-device and isolated-computer control
status: planned
priority: high
owner: owner
reviewer: codex
module: device-agent
task_type: security-architecture
source_refs:
  - docs/03-architecture/architecture-options.md
  - SECURITY.md
created: 2026-10-04
updated: 2026-10-04
---

# DOT-005 Design Local-Device And Isolated-Computer Control

## Summary

Define how a hosted or local Dot can use a user's computer, a managed browser,
or an isolated cloud computer without confusing those trust boundaries.

## Acceptance Criteria

- [ ] Distinguish user's actual device from per-Dot remote computer containers.
- [ ] Define local companion identity, pairing, outbound connectivity, scoped
  capabilities, revocation, updates, and health.
- [ ] Define permissions for browser, files, shell, microphone, and OS actions.
- [ ] Require user confirmation for external side effects and keep an auditable
  action receipt.
- [ ] Add prompt-injection defenses for pages, email, files, and tool output.
- [ ] Validate isolation with tests before enabling a real device connection.
