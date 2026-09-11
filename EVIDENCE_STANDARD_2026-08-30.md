# Ecosystem Evidence Standard — 2026-08-30

Across the `ndrorchestration` ecosystem, project-local terminology, CI, deployment, benchmarks, governance mappings, implementation claims, and historical records must not be promoted beyond the evidence actually produced.

This file defines shared vocabulary and anti-overclaim rules. It is **not** a global registry of current project state.

## Evidence vocabulary

`DEFINED → IMPLEMENTED → COMPUTED → VERIFIED → ATTESTED → HISTORICAL → HYPOTHESIS → METAPHOR → UNSUPPORTED → DEPRECATED`

Use these terms only when their repository-local evidence supports them. They are descriptive evidence labels, not automatic promotion gates shared across every project.

## Core rules

- CI proves only the checks executed on the revision actually tested.
- A skipped, missing, blocked, cancelled, or unavailable check is not PASS.
- Deployment proves deployment existence, not correctness, factual accuracy, security, or production readiness.
- Runtime verification does not equal empirical efficacy.
- A benchmark specification is not benchmark validation.
- A numerical target is not an observed result.
- An exported provenance record is not automatically an independent attestation.
- External-framework mappings are not certification without applicable requirements and evidence.
- Validation, authorization, deployment status, security status, and empirical results do not transfer between repositories through shared code, templates, terminology, or architecture patterns.

## Current versus historical authority

Historical records remain valuable provenance and should not be silently rewritten merely because current terminology or state has changed.

When historical material conflicts with a newer project-local authority surface:

1. preserve the historical record when it is legitimate provenance;
2. label its event-time or superseded scope where ambiguity is material;
3. point current readers to the newer authoritative surface;
4. do not promote a historical PASS, VERIFIED, authorized, deployed, or canonical label into current state without fresh evidence.

Repository age, file age, or a current-looking filename does not by itself establish authority.

## Cross-repository reuse

Shared patterns are implementation inputs, not evidence transfer mechanisms.

If repository B reuses code, policy language, a test helper, workflow, or architecture pattern from repository A, repository B must still establish its own applicable verification and claims. Conversely, a failure or unresolved state in one repository should not be projected onto another unless there is an explicit dependency that makes the result applicable.

For DGAF/PDMAL, `ndrorchestration/DGAF-Framework` retains its own governance and scientific-state authority. Other repositories may reuse patterns without inheriting DGAF authorization or evidence state.

## Security and privacy

Passing static analysis, dependency checks, unit tests, or code review does not establish comprehensive security. Never treat absence of a known issue as proof that no issue exists.

Secrets, credentials, private personal data, and confidential operational material are not acceptable evidence artifacts in public issues or repositories. Preserve provenance without exposing sensitive material.

_Last refreshed 2026-09-10._
