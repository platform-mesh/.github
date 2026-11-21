# Platform Mesh Security Policy

The Platform Mesh project takes the security of our software seriously, including all source code repositories managed through the [platform-mesh](https://github.com/platform-mesh) GitHub organization.

If you believe you have found a security vulnerability in any platform-mesh repository, please report it to us as described below.

## Reporting Security Issues

**Please do NOT**:

- **Report potential security vulnerabilities through GitHub issues or other public channels,**
- **Contact Security Response Team members directly**

Instead, please use one of the following channels:

  - **GitHub Security Advisories** — navigate to the **Security** tab of the affected repository and select **"Report a vulnerability"** to privately report an advisory.
  - Email: [platform-mesh-security@lists.neonephos.org](mailto:platform-mesh-security@lists.neonephos.org)

Please include the requested information listed below (as much as you can provide) to help us better understand the nature and scope of the possible issue:

  - The repository name or URL
  - Type of issue (buffer overflow, SQL injection, cross-site scripting, etc.)
  - Full paths of the source file(s) related to the manifestation of the issue
  - The location of the affected source code (tag/branch/commit or direct URL)
  - Any particular configuration required to reproduce the issue
  - Step-by-step instructions to reproduce the issue
  - Proof-of-concept or exploit code (if possible)
  - Impact of the issue, including how an attacker might exploit the issue

This information will help us triage your report more quickly.

## Preferred Languages

We prefer all communications to be in English.

## Security Contacts

The Security Response Team, reachable through the channels above, collectively serves as the security contact for Platform Mesh projects.

## Supported Versions

Platform Mesh releases in calver-as-semver: `vYY.MM.<patch>` and
provides security updates for the last three monthly releases.

## Response Process

This project follows the [NeoNephos Security Guidelines](https://github.com/neonephos/guidelines-development/blob/main/security-guidelines/security-guidelines.md) for vulnerability handling. In summary:

- **Initial response**: We will respond to your report within **14 calendar days** of receipt, in line with the [OpenSSF Best Practices](https://www.bestpractices.dev/) requirement.
- **Embargo**: Vulnerability details will remain confidential for up to **90 days** from report receipt while a fix is developed, consistent with the [Google Project Zero disclosure policy](https://googleprojectzero.blogspot.com/2021/04/policy-and-disclosure-2021-edition.html).
- **Disclosure**: Once a fix is available (or the embargo expires), we will publish a security advisory with full details.

### Severity Response Targets

| Severity | CVSS Score | Fix Target | Disclosure Target |
|----------|------------|------------|-------------------|
| Critical | 9.0 – 10.0 | ≤ 14 days | ≤ 30 days         |
| High | 7.0 – 8.9 | ≤ 30 days     | ≤ 60 days         |
| Medium | 4.0 – 6.9 | ≤ 90 days   | ≤ 90 days         |
| Low | 0.1 – 3.9 | Best effort    | Best effort       |

*These are **SHOULD**-level targets as defined by the [NeoNephos Security Guidelines](https://github.com/neonephos/guidelines-development/blob/main/security-guidelines/security-guidelines.md#7-severity-classification-and-response-targets). The 90-day embargo ceiling is a **MUST** aligned with Google Project Zero. All timelines are measured from report receipt (Day 0); fix and disclosure may occur simultaneously.*

## Handling and Disclosing Security Issues

We follow [coordinated disclosure](https://en.wikipedia.org/wiki/Coordinated_vulnerability_disclosure). We ask that you:

- Allow us reasonable time to investigate and address the vulnerability before public disclosure.
- Do not exploit the vulnerability beyond what is necessary to demonstrate the issue.
- Do not access or modify data belonging to other users.

We are committed to crediting reporters in our security advisories unless you prefer to remain anonymous.

For full details on how we handle and disclose security issues — including what to expect after reporting, and information for the end user community — please refer to [the Security document on the Platform Mesh website](https://platform-mesh.io/main/reference/security/).

## CRA Stewardship

CRA stewardship: This project is supported under the Linux Foundation CRA stewardship framework, as described at https://www.linuxfoundation.org/security. Security vulnerabilities should be reported through the mechanisms described above, which we will coordinate with our CRA steward. For actively exploited vulnerabilities and severe incidents that may require CRA escalation, please use the project's emergency security reporting mechanisms as appropriate.

**CRA Steward Contact**: `steward@linuxfoundation.org`

**Commercial Intent**: Platform Mesh software is designed and intended for use in commercial contexts.

For more information, see the [NeoNephos Security Guidelines §11](https://github.com/neonephos/guidelines-development/blob/main/security-guidelines/security-guidelines.md#11-eu-cyber-resilience-act-cra-compliance).

## Infrastructure Escalation Path

Platform Mesh is hosted in the [NeoNephos GitHub Enterprise](https://github.com/enterprises/neonephos).
Infrastructure issues (e.g. organization access, membership, or enterprise-level settings) are escalated to the
[NeoNephos GitHub Account Administration team](https://github.com/neonephos/account-administration), in line with the
[NeoNephos Project Guidelines §15.4](https://github.com/neonephos/guidelines-development/blob/main/project-guidelines/project-guidelines.md#154-escalation-and-support).

1. Report the issue to the Security Response Team at
   [platform-mesh-security@lists.neonephos.org](mailto:platform-mesh-security@lists.neonephos.org).
2. If it cannot be resolved at organization level, the team escalates it by opening an issue in
   [neonephos/account-administration](https://github.com/neonephos/account-administration/issues).

- **Non-critical issues**: Foundation contacts respond within **48 hours**.
- **Critical outages**: Foundation contacts respond within **24 hours**.

*These are **SHOULD**-level targets as defined by the NeoNephos Project Guidelines. **Do not include vulnerability details in a public issue**; use the reporting channels above instead.*

## Past Security Advisories

Published advisories are listed per repository in the repository's
**Security → Advisories** tab. Direct link (replace `<repository>` with the repository in question,
e.g. `platform-mesh`):

```text
https://github.com/platform-mesh/<repository>/security/advisories?state=published
```
