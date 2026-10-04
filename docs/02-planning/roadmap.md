# Product Roadmap

This is a gated roadmap, not a promise of delivery dates. Do not skip a gate
because the upstream template already contains a similarly named feature.

## Phase 0 — Fork And Discovery

**Goal:** establish what is inherited, what is desired, and what must change.

- Review the upstream commit, architecture, license, SECURITY policy, release
  history, dependency surface, workflows, and current single-owner assumptions.
- Select the first user workflow, product name, initial deployment mode, and
  success criteria.
- Confirm the policy and technical path for each candidate model provider.
- Record the source commit and a deliberate upstream-sync policy.

**Exit gate:** approved requirements, risk register, provider eligibility
matrix, and first architecture decisions. No external users or production
data.

## Phase 1 — Architecture And Security Foundation

**Goal:** define stable contracts before building product-specific features.

- Decide identity, tenant, user, Dot, conversation, memory, credential, task,
  and device ownership boundaries.
- Decide whether CopilotKit Intelligence remains, is replaced, or is isolated
  behind a persistence adapter.
- Specify provider adapters for ChatGPT-plan OAuth, API-key usage, other
  provider-supported auth, and local inference.
- Design approval levels, audit records, secret storage, retention, deletion,
  and tool execution isolation.
- Compare local, AWS, and managed-container hosting against measured needs.

**Exit gate:** reviewed architecture/ADRs, threat model, data lifecycle, cost
model, and test plan. No multi-user deployment until tenant isolation is
implemented and tested.

## Phase 2 — Single-Owner Vertical Slice

**Goal:** deliver one useful, low-risk workflow for the owner.

- One user, one Dot, one selected workflow, and one or two explicitly supported
  model routes.
- Durable conversation and editable memory with export/delete support.
- One permissioned app-owned tool, activity history, and confirmation for
  side effects.
- Clear provider/model selection, failure states, quotas, and disconnect flow.

**Exit gate:** end-to-end acceptance tests pass; no simulated provider success;
live routes are independently verified and clearly labeled.

## Phase 3 — Personal Device Companion

**Goal:** bridge hosted or local orchestration to the owner's computer without
granting the cloud unrestricted host access.

- Define enrollment, device identity, outbound connection, revocation, update,
  health, and supported operating systems.
- Start with a narrow capability set such as read-only browser navigation or
  selected workspace files.
- Use per-device scopes, isolated task execution, explicit approval, and
  visible action receipts.

**Exit gate:** threat model and abuse tests pass; device can be disconnected
and its credentials revoked; actions are independently reviewable.

## Phase 4 — Multi-User Private Pilot

**Goal:** admit a small set of invited users without sharing state or authority.

- Add verified authentication, tenant membership, role/ownership checks, and
  per-tenant provider credential storage.
- Isolate memory, Dots, conversations, files, jobs, channels, and device
  connections; test every cross-tenant boundary.
- Add account export/deletion, audit review, backups, restoration tests, and
  incident runbooks.

**Exit gate:** independent security review and cross-tenant test suite pass;
provider terms and any hosted plan-sharing access are confirmed.

## Phase 5 — Hosted Product Readiness

**Goal:** determine whether and how to offer a supported product to others.

- Select hosting region and platform based on workload and cost evidence.
- Add observability, support path, usage controls, cost attribution, release
  rollback, abuse response, and privacy/legal materials.
- Resolve provider approvals, licensing, terms, data retention, and commercial
  obligations.

**Exit gate:** owner explicitly authorizes launch after operational, security,
provider, legal, and cost reviews. No launch commitment is made by this plan.
