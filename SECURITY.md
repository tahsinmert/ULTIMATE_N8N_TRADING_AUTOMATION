# Security Policy

## Supported versions

This repository currently tracks the latest version on `main`.

## Reporting a vulnerability

If you discover a security issue, do not open a public issue. Instead, report it privately to the repository owner.

Include:

- What the issue is
- Why it matters
- How it can be reproduced
- Any recommended mitigation

## High-risk areas

- API credentials and webhook payloads
- Order execution logic
- Telegram notification configuration
- Any change that could trigger live trades unexpectedly

## Safe handling guidance

- Test with dummy payloads first.
- Use restricted API permissions.
- Keep secrets out of the repository.
- Review every automation path before enabling live execution.
