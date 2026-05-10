# claude-code-skills

A curated collection of [Claude Code](https://code.claude.com) skills focused on rigorous review, decisions, and craft. Everything here is also installable via the Claude Code plugin marketplace.

## Namespacing

After install, every skill in this plugin is invocable under the `claude-code-skills` namespace:

```
/claude-code-skills:scrutinize
/claude-code-skills:system-design-review
/claude-code-skills:git-hygiene
```

This guarantees that names from this plugin can never collide with skills from other plugins or your own personal skills. Manual invocation always wins over auto-routing — if you ever want a specific skill, name it explicitly.

## What's in here

6 skills:

| Skill | Purpose |
|---|---|
| [`scrutinize`](skills/scrutinize/SKILL.md) | General-purpose adversarial pass — adapts to plans, code, writing, and strategy. |
| [`system-design-review`](skills/system-design-review/SKILL.md) | Architecture review via lens framework with stakes calibration. |
| [`git-hygiene`](skills/git-hygiene/SKILL.md) | Lane-based repo cleanup for cluttered git state and stale branches. |
| [`next-steps`](skills/next-steps/SKILL.md) | Strategic action planning with dependency mapping. |
| [`making-recommendations`](skills/making-recommendations/SKILL.md) | Decision framework with stakes calibration. |
| [`writing-principles`](skills/writing-principles/SKILL.md) | Risk-calibrated principle enforcement for instruction documents. |

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

This public repo is canonical: bug fixes land here, not in any private dev-staging copy. See [CONTRIBUTING.md](CONTRIBUTING.md) for the full policy, including the standalone-plugin design principle (no operational cross-references between this plugin and the companion `claude-code-agent-teams`).

## See also

- [`claude-code-agent-teams`](https://github.com/jpsweeney97/claude-code-agent-teams) — agent-team-powered companion plugin (documentation generators, exploration, deep architecture review). Requires Claude Code v2.1.32+ and `CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1`. This plugin is self-contained — installing the companion plugin is optional, not required.

## License

[MIT](LICENSE).

## Author

[JP Sweeney](https://github.com/jpsweeney97).
