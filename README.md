# MCCCD District Information Technology Services — Review Framework

This is the organization base for code review structure, five-pillar governance, documentation standards and reusable project templates. Executable projects have separate repositories with their own purpose, usage, versions, findings, validation and approval evidence.

**Framework ITS-REVIEW-1 is a proposal provisioned at the organization's direction. Formal five-pillar policy adoption, reviewer assignments and enforcement remain pending. No project gains production approval through this restructure.**

## Governance and review

Every party affected through support responsibilities, users, products or services gets an opportunity to review. Infrastructure, Development, Business ERPs, End Point Engineering and CyberSecurity each assess impact. All affected pillars and additional required routes must approve. A reasoned Not applicable needs representative acknowledgement; no response stays pending and may delay the project.

Obtain technical peer review, required impact reviews and final CyberSecurity approval by a reviewer distinct from author and approving peer. Approvals identify the final commit. Production authorization is separate.

- [Governing policy](./GOVERNANCE.md)
- [Routing guidance](./docs/review-routing.md)
- [Code opening notes and section-comment standard](./docs/code-documentation.md)
- [Administrator setup and enforcement limits](./docs/approval-process.md)
- [Project template adoption and updates](./docs/template-adoption.md)
- [Framework policy approval record](./docs/APPROVAL.md)
- [Reusable project starter](./templates/project/) and [routing record](./templates/review-routing-record.md)

## Project catalog

| Project | Scope | Review |
| --- | --- | --- |
| [Windows-adobe-code](https://github.com/mcccd-IT-Operations/Windows-adobe-code) | Adobe Creative Cloud Windows/SailPoint remediation; Version 1 and Version 2 downloads | [Draft review](https://github.com/mcccd-IT-Operations/Windows-adobe-code/pull/1); pending |
| [jamf-blueprints-iac](https://github.com/mcccd-IT-Operations/jamf-blueprints-iac) | Python and Zsh implementations of one Blueprint migration workflow | [Draft review](https://github.com/mcccd-IT-Operations/jamf-blueprints-iac/pull/1); private, pending |
| [jamf-computer-group-erase](https://github.com/mcccd-IT-Operations/jamf-computer-group-erase) | Sanitized computer-group erase workflow | [Draft review](https://github.com/mcccd-IT-Operations/jamf-computer-group-erase/pull/1); private, pending |
| [jamf-mac-setup](https://github.com/mcccd-IT-Operations/jamf-mac-setup) | Mac onboarding Revision 11A and operator guides | [Draft review](https://github.com/mcccd-IT-Operations/jamf-mac-setup/pull/1); private, pending |
| [windows-dcu-compliance](https://github.com/mcccd-IT-Operations/windows-dcu-compliance) | Dell Command Update PowerShell compliance script and two supplied guides | [Draft review](https://github.com/mcccd-IT-Operations/windows-dcu-compliance/pull/1); private, pending |

Each independent tool/package has its own repository; dependent scripts, alternative implementations and guides stay with that tool. Local uploads do not create a native GitHub fork relationship. Python and API are organizational categories; new independent projects receive their own repositories rather than being placed in this policy repository.

## How the framework cascades

Eligible community files are GitHub defaults when a project lacks a local equivalent. Project-specific templates override those defaults and need explicit updates. Governance records and arbitrary files are copied/referenced through the starter and adoption process; reviewer teams, rules and approval checks require administrator configuration.

Defaults do not appear in project clones/downloads, so projects retain a small governance pointer, adoption record and local approval evidence. Use absolute central-policy links in templates so they work across repositories. See [GitHub default community files](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file).

This repository is public. Store only publishable policy/template text here; keep credentials and restricted project/security evidence in approved restricted systems.