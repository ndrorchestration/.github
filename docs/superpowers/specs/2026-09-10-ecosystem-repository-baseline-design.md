# Ecosystem Repository Baseline — Design

Date: 2026-09-10
Status: Design approved in chat; implementation pending written-spec review
Owner: ndrorchestration

## Purpose

Create a lightweight, evidence-bounded repository baseline for the `ndrorchestration` ecosystem that reduces duplicated maintenance without falsely transferring validation, scientific state, security status, deployment status, or governance authority between repositories.

The baseline must work across primary projects, research projects, workstreams, support planes, component libraries, utilities, historical archives, and external forks. It must strengthen consistency without forcing DGAF-level governance onto unrelated or smaller repositories.

## Authority model

1. Each repository remains authoritative for its own implementation, CI results, deployment state, tests, evidence, and project-specific status.
2. Notion remains the portfolio/classification SSoT for repository role, lifecycle, relationship, and portfolio disposition.
3. `ndrorchestration/.github` supplies account-level defaults and reusable conventions only.
4. `DGAF-Framework` remains authoritative only for DGAF/PDMAL governance and scientific-state claims. No DGAF evidence state transfers to another repository by reuse of a pattern or workflow.
5. Historical and external-fork repositories are not silently modernized into active first-party projects.

## Design principles

- Fail closed on claims: do not infer stronger status than evidence establishes.
- Prefer inheritance or reuse over copy/paste when GitHub supports it.
- Prefer local override when a repository has materially different requirements.
- Preserve provenance and historical context instead of rewriting history.
- Make the smallest useful baseline; add stricter controls only when a repository's role warrants them.
- Do not require secrets, deployments, protected branches, or external services merely to satisfy the baseline.

## Baseline layers

### Layer A — account-level community defaults

The public `.github` repository will provide supported default community-health files for repositories that do not define local equivalents:

- `CONTRIBUTING.md`
- `SECURITY.md`
- `SUPPORT.md`
- `.github/pull_request_template.md`
- `.github/ISSUE_TEMPLATE/bug_report.yml`
- `.github/ISSUE_TEMPLATE/feature_request.yml`
- `.github/ISSUE_TEMPLATE/config.yml`

These defaults must explicitly preserve per-repository evidence boundaries. A contribution or passing check must not be described as certification, authorization, empirical efficacy, security assurance, or production readiness unless the target repository separately establishes that claim.

A code of conduct may be added later if public contribution volume warrants it; it is not required for this first baseline wave.

### Layer B — evidence standard

Refresh the existing ecosystem evidence standard without turning it into a global scientific-state registry. The standard defines vocabulary and anti-overclaim rules only.

Required concepts:

- distinguish specification, implementation, computation, verification, attestation, historical record, hypothesis, metaphor, unsupported claim, and deprecation;
- test/CI scope is limited to the checks actually executed;
- deployment existence is not correctness;
- runtime verification is not empirical efficacy;
- cross-repository reuse does not transfer evidence;
- historical artifacts cannot silently override newer project-local authority;
- external framework mappings are not certification without applicable requirements and evidence.

### Layer C — repository role profiles

The baseline uses four practical profiles derived from the Notion repository classification registry.

#### Research / primary project

Expected local surfaces where applicable:
- README with current status and explicit evidence boundary;
- tests and CI appropriate to implementation;
- architecture or design documentation for non-trivial systems;
- clear unimplemented/not-established claims;
- project-local provenance for materially important artifacts.

Examples in first wave: `agent-control-plane`, `Orbit-Driftwatch`.

#### Operational / support plane

Expected local surfaces:
- explicit upstream authority boundary;
- operational/historical records clearly separated from sovereign/current state;
- provenance or reliability checks where records are machine-consumed;
- no promotion of operational snapshots into scientific or governance authority.

Example in first wave: `dgaf-ops`.

#### Application / showcase

Expected local surfaces:
- reproducible local evaluation path;
- deployed-vs-local status separated;
- credential boundaries documented;
- security policy where attack surface or server-side credentials exist;
- accessibility/deployment claims remain bounded to evidence actually produced.

Example in first wave: `Orbit-Driftwatch`.

#### Archive / external fork

Expected behavior:
- preserve historical/upstream provenance;
- add a concise archive/fork status pointer when needed;
- do not spend modernization effort unless the repository is reactivated or intentionally forked for first-party development;
- do not imply ownership of upstream claims or validation.

## CI reuse model

GitHub default community-health files may inherit from the public `.github` repository when a target repository has no local equivalent. Workflows do not inherit automatically.

Therefore:

