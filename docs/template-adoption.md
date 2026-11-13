# Project template adoption and change propagation

Baseline identifier: ITS-REVIEW-1.

Status: [framework adoption, approval and enforcement status](https://github.com/mcccd-IT-Operations/.github/blob/main/GOVERNANCE.md#enforcement-and-related-records).

## New project

1. Create a separate project repository with appropriate visibility; retain dependent code/guides together.
2. Copy the files under [templates/project](../templates/project/) into the project root, preserving paths. Fill in purpose, use, file explanations, version, execution context, validation, dependencies and recovery.
3. Copy [the routing record](../templates/review-routing-record.md) to docs/APPROVAL.md (move an existing record from another path) and populate project-specific impacts. Every pillar must assess; add affected owners.
4. Use central contribution/PR/issue defaults; remove equivalent local copies. Retain meaningful differences only when recorded as local overrides.
5. Set the central baseline commit and local overrides in the project's GOVERNANCE-ADOPTION.md. Never mark impact approval or production readiness merely because templates were copied.
6. Open a draft review; assign actual representatives and configure/verify repository rules separately.

## Existing project and future updates

Read the latest project branch before editing. Preserve code, findings, local routing and approvals; replace duplicated organization policy with links to this central source. Remove local contribution/PR/issue files equivalent in meaning to central defaults. Keep differing files and record their overrides. Record the central policy commit and any project extensions. Extra local routes may add required reviews; they do not remove required central reviews.

A central edit changes linked guidance and eligible defaults, but does not rewrite local copies, existing PR descriptions, approval records or branch rules. Maintainers compare the recorded baseline with central changes, open/update a project review, reconcile overrides and record the adopted baseline. New policy changes and project changes require their appropriate reviews.

Reusable pillar-approval and lint workflows, caller templates and CODEOWNERS are provided. Copy workflow callers and project-specific CODEOWNERS; org owners complete activation in the administrator runbook. Community-file defaults are inherited, while approval records and meaningful overrides remain local.

## Rollout inventory

| Repository | Current review branch | Local approval record |
| --- | --- | --- |
| Windows-adobe-code | review/windows/adobe-creative-cloud-v2 | docs/APPROVAL.md |
| jamf-blueprints-iac | review/jamf-blueprints-python-initial | docs/APPROVAL.md |
| jamf-computer-group-erase | review/sanitized-erase-script | docs/APPROVAL.md |
| jamf-mac-setup | review/mac-setup-revision-11a | docs/APPROVAL.md |
| windows-dcu-compliance | review/dcu-compliance-initial | docs/APPROVAL.md |
| intune-device-naming | review/intune-device-naming-initial | docs/APPROVAL.md |

Project changes remain in their existing review branches until the applicable reviews are complete. Record the central config PR merge commit in each GOVERNANCE-ADOPTION.md after merge; until then use PENDING — set after .github PR merges. Policy review evidence is tracked in [APPROVAL.md](./APPROVAL.md).