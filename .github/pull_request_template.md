## Summary

Describe what changed and why.

## Scope and authority

- Target repository/component:
- Exact revision or dependency boundary affected:
- Cross-repository dependency or reused pattern, if any:
- Does this change any public-facing status or evidence claim? If yes, identify the exact claim and supporting evidence.

## Verification performed

List only checks that actually ran on this revision.

```text
command / workflow / review:
result:
```

## Not verified / blocked / out of scope

State skipped, unavailable, blocked, administrative, deployment-only, empirical, or otherwise unresolved validation explicitly.

## Evidence boundary

Confirm that this change does not silently transfer validation, certification, security status, deployment status, authorization, or empirical efficacy from another repository.

For DGAF/PDMAL changes, identify the governing `DGAF-Framework` evidence/authority surface when relevant.

## Risk and rollback

- Main failure mode introduced or changed:
- Rollback/recovery path:
- Secrets, credentials, private data, or migrations involved: yes/no; explain if yes without disclosing secrets.

## Checklist

- [ ] I checked for overlapping open issues/PRs.
- [ ] I ran the repository-appropriate validation listed above.
- [ ] I did not mark missing or skipped checks as passing.
- [ ] Documentation and public claims match the evidence actually produced.
- [ ] Historical/provenance records were preserved or explicitly superseded rather than silently rewritten.
- [ ] No live secret, credential, private personal data, or sensitive exploit detail is included.
- [ ] Any cross-repository reuse preserves repository-local authority and evidence boundaries.
