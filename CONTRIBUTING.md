# Contributing to Platform Mesh

Thank you for your interest in contributing to Platform Mesh! This document explains how to contribute, what to expect during the process, and the practices we follow. Platform Mesh projects are [Apache 2.0 licensed](LICENSE) and accept contributions via GitHub Pull Requests.

## Table of Contents

- [Getting Started](#getting-started)
  - [Code of Conduct](#code-of-conduct)
  - [Developer Certificate of Origin](#developer-certificate-of-origin)
- [How to Contribute](#how-to-contribute)
  - [Finding What to Work On](#finding-what-to-work-on)
  - [Reporting Bugs](#reporting-bugs)
  - [Requesting Features](#requesting-features)
  - [Contributing with AI-Generated Code](#contributing-with-ai-generated-code)
- [Development Workflow](#development-workflow)
  - [Commit Messages](#commit-messages)
  - [Signing Your Commits](#signing-your-commits)
  - [Submitting a Pull Request](#submitting-a-pull-request)
- [Code Review](#code-review)
- [Code Style Guide](#code-style-guide)
- [Testing](#testing)
- [Security](#security)
- [Community and Communication](#community-and-communication)

## Getting Started

### Code of Conduct

Please make sure to read and follow our [Code of Conduct](CODE_OF_CONDUCT.md).

### Developer Certificate of Origin

Platform Mesh uses the [Developer Certificate of Origin (DCO)](https://developercertificate.org/) to ensure that contributors have the legal right to submit their work. All commits must be signed off to indicate your agreement with the DCO.

To sign your commits, add a `Signed-off-by` line to your commit message:

```
Signed-off-by: Jane Example <jane@example.com>
```

The easiest way to do this is with the `--signoff` (or `-s`) flag:

```bash
git commit --signoff -m "feat: add new feature"
```

If you've already created a PR and need to sign off all existing commits, you can rebase with the `--signoff` flag:

```bash
git rebase --signoff origin/main
```

By signing off, you certify that you wrote the code or otherwise have the right to submit it under the open source license used by the project.

## How to Contribute

### Finding What to Work On

A great place to start is the list of open issues. We use [the `platform-mesh/backlog` repository](https://github.com/platform-mesh/backlog/) to track our work. Please check [the repository's README.md file](https://github.com/platform-mesh/backlog/blob/main/README.md#getting-started) for more information on how to find suitable tasks.

If you are unsure where to start or have questions, feel free to open an issue or reach out through our community channels.

### Reporting Bugs

Before opening a bug report, please search existing issues to avoid duplicates. When filing a bug, include:

- A clear, descriptive title
- Steps to reproduce the issue
- Expected vs. actual behavior
- Relevant logs, error messages, or screenshots
- Your environment (OS, versions of relevant tools and dependencies)

### Requesting Features

We welcome ideas for new features or improvements. Before starting implementation work, please open an issue to discuss your proposal. Describe:

- The problem you want to solve and its use cases
- Your proposed approach and what it would look like
- Any known alternatives you've considered

This discussion helps align the feature with the project direction and avoids wasted effort. The more significant the change, the more important it is to align early. Once the proposal is accepted, we encourage you to open a draft PR so maintainers and users can give early feedback.

**Not all proposed contributions can be accepted.** Some features may be out of scope or fit better in another project. We will communicate this clearly and promptly.

### Contributing with AI-Generated Code

We recognize the potential benefits of AI-assisted development. If you use AI tools to generate or assist with your contribution, please see our [guidelines for AI-generated code contributions](CONTRIBUTING_USING_GENAI.md) for the requirements that apply.

You are responsible for reviewing, testing, and verifying any AI-generated code before submitting it. Ensure it is correct, does not introduce security vulnerabilities, and complies with the project license.

## Development Workflow

### Commit Messages

Write clear and meaningful commit messages. We follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

```
<type>(<scope>): <short summary>

<optional body explaining the why, not the what>
```

Common types: `feat`, `fix`, `docs`, `chore`, `refactor`, `test`, `ci`.

Good commit messages explain *why* a change was made, not just what changed. Keep the subject line under 72 characters and use the imperative mood ("add feature" not "added feature").

Additional guidelines:

- Do not include `@mentions` or `fixes #<issue>` keywords in commit messages — put those in the PR description instead.
- Squash fixup commits before submitting if they don't add useful history.

### Signing Your Commits

All commits must include a `Signed-off-by` line. See [Signing Your Commits](#signing-your-commits) above.

### Submitting a Pull Request

1. Ensure your branch is up to date with `upstream/main`.
2. Run the full test suite and linting checks locally and confirm everything passes.
3. Push your branch to your fork:

   ```bash
   git push origin feat/short-description
   ```

4. Open a pull request against the `main` branch of the upstream repository.
5. Fill in the PR template with:
   - A clear summary of what the PR does and why
   - Links to related issues (e.g., `Closes #123`)
   - Any relevant context reviewers need
6. Mark the PR as a **Draft** if it is not yet ready for review.

CI checks will run automatically. Address any failures before requesting a review.

## Code Review

Code review is an important part of the contribution process. To make review go smoothly:

- **For contributors:** Keep PRs focused and small. A series of smaller, logically coherent PRs is easier to review than one large change. Respond to review comments promptly and be open to feedback.
- **For reviewers:** Be respectful, constructive, and timely. Reviewers should focus in order on: (1) Is the idea sound? (2) Is the design correct? (3) Is the implementation polished?

Please note that maintainers may have many responsibilities and reviews may take time. If your PR has not received attention after a reasonable period, feel free to leave a comment to request a review.

## Code Style Guide

The guidelines below apply across all Platform Mesh projects.

### Testing

All contributions should include appropriate tests. Before submitting a PR:

- Run the existing test suite to confirm no regressions.
- Add unit tests for new or changed logic.
- Add integration or end-to-end tests for larger features where applicable.

### Linting

All code must pass linting checks before a PR can be merged. CI enforces this automatically. Run linting locally before pushing to catch issues early. Go-based projects generally use [`golangci-lint`](https://github.com/golangci/golangci-lint).

### Language-Specific Guidelines

**Bash**
- Follow the [Google Shell Style Guide](https://google.github.io/styleguide/shellguide.html).
- Ensure scripts are portable and tested on both Linux and macOS where applicable.

**Go**
- Follow [Effective Go](https://golang.org/doc/effective_go.html) and the [Go Code Review Comments](https://github.com/golang/go/wiki/CodeReviewComments).
- Use `gofmt` and `goimports` to format your code.
- Command-line flags should use dashes, not underscores.
- Avoid redundancy in package and interface names (e.g. prefer `storage.Interface` over `storage.StorageInterface`).

**TypeScript**
- Follow the [Google TypeScript Style Guide](https://google.github.io/styleguide/tsguide.html).
- Use the project's existing `tsconfig.json` and ESLint configuration — do not override them locally.

## Security

**Please do not report security vulnerabilities via public GitHub issues.**

If you believe you have found a security vulnerability, please follow the responsible disclosure process described in our [Security Policy](SECURITY.md). This allows us to address the issue before it is publicly disclosed.

## Community and Communication

We welcome questions, feedback, and discussion. Please avoid contacting maintainers directly — public channels are faster and help others with similar questions.

For a full list of community channels, events, and ways to get involved, visit the [Platform Mesh community page](https://platform-mesh.io/main/community/).
