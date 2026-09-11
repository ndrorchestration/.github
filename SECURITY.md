# Security Policy

This file is an account-level default for `ndrorchestration` repositories that do not define a local `SECURITY.md`. A repository-local security policy overrides this file.

## Reporting a vulnerability

Do not disclose suspected vulnerabilities, exploit details, credentials, tokens, private data, or sensitive operational information in a public issue.

If the target repository has GitHub private vulnerability reporting or Security Advisories enabled, use that private reporting path. Otherwise, use a private maintainer channel already provided by the target repository or GitHub account rather than publishing exploit details publicly.

Include, when safe to share:

- affected repository and exact revision or release;
- affected component or path;
- reproduction conditions;
- observed impact;
- minimal proof or logs with secrets removed;
- whether the issue requires credentials, deployment access, or a particular environment.

## Evidence boundary

A security fix, passing test, dependency scan, code review, or absence of known reports does **not** by itself establish security certification, production hardening, complete vulnerability coverage, or resistance to untested attack classes.

Security claims remain repository-local. Validation in one `ndrorchestration` repository does not transfer to another repository through shared code, templates, or architecture patterns.

For DGAF/PDMAL, current governance and scientific-state authority remains in `ndrorchestration/DGAF-Framework`; this policy does not change authorization state.

## Secrets

Never commit or attach live secrets. Rotate any credential believed to have been exposed using the appropriate provider controls; removing a secret from a later commit does not erase it from prior Git history or external caches.
