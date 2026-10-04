# Provider And Authentication Strategy

Status: research baseline, not implementation or provider approval.

## OpenAI ChatGPT Plan

OpenAI now documents **Sign in with ChatGPT** with a separate optional consent
for eligible Plus/Pro users to make supported Responses API requests using
their ChatGPT plan. This is not ordinary identity-only login and does not give
the app access to ChatGPT conversations or memories.

- OpenAI documents plan usage for open-source apps and local personal
  projects. Offering a paid or remotely hosted app to users has an interest-
  form/availability gate; it must not be assumed approved.
- A self-hosted VM route exists for an open-source app, but current docs note
  transferred sessions do not yet have host-specific usage attribution or
  revocation.
- Inference uses the public Responses API, account-authorized model catalog,
  `store: false`, and `stream: true`; send required conversation context with
  each request. Never call private ChatGPT backend endpoints.
- Custom/function tools can be supplied by the app, but this flow does not
  include OpenAI-hosted native computer use, hosted MCP/connectors, file
  search, Code Interpreter, image generation, or audio/video input and
  transcription.
- OpenAI Realtime voice used by the current OpenDots template is separate from
  this plan-sharing route and currently expects a separate API credential.
- Eligible plan usage is limited/shared with the user's other participating
  apps. It is not a free, unlimited, separate model pool. Per-app usage limits
  and any credit permission must be surfaced to the user.

Primary sources:

- [OpenAI Sign in with ChatGPT quickstart](https://developers.openai.com/siwc/quickstart)
- [Open-source app integration cookbook](https://developers.openai.com/cookbook/articles/sign-in-with-chatgpt)
- [OpenAI plan usage overview](https://developers.openai.com/siwc/token-sharing-open-source)
- [Models and inference](https://developers.openai.com/siwc/token-sharing-open-source/models-and-inference)
- [Preview limitations](https://developers.openai.com/siwc/token-sharing-open-source/preview-limitations)
- [Accounts, sessions, and token protection](https://developers.openai.com/siwc/token-sharing-open-source/profiles-and-sessions)
- [Self-hosted VM flow](https://developers.openai.com/siwc/token-sharing-open-source/self-hosted-vms)
- [OpenDots setup and voice configuration](https://github.com/CopilotKit/OpenDots/blob/main/docs/SETUP.md)

## Provider Adapter Model

The product should distinguish:

1. **ChatGPT-plan OAuth:** only where the official integration supports the
   app and deployment model. Store refresh credentials in protected
   server-side or OS-secure storage; refresh, revoke, and disclose usage.
2. **API-key / BYOK:** key belongs to an individual user or organization,
   stored encrypted and scoped to that provider. Do not expose it to browser
   code or a Dot prompt.
3. **Operator-managed provider:** if later offered, isolate credentials,
   enforce per-user quotas, attribute costs, and disclose data processing.
4. **Local inference:** connect to an explicitly configured local service or
   separately isolated cloud inference worker. Define network and data
   boundaries for each.

Each provider connection should expose capability metadata (models, streaming,
tools, vision, audio, context size, and deployment constraints) and report
unsupported features. A provider failure must stop or ask the user; it must not
silently use another paid credential.

## Open Items

- Confirm ChatGPT-plan access eligibility for private remote self-hosting and
  any future commercial offering before designing the product's hosted default.
- Verify how TanStack AI's current OpenAI adapter speaks to the Responses API;
  decide between a maintained provider adapter and an official Codex
  app-server backend.
- Test OAuth scopes, model discovery, streaming completion, tool-call round
  trips, refresh races, account switching, revocation, usage-limit failures,
  and sensitive-token redaction.
- Verify separate auth policies for Claude, Gemini, and any other provider.
  Do not infer that a subscription login may be reused in a third-party app.
- Decide whether local models run on user devices or operator-managed GPU
  infrastructure; these are different products and cost models.
