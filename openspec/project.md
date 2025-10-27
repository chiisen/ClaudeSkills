# Project Context

## Purpose
Create and maintain a concise landing page that introduces Anthropic Claude Skills in Traditional Chinese, highlighting capabilities, use cases, and onboarding steps for contributors and readers.

## Tech Stack
- Static HTML + CSS (no JS build tooling)
- Markdown documentation (OpenSpec driven)

## Project Conventions

### Code Style
Prefer semantic HTML5 structure with descriptive class names, 2-space indentation, and max line width near 100 characters. Keep CSS scoped within each page; reuse color tokens defined in `:root`. Documentation uses Traditional Chinese, Markdown headings, and bullet lists with verb-led phrasing.

### Architecture Patterns
The site is a single-page brochure in `docs/index.html`. Additional assets should live under `docs/` with relative paths. Specifications and proposals follow OpenSpec: active requirements in `openspec/specs/`, in-flight changes under `openspec/changes/<change-id>/`.

### Testing Strategy
No automated UI tests. Validate HTML structure with manual browser preview. Run `openspec validate --strict` before submitting spec or proposal updates to ensure formatting rules and scenarios pass.

### Git Workflow
Use short-lived feature branches. Commits follow imperative mood (`Add skills landing page hero`). Reference relevant change IDs in PR titles/descriptions. Keep diffs focused; one logical concern per commit when possible.

## Domain Context
Claude Skills are reusable instruction bundles introduced by Anthropic to let teams package workflows, tools, and branded tone. They can be shared across users, integrated via API/automation platforms, and governed with permissions.

## Important Constraints
All content must respect Anthropic's official messaging and remain within public information. Maintain Traditional Chinese localization. Avoid introducing build dependencies; keep the project deployable as static assets.

## External Dependencies
Relies on Anthropic's published announcements for authoritative information. No runtime external services beyond standard web fonts available in browsers.
