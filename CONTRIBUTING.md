# Contributing to ndrorchestration repositories

Thank you for contributing. This file is an account-level default for repositories that do not define a local `CONTRIBUTING.md`. A repository-local contribution guide overrides this default.

## Start with the target repository

Before proposing a change:

1. Read the target repository's README, current-status/evidence documentation, and local contribution or governance files.
2. Check open issues and pull requests to avoid duplicating active work.
3. Treat that repository as authoritative for its own implementation, tests, deployment state, evidence, and project-specific status.
4. Do not transfer validation, certification, security status, authorization, or empirical claims from another repository merely because code or patterns are reused.

For DGAF/PDMAL governance or scientific-state questions, `ndrorchestration/DGAF-Framework` is the project-local authority. This `.github` repository provides shared defaults only.

## Change requirements

A pull request should state:

- what changed and why;
- the exact validation actually performed;
- what remains untested, unverified, blocked, or outside scope;
- whether documentation or public-facing claims changed;
- whether the change depends on another repository, deployment, secret, external service, or administrator action.

Use the ecosystem evidence vocabulary where useful:

`DEFINED → IMPLEMENTED → COMPUTED → VERIFIED → ATTESTED → HISTORICAL → HYPOTHESIS → METAPHOR → UNSUPPORTED → DEPRECATED`

A passing test establishes only the property exercised under that test environment. It does not by itself establish certification, production readiness, security assurance, authorization, factual correctness, or empirical efficacy.

## Verification

Prefer the target repository's documented test and lint commands. When a repository has CI, keep local verification aligned with the authoritative CI path.

Do not mark a check as passing unless it actually ran and passed on the revision being described. Missing, skipped, blocked, or unavailable checks must remain explicit.

## Documentation and provenance

When changing behavior, update the documentation that claims that behavior. Preserve historical records when they provide provenance; do not silently rewrite old evidence into current state.

Prefer references to canonical state over copying mutable status into multiple repositories.

## Sensitive information

Never commit API keys, tokens, credentials, private personal data, or confidential operational material. Remove secrets from logs and reproduction artifacts before attaching them to issues or pull requests.

Security vulnerabilities should follow the applicable `SECURITY.md` rather than being disclosed in a public issue.
