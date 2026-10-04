# Definition Of Done

## Product Work

- The change maps to an accepted requirement and task card.
- Product-visible behavior is implemented, documented, and tested for loading,
  success, failure, empty, denied, disconnected, and recovery states as
  applicable.
- Model, provider, tool, and background-job success are based on terminal
  completion evidence, not a configured key or queued request.
- External side effects follow the recorded approval policy and create an
  inspectable receipt.

## Security And Privacy

- Authorization is enforced server-side for every user/tenant-owned record and
  tool call.
- Untrusted external and model-generated content cannot override instructions,
  grant permissions, or change identity.
- Secrets are not returned to the client, written into logs, or copied into
  source control; disconnect/revocation behavior is verified.
- Tenant boundary, retention, export/delete, backup, and audit behavior are
  tested for data-affecting changes.
- Computer and local-device permissions are scoped, visible, revocable, and
  exercised in an isolated test environment.

## Validation And Release

- Relevant unit/integration tests, lint, typecheck, format check, and build run
  successfully, or limitations are recorded.
- Live provider/deployment checks are separately identified from fixtures and
  local tests.
- Public changes pass secret, local-resource, dependency, and workflow review.
- Docs, task status, changelog, and decision records are updated.
- No feature is called production-ready before its acceptance gate and owner
  review pass.
