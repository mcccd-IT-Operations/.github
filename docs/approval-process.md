# Review approvals and repository administration

Status: CODEOWNERS, workflow definitions and label definitions are provided by files. Org owners configure teams/members/access, rulesets, PILLAR_CHECK_TOKEN and required-check registration. Status: [framework adoption, approval and enforcement status](https://github.com/mcccd-IT-Operations/.github/blob/main/GOVERNANCE.md#enforcement-and-related-records).

The governing policy is [GOVERNANCE.md](../GOVERNANCE.md). Route every change through impact assessment by all five pillars and obtain approvals from all affected pillars/additional required parties. Missing approval or unresolved routing keeps approval pending and may delay the project. The five governance pillars do not require five Git branches.

## Access and reviewer assignments

An administrator invites the intended District ITS members and gives contributors/reviewers only the repository access needed for their responsibilities. Assign real, verified GitHub users or teams to these roles before approving code:

| Role | Assignment | Responsibility |
| --- | --- | --- |
| Infrastructure | Pending administrator assignment | Infrastructure/shared-service impact and approval when affected |
| Development | Pending administrator assignment | Code/application/integration impact and approval when affected |
| Business ERPs | Pending administrator assignment | Business-system/data/workflow impact and approval when affected |
| End Point Engineering | Pending administrator assignment | Endpoint/user-session/deployment impact and approval when affected |
| CyberSecurity | Pending administrator assignment | Security impact assessment and final production-bound review |
| District ITS peer reviewers | Pending administrator assignment | Technical review and nonproduction test review |
| Additional routed owners | Pending per assessment | Product, identity, data, support, or other impact review as required |
| Maintainers | Pending administrator assignment | Verify all routing dispositions and required approvals before merge |
| Production deployment owner | Pending per change | Deploy only the approved artifact with applicable authorization |

The author cannot fill an approving role. Require a technical peer and a distinct final CyberSecurity approver, along with all required pillar/additional approvals. A peer may represent an affected pillar when authorized and recorded. Obtain representative acknowledgement for Not applicable dispositions; no response stays pending. Invitations, labels, comments, and checklists are not formal approval.

## Branch and merge controls to configure

For `main` and any future production branch, an authorized administrator must configure and verify:

- Changes through pull requests, with at least two approving reviews as a baseline, plus verification of every required pillar/additional role; a fixed count does not encode the complete routing requirement.
- Dismissal of stale approvals when new commits change the candidate, and review of the latest reviewable push by someone other than its pusher.
- Resolution of review conversations before merge; no unresolved requests for changes.
- Applicable tested status checks once those checks actually exist; do not claim a nonexistent check is enforced.
- Restrictions on direct updates, force pushes, deletion, and bypass permissions so routine work cannot circumvent the review process.
- A real CODEOWNERS assignment using verified reviewer handles with the required repository access. Protect changes to review-governance files as well as code.

Requiring two approvals alone does not prove the correct roles approved, and more than two may be required by impact routing. Listing multiple teams as owners of a path does not require approval from every listed team: GitHub accepts an approval from any matching owner. Maintainers must verify each required role, acknowledged exclusions, additional routing, and final CyberSecurity review order until a trusted routing-aware required check or applicable team-specific rules are configured and tested. Do not describe the pillar requirement as automatically enforced before that setup is verified. CODEOWNERS entries must resolve to the requested teams with repository access; verify them before activating required owner reviews.

References: [protected branches](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches), [managing a protection rule](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/managing-a-branch-protection-rule), and [code owners](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners).

## Project setup and cascade

Follow [template adoption](./template-adoption.md). Every project maintains its own README, routing/approval record, validation, release notes and recovery evidence. The central repository contains policy and templates, not executable project code.

Eligible default community files are supplied from this public repository's default branch to repositories without a local equivalent. Local templates take precedence; they must be updated explicitly. Arbitrary policy files, project records, CODEOWNERS, teams and rules do not automatically cascade. See [GitHub defaults documentation](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file).

Use [project templates](../templates/project/) for new projects. Private projects must keep sensitive operational evidence private. Governance template updates do not grant project approvals or production authorization.

## Part A activation and verification

Org owners complete security/member privileges, provision teams with active members and repository access, create labels from [the label definitions](../templates/labels.json), review/merge this central configuration PR, then provision the PILLAR_CHECK_TOKEN secret, rulesets and required-check registration in the order specified by the 2026-11-13 configuration runbook. No merge is performed by this change.

PILLAR_CHECK_TOKEN needs organization Members:Read and repository Pull requests:Read for every selected project; use a narrowly scoped token/App and an organization secret available to the intended callers. Do not put its value in a file or issue. No checkout or PR-controlled code runs in the metadata-only approval job. Lint executes only on pull_request with a read-only token and no membership secret; it checks out code without persisted credentials.

The approval job accepts only known pillar slugs, always requires CyberSecurity plus at least one other pillar label, excludes the author, requires each reviewer's latest state to be APPROVED on the current head, verifies active team membership, requires a peer, and requires distinct final security approval after the other counted pillar approvals and a peer. It fails on metadata races or unverifiable membership. All-five impact acknowledgements, additional routing and CAB evidence still need maintainer verification; the labels alone do not prove those obligations.

Run 13 metadata-only scenarios before deployment: valid approvals; no labels; security-only labels; author-only; old head; dismissed latest review; early security; same peer/security reviewer; unknown pillar; inactive membership; denied membership API; head change; required-pillar approval after security. These synthetic checks pass during preparation; workflow YAML parses. GitHub Actions, Graph/team APIs and required-check enforcement were not exercised live.

Validate a real test PR after activation. Observe the exact emitted check context on the PR head before registering it as required: reusable workflow/job naming and event context must not be assumed to equal a display label. Confirm both review events and label changes update the correct candidate. Verify rejected force pushes/tag updates through authorized tests. Pin/approve tool versions and permissions as part of owner review.
