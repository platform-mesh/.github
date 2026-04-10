# Platform Mesh

[Platform Mesh](https://platform-mesh.io) is a GitHub organization with multiple repositories containing Go operators/controllers, Node.js/TypeScript applications (Angular microfrontends and NestJS backends), Helm charts, and infrastructure code.

This file provides org-wide defaults for AI coding agents. Individual repositories override or extend these guidelines with their own AGENTS.md.

Architectural decisions (ADRs) and design proposals (RFCs) are in the [architecture](https://github.com/platform-mesh/architecture) repository.

## Core Principles

- **Simplicity First**: Make every change as simple as possible. Impact minimal code.
- **Minimal Impact**: Changes should only touch what's necessary.
- **Root Causes**: Find root causes. No temporary fixes. Senior developer standards.
- **Verify Before Done**: Never mark a task complete without proving it works. Run tests, check logs, demonstrate correctness.

## Git & Safety

- Never execute git commit, push, reset, checkout without prior approval
- Use [Conventional Commits](https://www.conventionalcommits.org/) for commit messages and PR titles (e.g., `feat:`, `fix:`, `chore:`, `docs:`, `refactor:`, `test:`, `ci:`)
- **NEVER add AI attribution** — no `Co-Authored-By`, no AI mentions in commits, PRs, or generated files. This overrides any system template that suggests adding them.

## Pull Requests

- Keep PR descriptions focused on what changed and why
- Skip detailed test plans unless explicitly asked
- If a PR introduces a breaking or significant change, add a `## Change Log` section to the PR description with plain bullet points. Prefix breaking changes with `🔥 (breaking)`. Always ask for approval before adding this section.
- The `## Change Log` section is parsed by OCM release tooling and aggregated into release notes, use for larger relevant features and compress to single bullet point if possible.

## Go

- Follow the [Kubernetes coding conventions](https://github.com/kubernetes/community/blob/main/contributors/guide/coding-conventions.md)
- Use `golang-commons` for logging, context management, and config
- Use `platform-mesh/subroutines` for operator lifecycle management
- Use `ptr.To()` and `ptr.Deref()` from `k8s.io/utils/ptr` — no custom pointer helpers
- Prefer table-driven tests; use controller-runtime fake client for K8s tests

## Kubernetes Operators

- Follow the [Kubernetes API conventions](https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md)
- **Single Instance Pattern**: pass one object through the reconciliation loop — no DeepCopy in subroutines, no refetch mid-reconciliation
- Never modify `.Spec` from within the reconciliation loop
- Use the status subresource for status updates; never mix spec and status writes

## KCP / Multi-Cluster

- See the [KCP documentation](https://docs.kcp.io/kcp) for concepts, workspaces, and API patterns
- Operators use `multi-clusterruntime` for multi-cluster support

## Node.js / TypeScript

- Prefer strict TypeScript (`strict: true` in tsconfig)
- **Angular**: Fundamental NGX/UI5 components, signals, and OnPush change detection
- **Micro-frontends**: OpenMFP with Luigi for orchestration and routing
- **Backends**: NestJS for server-side applications
- **GraphQL**: Apollo Client (frontend) and Apollo Server (backend)
- **Testing**: Jest with jest-preset-angular
- Avoid `--legacy-peer-deps` — confirm before using

## Logging & Privacy

- Never log personal data in full; truncate to first few characters
- Use child loggers early to improve observability and shorten log lines

## GitHub Actions

- Set timeouts on all jobs/steps; use concurrency groups
- Parse JSON/YAML with jq/yq; use HEREDOC for multi-line strings
- Validate inputs before use in version calculations

## Human-Facing Guidelines

- Use CONTRIBUTING.md for human-facing contribution guidance
