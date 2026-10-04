# Security Status

Last bounded review: 2026-10-04. This is an initial repository/dependency
check, not a penetration test, code audit, or production certification.

## Evidence

- Upstream `SECURITY.md` says OpenDots is an unaudited application template
  and its local prototype is single-owner.
- The upstream setup guide says the Slack mapping is not a multi-user identity
  model and that multi-user page sharing is not included.
- `npm audit --package-lock-only --audit-level=high` reported zero known npm
  vulnerabilities for the checked lockfile. No dependencies were installed.
- The only upstream GitHub Actions workflow reviewed has `contents: read` and
  runs checkout, format/lint/typecheck/tests/build.
- The GitHub Dependabot alerts API could not be queried with the current CLI
  token (HTTP 403; required token scope unavailable). This is unknown, not a
  clean-alert result.
- Context Kit health check passed for the local development clone. Its
  security marker and Context Kit checkout are ignored and must not be
  published.

## Required Before Wider Use

- Complete DOT-001 source-level review of authorization, data boundaries,
  computer isolation, dependency scripts, and CI trust.
- Re-run npm and GitHub advisory checks before dependency installation or
  upgrades.
- Complete DOT-006 tenant threat model and cross-tenant tests before inviting
  another user.
- Complete DOT-005 local-device threat model before connecting a real PC.
- Keep provider tokens and owner data out of public issues, PRs, screenshots,
  logs, and planning docs.
- Enable and verify private vulnerability reporting on the fork before
  inviting external contributors.
