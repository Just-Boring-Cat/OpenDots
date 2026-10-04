# Initial Requirements

Status: discovery baseline. Requirements below record the owner's direction;
items marked **open** need a decision before implementation.

## Product Requirements

| ID | Requirement | Priority | Status |
| --- | --- | --- | --- |
| PR-001 | Operate as a standalone product, separate from Agent Harllens and Agent Context Kit. | Must | Accepted direction |
| PR-002 | Let a user create and configure multiple named Dots with role-specific instructions and tool permissions. | Must | To validate against upstream |
| PR-003 | Keep Context Kit integration optional; provide no dependency on its private repo for product operation. | Must | Accepted direction |
| PR-004 | Support more than one model provider, including official hosted-provider routes and local model endpoints. | Must | Provider list open |
| PR-005 | Provide user-owned, reviewable persistent memory/preferences with provenance, edit, export, and deletion controls. | Must | Data model open |
| PR-006 | Support controlled interaction with a user's own computer through a separate, authenticated local component or isolated remote computer. | Must for vision | Architecture open |
| PR-007 | Separate users' identities, conversations, files, credentials, tools, scheduled jobs, and device connections. | Must before multi-user use | Security design required |
| PR-008 | Show tool activity and require confirmation for consequential external actions. | Must | Approval model open |
| PR-009 | Support an always-available hosted option only after provider eligibility, tenant isolation, cost, and operations are validated. | Should | Hosting open |
| PR-010 | Support a future commercial product path without assuming that upstream OpenDots is already suitable for that purpose. | Should | Product/legal review open |

## Quality And Security Requirements

- Authenticate every interactive and background request; never accept a client-
  supplied user or tenant ID as proof of identity.
- Enforce authorization at each server data/tool boundary, not only in UI
  navigation or agent instructions.
- Keep provider tokens, API keys, local companion secrets, and channel tokens
  out of browser storage, source control, logs, analytics, and model context.
- Encrypt secrets at rest with keys separated from the database; scope and
  rotate credentials; provide a revoke/disconnect path.
- Isolate browser, shell, file, and model-compute workloads by user and task.
- Treat web pages, email, uploaded files, screenshots, tool results, and model
  output as untrusted data. They cannot grant permissions or override system
  policy.
- Log action intent, authorization, execution result, and user-visible status
  without retaining unnecessary sensitive content.
- Define retention, export, account deletion, backup, restore, and incident
  response before any external pilot.
- Test cross-user access denial, stale/revoked credentials, interrupted tasks,
  and failure recovery before multi-user release.
- Keep the UI clear about which Dot, provider, connected device, permissions,
  and account are active.

## Open Product Decisions

1. Product name, public positioning, and whether the GitHub fork remains named
   `OpenDots` during development.
2. First low-risk workflow and its measurable acceptance criteria.
3. First supported deployment: local desktop, private hosted instance, or both.
4. Whether providers are configured per user, per Dot, or both.
5. Which other hosted providers are in scope for the first release.
6. Whether the first supported local model runs on the user's computer or on a
   separately provisioned GPU worker.
7. Which memory is automatic, which requires approval, and how it is reviewed.
8. Whether invited multi-user access is needed in the first pilot or a later
   phase.
9. Hosting region, expected concurrency, retention, recovery objectives, and
   monthly spending ceiling.
10. Commercial distribution, billing, support, and legal obligations.
