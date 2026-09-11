# Ecosystem Repository Baseline Wave 1 Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Establish a lightweight shared repository baseline in `ndrorchestration/.github`, then apply evidence-backed repository-specific corrections to `agent-control-plane`, `dgaf-ops`, and `Orbit-Driftwatch` without transferring project status or authority across repositories.

**Architecture:** `ndrorchestration/.github` supplies community-health defaults and evidence conventions only. Each target repository remains authoritative for its own implementation, CI, deployment, evidence, and status; repo-local workflows remain local unless repeated logic justifies an explicitly called reusable workflow.

**Tech Stack:** GitHub repository community-health files, GitHub Actions YAML, Markdown, Python/pytest (`agent-control-plane`), repository-local provenance checks (`dgaf-ops`), Node/npm tests and GitHub Pages (`Orbit-Driftwatch`).

**Spec:** `docs/superpowers/specs/2026-09-10-ecosystem-repository-baseline-design.md`

## Global Constraints

- Notion remains the portfolio/classification SSoT for repository role, lifecycle, relationship, and portfolio disposition.
- Each repository remains authoritative for its own implementation, CI results, deployment state, tests, evidence, and project-specific status.
- `DGAF-Framework` remains authoritative only for DGAF/PDMAL governance and scientific-state claims.
- Cross-repository reuse must not transfer validation, certification, security status, deployment status, authorization, or empirical efficacy.
- Historical and external-fork repositories are not reactivated by this wave.
- Existing repo-local workflows remain authoritative; reusable workflows require explicit opt-in.
- No merge occurs until relevant checks are green; missing checks are not inferred as PASS.
- No secrets, deployment-admin changes, branch-protection changes, or historical deletions are required by this wave.

---

## File Structure

Shared baseline in `ndrorchestration/.github`:
- `README.md` — explain account-level defaults, override behavior, evidence boundary, and role of this repository.
- `EVIDENCE_STANDARD_2026-08-30.md` — refresh shared vocabulary and anti-overclaim rules without becoming a status registry.
- `CONTRIBUTING.md` — default contribution/evidence expectations.
- `SECURITY.md` — default reporting and evidence-bound security language.
- `SUPPORT.md` — default support routing and project-local authority rule.
- `.github/pull_request_template.md` — default PR evidence checklist.
- `.github/ISSUE_TEMPLATE/bug_report.yml` — structured reproducibility-focused bug report.
- `.github/ISSUE_TEMPLATE/feature_request.yml` — structured feature proposal with evidence boundary.
- `.github/ISSUE_TEMPLATE/config.yml` — disable blank issues and route to templates.

Pilot repositories:
- `agent-control-plane/.github/workflows/test.yml` — tighten permissions/runtime determinism only if audit supports it.
- `dgaf-ops/.github/workflows/reliability-provenance.yml` and/or operational docs — make exact authority/provenance boundaries explicit only where current checks are insufficient.
- `Orbit-Driftwatch/.github/workflows/ci.yml`, `.github/workflows/pages.yml`, package/test/docs surfaces — strengthen only evidence-backed gaps; preserve local `SECURITY.md`.

---

### Task 1: Shared Community and Evidence Baseline

**Files:**
- Create: `CONTRIBUTING.md`
- Create: `SECURITY.md`
- Create: `SUPPORT.md`
- Create: `.github/pull_request_template.md`
- Create: `.github/ISSUE_TEMPLATE/bug_report.yml`
- Create: `.github/ISSUE_TEMPLATE/feature_request.yml`
- Create: `.github/ISSUE_TEMPLATE/config.yml`
- Modify: `README.md`
- Modify: `EVIDENCE_STANDARD_2026-08-30.md`

**Interfaces:**
- Consumes: approved design spec.
- Produces: repository-default community-health/evidence conventions inherited only when target repositories do not define local equivalents.

- [ ] **Step 1: Confirm the baseline files do not already exist on the implementation branch.**

Read each intended path. Existing files must be reviewed rather than overwritten by assumption.

- [ ] **Step 2: Add default contribution/security/support files.**

Required contribution language: contributors describe what changed, how it was tested, what remains unverified, and whether the change affects public claims. A passing check must not be described as certification, authorization, empirical efficacy, production readiness, or security assurance without separate evidence.

