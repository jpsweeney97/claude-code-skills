# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project follows [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

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
