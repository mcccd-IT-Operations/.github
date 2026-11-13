# Project template adoption and change propagation

Baseline identifier: ITS-REVIEW-1. Status: framework proposal; policy and code approvals are independent.

## New project

1. Create a separate project repository with appropriate visibility; retain dependent code/guides together.
2. Copy the files under [templates/project](../templates/project/) into the project root, preserving paths. Fill in purpose, use, file explanations, version, execution context, validation, dependencies and recovery.
3. Copy [the routing record](../templates/review-routing-record.md) to the project's approval record and populate project-specific impacts. Every pillar must assess; add affected owners.
4. Use the central PR/issue defaults where no local equivalent exists, or copy them explicitly and record that override.
5. Set the central baseline commit and local overrides in the project's GOVERNANCE-ADOPTION.md. Never mark impact approval or production readiness merely because templates were copied.
6. Open a draft review; assign actual representatives and configure/verify repository rules separately.

## Existing project and future updates

Read the latest project branch before editing. Preserve code, findings, local routing and approvals; replace duplicated organization policy with links to this central source. Update local PR/issue templates explicitly because local files override defaults. Record the central policy commit and any project extensions. Extra local routes may add required reviews; they do not remove required central reviews.

A central edit changes linked guidance and eligible defaults, but does not rewrite local copies, existing PR descriptions, approval records or branch rules. Maintainers compare the recorded baseline with central changes, open/update a project review, reconcile overrides and record the adopted baseline. New policy changes and project changes require their appropriate reviews.

There is no scheduled synchronization, bot, workflow or automated enforcement configured here. This is explicit, reviewable template distribution plus central references.

## Rollout inventory

| Repository | Current review branch | Local approval record |
| --- | --- | --- |
| Windows-adobe-code | review/windows/adobe-creative-cloud-v2 | windows-code/adobe-creative-cloud/APPROVAL.md |
| jamf-blueprints-iac | review/jamf-blueprints-python-initial | docs/APPROVAL.md |
| jamf-computer-group-erase | review/sanitized-erase-script | docs/APPROVAL.md |
| jamf-mac-setup | review/mac-setup-revision-11a | docs/APPROVAL.md |
| windows-dcu-compliance | review/dcu-compliance-initial (planned during provisioning) | docs/APPROVAL.md |

Project updates stay in draft reviews until approved. Their main branches may still contain only initial stubs. Do not infer adoption or production approval from this inventory. The central defaults are published on main for use; formal policy approval is tracked separately in [APPROVAL.md](./APPROVAL.md).