Required security language: report suspected vulnerabilities privately through GitHub's supported security-reporting path when enabled; do not publish secrets or exploit details in public issues; absence of a reported vulnerability is not evidence of security certification.

Required support language: repository-specific implementation/status questions resolve to that repository; DGAF/PDMAL governance questions resolve to `DGAF-Framework`; shared `.github` policy does not supersede local project authority.

- [ ] **Step 3: Add structured issue and PR templates.**

PR checklist must include exact validation performed, unverified claims, docs/evidence changes, cross-repo authority transfer check, and secrets/private-data check.

Bug report must capture reproduction steps, expected/actual behavior, environment/revision, evidence/logs with secrets removed, and whether failure affects only software behavior or also a documented claim.

Feature request must capture problem, proposed scope, repository-local success criteria, evidence needed to promote claims, and explicit non-goals.

- [ ] **Step 4: Refresh README and evidence standard.**

README must describe inheritance/override rules and state that this repo provides defaults rather than global project status. Evidence standard must retain the vocabulary:

`DEFINED → IMPLEMENTED → COMPUTED → VERIFIED → ATTESTED → HISTORICAL → HYPOTHESIS → METAPHOR → UNSUPPORTED → DEPRECATED`

and add explicit rules for historical authority and cross-repository reuse.

- [ ] **Step 5: Validate file structure and YAML syntax.**

Check all expected paths exist on the branch and parse the three YAML issue-template files as YAML. Confirm no template claims global PASS/VERIFIED status.

- [ ] **Step 6: Review diff against main and open a PR.**

PR body must state that community-health inheritance is conditional on absence of a local override and that no project status changes.

---

### Task 2: Agent Control Plane Audit and Minimal Hardening

**Files:**
- Inspect: `README.md`, `pyproject.toml`, `.github/workflows/test.yml`, `tests/`, `src/`
- Modify only evidence-backed gaps discovered in those surfaces.

**Interfaces:**
- Consumes: Task 1 shared defaults.
- Produces: a repo-local PR only if concrete gaps exist; otherwise an audit conclusion with no speculative changes.

- [ ] **Step 1: Check open PRs/issues and recent commits for overlapping work.**

Do not create duplicate CI or documentation work.

- [ ] **Step 2: Inspect workflow permissions, Python version, dependency installation, and test command.**

Audit for explicit least permissions, deterministic install/test commands, and consistency with `pyproject.toml`.

- [ ] **Step 3: Verify README claims against tests and implementation surfaces.**

Specifically check fail-closed unknown-capability behavior, cooperative budget semantics, provenance manifest scope, and stated non-goals.

- [ ] **Step 4: Implement only necessary local corrections on an isolated branch.**

Do not import DGAF-specific gates. Prefer shared community defaults over local copies unless ACP requires different instructions.

- [ ] **Step 5: Verify by running/inspecting the repository's Python test workflow and diff.**

Expected result: existing tests remain authoritative; added CI hardening must not change scientific/security claims.

- [ ] **Step 6: Open a PR only if there is a material correction.**

If no correction is warranted, record the audit as PASS-within-scope rather than creating churn.

---

### Task 3: dgaf-ops Authority and Provenance Audit

**Files:**
- Inspect: `README.md`, `.github/workflows/reliability-provenance.yml`, `deployment_manifest.json`, `SESSION_ANCHOR.md`, `SWEEP_LOG.md`, `ENSEMBLE_ROSTER.md`, `AGENT_MANIFEST.md`, `docs/`, `reliability/`
- Modify only current-looking ambiguity or provenance-validation gaps supported by evidence.

**Interfaces:**
- Consumes: Task 1 default conventions and `DGAF-Framework` authority boundary already stated in `dgaf-ops` README.
- Produces: operational records that remain clearly historical/support-plane records and do not become DGAF sovereign/scientific authority.

- [ ] **Step 1: Check open PRs/issues and recent commits for overlapping work.**

- [ ] **Step 2: Audit reliability/provenance workflow for exact source binding and mutable dependencies.**

Check permissions, action references, source identity validation, artifact generation, and whether a passing run could be misread as current DGAF authorization.

- [ ] **Step 3: Search operational records for unbounded current-authority language.**

Flag phrases such as `current`, `canonical`, `authorized`, `sovereign`, or `verified` only when they can reasonably override or conflict with the current README authority boundary.

- [ ] **Step 4: Apply minimal labels/pointers or workflow corrections.**

