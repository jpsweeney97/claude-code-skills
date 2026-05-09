# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project follows [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.2.0] - 2026-05-08

### Removed

- **11 skills cut** from the curated set: `adversarial-review` (overlapped with `scrutinize`), `implementation-review` (curated set has enough critique skills), `review-code` / `review-plan` / `review-strategy` / `review-writing` (slash-command stubs that thinly route to other skills), `llm-reference` (narrow audience), `merge-branch` (too thin to earn a slot), `exiting-worktrees` (tied to a specific built-in tool), `prompt-generator` (polished but doesn't fit the curated identity), `format-export` (narrow utility). Recovery is via git history (the v0.1.0 release commit `1d07a27` retains all source).

### Moved

- **5 agent-team-powered skills moved** to the new companion plugin [`claude-code-agent-teams`](https://github.com/jpsweeney97/claude-code-agent-teams): `claude-md`, `design-review-team`, `explore-repo`, `handbook`, `readme`. To install the companion plugin: `/plugin install claude-code-agent-teams@jpsweeney97-agent-teams`. The companion plugin is fully standalone — no operational cross-references between the two plugins.

### Changed

- **Requirements section removed from README.** No surviving skill requires `CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1` or Claude Code v2.1.32+. The agent-teams skills moved to the companion plugin.
- **Trigger-shadow note removed from README.** Verified against the [official docs](https://code.claude.com/docs/en/skills#override-skill-visibility-from-settings): `skillOverrides` does not apply to plugin skills. For dual-install collisions (`system-design-review` ↔ `design-review-team`), manual invocation (`/<plugin>:<skill>`) always works; `/plugin` provides plugin-level visibility control.
- **CONTRIBUTING.md gains a "Cross-plugin references" section** codifying the standalone-plugin design principle.

## [0.1.0] - 2026-05-08

### Added

- **Review & adversarial critique** (9 skills): `adversarial-review`, `scrutinize`, `implementation-review`, `system-design-review`, `design-review-team`, `review-code`, `review-plan`, `review-strategy`, `review-writing`.
- **Grounded documentation generation** (3 skills): `readme`, `handbook`, `claude-md`.
- **Repo exploration & analysis** (2 skills): `explore-repo`, `llm-reference`.
- **Workflow** (7 skills): `git-hygiene`, `merge-branch`, `exiting-worktrees`, `next-steps`, `making-recommendations`, `prompt-generator`, `format-export`.
- **Authoring** (1 skill): `writing-principles`.
- Marketplace catalog at `.claude-plugin/marketplace.json` for one-line install.
- README with namespacing + Trigger-shadow + Requirements sections; CONTRIBUTING.md with maintenance flow; MIT license.

### Notes

- Five skills (`claude-md`, `design-review-team`, `explore-repo`, `handbook`, `readme`) require Claude Code v2.1.32+ and `CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1`. See README Requirements section.
