# Product Vision

## Direction

Build a personal AI assistant workspace that can grow from one owner's useful,
supervised assistant into a secure product for multiple independent users. A
user can create named agents (“Dots”) with different responsibilities, connect
approved models and tools, and ask them to help across projects and everyday
work. The long-term aspiration includes a persistent assistant that can work
with the user's computer, communications, files, and services, with the user
retaining clear control over access and consequential actions.

The present repository is a starting codebase, not that finished product. The
first release must prove one narrow end-to-end workflow before broad personal
automation is attempted.

## Product Principles

- **A separate product:** this project is not Agent Harllens and is not part of
  the Agent Context Kit repository. Do not import their runtime, personal
  memories, private instructions, or roadmaps into this fork.
- **Useful without Context Kit:** the application can run standalone. A user
  may opt into a Context Kit connector/profile to supply selected skills and
  project standards; that integration is replaceable and never required for
  core operation.
- **Provider choice:** support provider-authorized sign-in, user-supplied API
  credentials where appropriate, and local model endpoints. Use only provider
  documented integrations. Do not extract or reuse credentials from another
  product's private session files or bypass provider eligibility rules.
- **Personal first, multi-user by design:** prove the first workflow with one
  owner, but design identity, storage, tools, and compute with tenant boundaries
  before admitting additional users.
- **Local device access is explicit:** a hosted service cannot directly see or
  control a user's computer. Any such capability needs a user-installed local
  companion or an explicitly provisioned isolated remote computer, with
  scoped permissions and a visible connection state.
- **Supervised autonomy:** start with read, summarize, and draft actions. Require
  explicit confirmation for externally visible, financial, destructive, or
  hard-to-reverse actions. Record what was proposed, approved, and executed.
- **Learning is inspectable:** persist user-approved preferences, memories, and
  task outcomes as editable data with source and deletion controls. Do not
  imply that the model is fine-tuned or silently trained on user activity.
- **Privacy and portability:** users need understandable data boundaries,
  export and deletion paths, and the ability to choose where inference occurs.

## Intended Users

- The owner using a private personal assistant across work and personal
  projects.
- Later, invited individual users who each have isolated accounts, agents,
  credentials, memories, files, and device connections.
- Potential future customers if the owner chooses to commercialize the product
  after security, provider-policy, licensing, support, and operating-cost gates.

These are future target groups, not current users or launch commitments.

## Initial Scope Hypothesis

The first product slice should use one account and one Dot to complete a
low-risk, repeatable workflow with a clear result and review step. Candidate
examples are project status gathering, research-to-draft, or a user-approved
local browser task. The owner has not selected the first workflow yet; do not
implement all email, tax, finance, or desktop automation at once.

The prototype should prove provider choice independently from tool execution:

1. Connect one supported hosted model route and one local-compatible route.
2. Maintain a durable conversation and user-editable memory.
3. Call one app-owned, permissioned tool and show its result in the activity
   history.
4. Ask for confirmation before any side effect.
5. Demonstrate that a user can disconnect the provider and delete the data.

Whether the first workflow is local-only or hosted must be decided before the
prototype architecture is locked.

## Not In Initial Scope

- Unrestricted autonomous computer or account access.
- Automatically sending emails, submitting forms, moving money, filing taxes,
  or changing production systems without review.
- Claiming OpenAI ChatGPT, Claude, Gemini, or other subscription usage is
  available to this app unless the provider explicitly supports the exact
  integration and deployment model.
- Training or fine-tuning a foundation model on user data.
- Public multi-tenant production hosting before the identity and isolation gates
  in the roadmap pass.
- Requiring the Agent Context Kit, Codex, CopilotKit Intelligence, or any single
  model vendor as the product's permanent runtime.
