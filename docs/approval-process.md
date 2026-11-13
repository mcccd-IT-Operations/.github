# Review approvals and repository administration

Status: proposed process prepared for administrator setup. No GitHub access controls, teams, branch protections, required checks, or approval integrations have been configured by these files.

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

Requiring two approvals alone does not prove the correct roles approved, and more than two may be required by impact routing. Listing multiple teams as owners of a path does not require approval from every listed team: GitHub accepts an approval from any matching owner. Maintainers must verify each required role, acknowledged exclusions, additional routing, and final CyberSecurity review order until a trusted routing-aware required check or applicable team-specific rules are configured and tested. Do not describe the pillar requirement as automatically enforced before that setup is verified. No placeholder CODEOWNERS entries or inactive checks are presented as enforcement.

References: [protected branches](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches), [managing a protection rule](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/managing-a-branch-protection-rule), and [code owners](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners).

## Project setup and cascade

Follow [template adoption](./template-adoption.md). Every project maintains its own README, routing/approval record, validation, release notes and recovery evidence. The central repository contains policy and templates, not executable project code.

Eligible default community files are supplied from this public repository's default branch to repositories without a local equivalent. Local templates take precedence; they must be updated explicitly. Arbitrary policy files, project records, CODEOWNERS, teams and rules do not automatically cascade. See [GitHub defaults documentation](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file).

Use [project templates](../templates/project/) for new projects. Private projects must keep sensitive operational evidence private. Governance template updates do not grant project approvals or production authorization.
