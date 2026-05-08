# claude-code-skills

A curated collection of [Claude Code](https://code.claude.com) skills focused on rigorous review, adversarial critique, and grounded documentation. Each skill is a self-contained instruction document that Claude loads on demand and follows like an expert co-worker would. Everything here is also installable via the Claude Code plugin marketplace.

## Namespacing

After install, every skill in this plugin is invocable under the `claude-code-skills` namespace:

```
/claude-code-skills:scrutinize
/claude-code-skills:adversarial-review
/claude-code-skills:readme
```

This guarantees that names from this plugin can never collide with skills from other plugins or your own personal skills.

## Trigger-shadow note

If a skill's name or trigger phrase overlaps with a skill you already use (yours, or another plugin's), Claude may auto-trigger the wrong one. The cleanest fix is settings-level: use [`skillOverrides`](https://code.claude.com/docs/en/skills#override-skill-visibility-from-settings) to disable the version you don't want. No skill editing required.

If you want a specific skill from this plugin every time, just call it manually with the `/claude-code-skills:<name>` form above — manual invocation always wins.

## Requirements

- **Claude Code v2.1.32 or higher.** Check with `claude --version`. The agent-teams primitive used by 5 of the skills landed in this version. See the [agent teams documentation](https://code.claude.com/docs/en/agent-teams) for background.
- **`CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1`** in your `settings.json` `env` block (or as a shell environment variable). Affects 5 of 22 skills:
  - `claude-md`
  - `design-review-team`
  - `explore-repo`
  - `handbook`
  - `readme`

  These skills hard-stop without the flag — the agent-teams architecture is foundational to how they explore a project.

  > **Note:** The agent-teams feature is experimental. If Anthropic renames the flag or stabilizes the feature in a future release, expect a follow-up release of this plugin. Bug reports against rename/deprecation are welcome.

The other 17 skills work without any of the above.

## What's in here

22 skills across five categories:

| Category | Skills |
|----------|--------|
| Review & adversarial critique | [`adversarial-review`](skills/adversarial-review/SKILL.md), [`scrutinize`](skills/scrutinize/SKILL.md), [`implementation-review`](skills/implementation-review/SKILL.md), [`system-design-review`](skills/system-design-review/SKILL.md), [`design-review-team`](skills/design-review-team/SKILL.md) ↗, [`review-code`](skills/review-code/SKILL.md), [`review-plan`](skills/review-plan/SKILL.md), [`review-strategy`](skills/review-strategy/SKILL.md), [`review-writing`](skills/review-writing/SKILL.md) |
| Grounded documentation generation | [`readme`](skills/readme/SKILL.md) ↗, [`handbook`](skills/handbook/SKILL.md) ↗, [`claude-md`](skills/claude-md/SKILL.md) ↗ |
| Repo exploration & analysis | [`explore-repo`](skills/explore-repo/SKILL.md) ↗, [`llm-reference`](skills/llm-reference/SKILL.md) |
| Workflow | [`git-hygiene`](skills/git-hygiene/SKILL.md), [`merge-branch`](skills/merge-branch/SKILL.md), [`exiting-worktrees`](skills/exiting-worktrees/SKILL.md), [`next-steps`](skills/next-steps/SKILL.md), [`making-recommendations`](skills/making-recommendations/SKILL.md), [`prompt-generator`](skills/prompt-generator/SKILL.md), [`format-export`](skills/format-export/SKILL.md) |
| Authoring | [`writing-principles`](skills/writing-principles/SKILL.md) |

↗ = depends on agent teams (see Requirements above).

Each skill's `SKILL.md` is the canonical specification — frontmatter declares when Claude should trigger it, and the body is the procedure Claude follows.

## Install

### Try it (clone + dev flag)

For a session-scoped trial without committing to install:

```
git clone https://github.com/jpsweeney97/claude-code-skills
claude --plugin-dir <path-to-clone>
```

The clone is permanent on your filesystem, but Claude only loads the plugin for the session you launched with `--plugin-dir`. Drop the flag next time and the skills disappear from that session.

### Install permanently (marketplace)

For ongoing access across all your sessions:

```
/plugin marketplace add jpsweeney97/claude-code-skills
/plugin install claude-code-skills@jpsweeney97-skills
```

Run those inside a Claude Code session. The first command points Claude at this repo's marketplace manifest; the second installs the plugin from it. After install, every skill is invokable as `/claude-code-skills:<name>`.

## Use a skill

Manual invocation always works:

```
/claude-code-skills:scrutinize
```

Or just describe what you want — the skill's frontmatter trigger phrases will route Claude to the right skill automatically. For example, "I want to scrutinize this design" or "tear this apart" will both trigger `scrutinize` if it's loaded.

## Contributing

Issues are welcome — bug reports, install problems, behavior questions, and feature suggestions. PRs are reviewed case-by-case; small fixes (typos, doc corrections, broken links, obvious bugs) merge fast. For larger changes, please open an issue first.

This public repo is canonical: bug fixes land here, not in any private dev-staging copy. See [CONTRIBUTING.md](CONTRIBUTING.md) for the full policy.

## License

[MIT](LICENSE).

## Author

JP Sweeney — [@jpsweeney97 on GitHub](https://github.com/jpsweeney97).
