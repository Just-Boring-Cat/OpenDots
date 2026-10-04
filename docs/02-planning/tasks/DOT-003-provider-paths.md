---
id: DOT-003
title: Validate provider and ChatGPT-plan routes
status: planned
priority: high
owner: owner
reviewer: codex
module: providers
task_type: integration-discovery
source_refs:
  - docs/03-architecture/provider-auth.md
created: 2026-10-04
updated: 2026-10-04
---

# DOT-003 Validate Provider And ChatGPT-Plan Routes

## Summary

Select a policy-compliant model connection strategy and verify it with a
minimal local prototype before changing the product runtime.

## Acceptance Criteria

- [ ] Confirm the OpenAI Sign in with ChatGPT route for the exact intended
  deployment; submit an interest form if required for hosted/commercial use.
- [ ] Define OAuth token storage, renewal, disconnect, account switching, and
  per-app usage-limit UX.
- [ ] Prove model listing and streamed inference with the account's authorized
  catalog; do not infer entitlement from a static model list.
- [ ] Prove one app-owned custom tool round trip through the selected runtime.
- [ ] Confirm the desired Anthropic, Google, and local routes through their own
  documented auth/API mechanisms.
- [ ] Record costs and features not covered by a ChatGPT plan, including voice
  and persistence services.

## Guardrails

- Never reuse Codex CLI, ChatGPT desktop, or browser session files.
- Never call private ChatGPT backend endpoints.
- Never silently switch to a paid API key or another provider after an OAuth
  route fails.
