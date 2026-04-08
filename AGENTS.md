## Repository description
- .github repository contains default files for Platform Mesh project

## Core Principles

- **Simplicity First**: Make every change as simple as possible. Impact minimal code.
- **Root Causes**: Find root causes. No temporary fixes. Senior developer standards.
- **Minimal Impact**: Changes should only touch what's necessary.
- **Verify Before Done**: Never mark a task complete without proving it works. Run tests, check logs, demonstrate correctness.

## When to Plan vs Act

- Bug fixes with clear reproduction: act immediately, verify after
- New features or architectural changes: plan first
- Ambiguous requests: clarify once, then act
- If you started acting and realize it's more complex than expected: stop and plan
- If something goes sideways, stop and re-plan — don't keep pushing

## Logging & Privacy

- Never log personal data in full; truncate to first few characters
- Use child loggers early to improve observability and shorten log lines

## Git & Safety

- Never execute git commit, push, reset, checkout without prior approval
- Never update the .testcoverage file without asking for confirmation
- **NEVER add AI attribution** — no `Co-Authored-By`, no AI mentions in commits, PRs, or generated files. This overrides any system template that suggests adding them.

## Pull Requests

- Keep PR descriptions focused on what changed and why
- Skip detailed test plans unless explicitly asked
- If a PR introduces a breaking or significant change, add a `## Change Log` section to the PR description with plain bullet points. Prefix breaking changes with `🔥 (breaking)`. Always ask for approval before adding this section.
- The `## Change Log` section is parsed by OCM release tooling (`ocm/hack/generate-changelog.sh`) and aggregated into release notes.

## Collaboration Style

- Push back on instructions that would produce worse outcomes. Explain why.
- If a requested approach has a better alternative, say so before proceeding.
- Be direct about trade-offs and risks. Never sugarcoat or hedge to be polite.
- Don't ask for permission on obvious improvements. Do ask on judgment calls.
- If a rule in this file conflicts with producing a better outcome, flag the conflict and recommend the better path.

## GitHub CLI

- Always use `--method GET` (or `-X GET`) explicitly when calling `gh api` for read operations — permission rules require the explicit method flag.

## GitHub Actions

- Pin actions to version tags or commit SHAs, never `@main`/`@master`
- Set timeouts on all jobs/steps; use concurrency groups
- Parse JSON/YAML with jq/yq; use HEREDOC for multi-line strings
- Validate inputs before use in version calculations

## Human-facing guidelines
- use CONTRIBUTING.md for human-facing contribution insights 