1. Existing repo-local workflows remain authoritative.
2. Reusable workflows may be introduced under `.github/workflows/` only for deterministic checks that are genuinely shared by multiple repositories.
3. Caller repositories must explicitly opt in using `uses:`.
4. Reusable workflow references should use an immutable commit SHA for high-assurance or governance-sensitive contexts; a maintained tag may be acceptable for lower-risk convenience workflows.
5. No shared workflow may claim project-specific scientific, security, deployment, or authorization status.

Initial reusable-workflow candidates should be limited to low-risk repository hygiene/evidence linting after the first-wave audits demonstrate repeated logic. No reusable workflow is required merely to complete the community baseline.

## First-wave repository treatment

### `ndrorchestration/.github`

Current state: minimal README, public-profile material, and ecosystem evidence standard. No shared contribution/security/support/issue/PR defaults are present.

First implementation:
- add the account-level community defaults;
- refresh the evidence standard and README to explain inheritance and override rules;
- keep the repository free of project-specific status claims.

### `ndrorchestration/agent-control-plane`

Current state: compact Python research project with source, tests, one Python CI workflow, and a strong README that already distinguishes implemented/verified boundaries from unimplemented production/security properties.

First treatment:
- preserve its local README/evidence language;
- inspect CI for dependency pinning, least permissions, deterministic test command, and supported Python range;
- inherit account-level community defaults unless a local override is justified;
- avoid importing DGAF-specific gates.

### `ndrorchestration/dgaf-ops`

Current state: private operational/support repository with many historical/session/orchestration records and one reliability/provenance workflow. README already states that `DGAF-Framework` owns current DGAF authority.

First treatment:
- preserve private operational role and historical provenance;
- validate that reliability/provenance CI is exact enough for machine-consumed records;
- identify mutable/current-looking operational files that need stronger historical/current labels rather than deleting them;
- inherit community defaults where useful, but keep current DGAF authority links repo-local.

### `ndrorchestration/Orbit-Driftwatch`

Current state: public showcase/application with architecture, security policy, deterministic tests, hosted-provider/retrieval path, CI, Pages workflow, and explicit unresolved deployment/admin gates.

First treatment:
- preserve its stronger local `SECURITY.md` override;
- inspect CI/Pages permissions, action pinning, package/test determinism, and credential boundary;
- identify root-level showcase artifacts whose purpose should be made explicit or relocated only if safe;
- inherit contribution/support/issue/PR defaults unless local application-specific guidance is warranted.

## Mutation policy

For each active first-party repository:

1. Read current main/default branch, README, workflows, project manifest, tests, and key docs.
2. Check open PRs/issues and avoid duplicating in-flight work.
3. Classify each proposed change as shared-baseline, repo-local, historical-only, or blocked/admin-only.
4. Create an isolated branch.
5. Make only evidence-supported changes.
6. Run or inspect available validation before opening a PR.
7. Open a PR with exact scope, evidence boundary, and unresolved blockers.
8. Do not merge until relevant checks are green; do not infer missing checks as PASS.

## Duplicate-work controls

Before creating a new policy, workflow, helper, or documentation surface:

- search the repository and `.github` baseline for an existing equivalent;
- check Notion role/relationship records for a superseding project or component library;
- prefer a link/reference over duplicated mutable state;
- where historical duplicates must remain, label authority and supersession explicitly;
- never create a second ecosystem-wide SSoT for repository classification outside Notion.

## Success criteria for wave 1

Wave 1 is successful when:

- `.github` contains a coherent, minimal community/evidence baseline;
- the three pilot repositories have evidence-backed audit findings mapped to that baseline;
- changes are proposed through isolated PRs rather than direct unreviewed main edits;
- no project-specific status has been promoted by inheritance;
- no historical or external-fork repository has been accidentally reactivated;
- repeated logic suitable for a reusable workflow is identified only from observed duplication, not speculation.

## Non-goals

This wave does not:

- impose DGAF governance on the entire ecosystem;
- configure repository-admin settings that are unavailable through the current integration;
- create or rotate secrets;
- certify security, production readiness, empirical efficacy, or standards compliance;
- delete branches or historical files solely because they look old;
- modernize external forks or archived repositories without an explicit reactivation decision.

## Follow-on waves

After wave 1, propagate by Notion portfolio decision:

1. `KEEP_ACTIVE` primary/research projects;
2. `KEEP_AS_WORKSTREAM` support/workstream/component/utility repositories;
3. `INVESTIGATE` repositories receive classification audits before implementation work;
4. `ARCHIVE` repositories receive only provenance/status corrections unless reactivated;
5. external forks remain separated from first-party product claims.
