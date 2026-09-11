# ndrorchestration/.github

Account-level profile, community-health defaults, and evidence conventions for the `ndrorchestration` GitHub ecosystem.

## What this repository does

This repository provides shared defaults for repositories owned by `ndrorchestration` when a target repository does not define its own equivalent file. Repository-local files and project-specific governance remain authoritative for that repository.

Shared surfaces include:

- `CONTRIBUTING.md` — default contribution and verification expectations;
- `SECURITY.md` — default vulnerability-reporting and security-claim boundary;
- `SUPPORT.md` — default support and authority routing;
- `.github/pull_request_template.md` — evidence-aware pull request checklist;
- `.github/ISSUE_TEMPLATE/` — structured bug and feature intake;
- `EVIDENCE_STANDARD_2026-08-30.md` — common evidence vocabulary and anti-overclaim rules;
- `profile/` — account profile material.

## Authority boundary

This repository is a **support plane**, not an ecosystem-wide mutable status registry.

Each project remains authoritative for its own implementation, CI results, deployment state, tests, evidence, and project-specific status. A local contribution guide, security policy, support file, issue template, or PR template overrides the corresponding account-level default for that repository.

`ndrorchestration/DGAF-Framework` remains authoritative only for DGAF/PDMAL governance, experiment authorization, and scientific-state claims. Reusing a DGAF pattern, workflow idea, terminology rule, or helper does not import DGAF evidence state into another project.

Portfolio role, lifecycle, relationship, and disposition are maintained in the ecosystem's Notion classification layer rather than duplicated here as moving state.

## Evidence boundary

Current-facing claims must remain evidence-bounded and must not transfer certification, production readiness, security status, deployment verification, governance authorization, or empirical status between projects.

A passing test proves only the property exercised under that test environment. A deployment proves deployment existence, not correctness. A shared template or workflow proves no project-specific claim by itself.

See `EVIDENCE_STANDARD_2026-08-30.md` for the shared vocabulary and claim rules.

## Workflow reuse

GitHub Actions workflows are not treated as automatically inherited project authority. Reusable workflows may live here only when multiple repositories demonstrate materially identical deterministic validation needs, and caller repositories must opt in explicitly. Project-specific scientific, security, deployment, or authorization decisions remain local.

## Historical and external repositories

Historical archives and external forks are preserved as provenance/upstream records. Shared defaults do not reactivate them as first-party current projects or transfer upstream claims to `ndrorchestration`.
