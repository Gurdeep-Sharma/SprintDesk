# Security Policy

## Scope

SprintDesk is a work-in-progress learning project. Do not assume that an unreviewed or undeployed feature is production-ready.

## Reporting a vulnerability

Please avoid posting exploitable vulnerability details in a public issue. Before making the repository public, add a maintainer-controlled contact method for private vulnerability reports. Do not include credentials, personal data, access tokens, or live exploit instructions in public discussions.

## Security expectations

- Never commit real secrets or production credentials.
- Use placeholder values in `.env.example`.
- Validate all untrusted input at runtime.
- Enforce authorization on the backend.
- Use secure password storage and deliberate token handling.
- Avoid logging sensitive data.
- Keep dependencies updated and review security advisories.
- Test unauthorized access and cross-workspace access attempts.
- Treat user-provided content as untrusted.

## Disclosure

Coordinate fixes and disclosure with the repository maintainer. Do not publish private user data or credentials as part of a report.
