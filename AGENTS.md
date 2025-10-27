# Repository Guidelines

## Project Structure & Module Organization
Keep the root tidy: `openspec/` hosts all specification work, while `docs/` is reserved for published guidance. Within `openspec/`, use `specs/<capability>/spec.md` for live requirements and `changes/<change-id>/` for in-flight proposals; archive completed work under `changes/archive/` when prompted by tooling. Place any supplementary assets beside the spec or proposal they clarify, and include relative links so future readers see the context in one click.

## Build, Test, and Development Commands
This repository is documentation-first; there is no runtime build. Use the OpenSpec CLI to manage changes:
`openspec list --specs` enumerates shipped capabilities, `openspec list` shows active changes, `openspec show <item>` inspects details, and `openspec validate <change-id> --strict` confirms formatting and scenario coverage before review. Run commands from the repository root so path resolution stays consistent across contributors.

## Coding Style & Naming Conventions
Author content in Markdown with 80–100 character lines, fenced code blocks for commands, and verb-led bullet lists when outlining tasks. Follow the OpenSpec naming pattern for change IDs—short kebab-case starting with `add-`, `update-`, `remove-`, or `refactor-`. Keep filenames descriptive (`proposal.md`, `tasks.md`, `design.md`) and prefer ASCII characters unless quoting external material. Review `openspec/AGENTS.md` for detailed spec-writing rules before drafting changes.

## Testing Guidelines
Treat `openspec validate --strict` as the CI gate; run it whenever you modify specs or proposals. Each requirement must include at least one `#### Scenario:` block describing WHEN/THEN behavior. When adjusting shipped specs, diff the result with `openspec diff <change-id>` and capture notable behavior shifts in your proposal so reviewers can replay the reasoning.

## Commit & Pull Request Guidelines
Keep commits focused and message them in the imperative mood (e.g., `Add payment-capability spec`). Reference relevant change IDs in both commits and PR descriptions, summarize what changed, and call out any validation outputs or screenshots that help reviewers reproduce results. Pull requests should link to approval discussions and list manual checks performed; include follow-up tasks when work is deferred.

## Agent Workflow Tips
Before editing, scan pending work with `openspec list` and confirm no conflicting change already targets your capability. If multiple assistants contribute, coordinate change ownership inside `proposal.md` to avoid duplicated effort. When in doubt, ask for clarification rather than guessing—small course corrections save time compared to rewriting specs after review.