Prefer an explicit historical/support-plane notice or exact upstream authority link over moving/deleting provenance records.

- [ ] **Step 5: Validate existing provenance/reliability checks and review diff.**

- [ ] **Step 6: Open a PR only for evidence-backed corrections.**

PR must state that DGAF scientific state and authorization remain unchanged.

---

### Task 4: Orbit-Driftwatch Application/Showcase Audit

**Files:**
- Inspect: `README.md`, `SECURITY.md`, `ARCHITECTURE.md`, `package.json`, `.github/workflows/ci.yml`, `.github/workflows/pages.yml`, `.env.example`, `api/`, `scripts/`, `tests/`, root artifacts including `bar.md` and `claim-audit.html`
- Modify only evidence-backed gaps.

**Interfaces:**
- Consumes: Task 1 defaults, while local `SECURITY.md` overrides the account default.
- Produces: a clearer, reproducible portfolio application without upgrading live deployment/factual-correctness/multi-agent efficacy claims.

- [ ] **Step 1: Check open PRs/issues and recent commits for overlapping work.**

- [ ] **Step 2: Audit CI and Pages permissions/action references/test determinism.**

Confirm CI executes `npm test` or equivalent authoritative test command and that Pages permissions are no broader than needed.

- [ ] **Step 3: Audit credential and provider boundaries.**

Confirm browser surfaces do not require or expose `OPENAI_API_KEY`; verify `.env.example`, server endpoint, and README remain aligned.

- [ ] **Step 4: Classify unusual root artifacts before moving or deleting anything.**

Determine whether `bar.md`, `claim-audit.html`, and other root artifacts are intentional public surfaces, generated artifacts, historical residue, or documentation. Preserve them when purpose is legitimate; prefer documentation clarification to destructive cleanup.

- [ ] **Step 5: Apply only supported CI/docs/structure corrections and validate `npm test`.**

- [ ] **Step 6: Open a PR only if material improvements are justified.**

PR must preserve the current unresolved live-deployment/admin gates and must not claim factual correctness or multi-agent superiority.

---

### Task 5: Cross-Repo Reuse Decision

**Files:**
- Inspect diffs/findings from Tasks 2–4.
- Create reusable workflow(s) in `ndrorchestration/.github/.github/workflows/` only if at least two pilot repositories contain materially identical deterministic validation logic.

**Interfaces:**
- Consumes: observed duplication from completed pilot audits.
- Produces: either an explicitly justified reusable workflow or a documented decision that no shared workflow is warranted yet.

- [ ] **Step 1: Compare pilot workflow logic by purpose, inputs, runtime, and evidence semantics.**

- [ ] **Step 2: Reject false reuse.**

Do not combine Python tests, DGAF provenance validation, and Node application tests merely because they are all CI.

- [ ] **Step 3: If genuine duplication exists, implement one narrowly scoped reusable workflow with explicit `workflow_call` inputs and least permissions.**

- [ ] **Step 4: If no genuine duplication exists, keep workflows local and record that as the correct outcome.**

---

### Task 6: Wave-1 Verification and Portfolio Sync

**Files:**
- Inspect all Wave-1 PR diffs/checks.
- Update Notion classification/Last Sweep only with observed facts; do not duplicate mutable implementation state into Notion.

**Interfaces:**
- Consumes: Tasks 1–5.
- Produces: evidence-backed Wave-1 completion state and next-repo queue.

- [ ] **Step 1: Verify every opened PR's exact head and available checks.**

Classify each as PASS, FAIL, RUNNING, BLOCKED, or NOT VERIFIED. Do not infer.

- [ ] **Step 2: Confirm no PR changes repository role, lifecycle, or authority without corresponding Notion evidence.**

- [ ] **Step 3: Update only the appropriate Notion `Last Sweep`, confidence, relationship, or evidence-boundary fields when the repository audit materially changes them.**

- [ ] **Step 4: Produce the next propagation queue.**

Order: remaining `KEEP_ACTIVE` primary/research projects, then `KEEP_AS_WORKSTREAM`, then `INVESTIGATE`; archived/external-fork repositories remain non-modernization targets unless explicitly reactivated.

- [ ] **Step 5: Merge only fully green PRs whose exact head has been reviewed; leave blocked/admin-dependent work open and explicitly bounded.**
