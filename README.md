# nestdev must-have

A meta-package (OpenPack "pack") that installs a curated set of essential agent resources from multiple sources -- it ships no resources of its own.

## What it installs

| Resource | Type | From | Purpose |
|---|---|---|---|
| `rules/git-read-only-by-default.md` | Rule | `github:Yehonal/agent-toolkit` | Git is read-only unless explicitly asked for a write action. |
| `rules/no-nonsense-comments.md` | Rule | `github:Yehonal/agent-toolkit` | Code comments are written for future readers with no process narration or self-reference. |
| `rules/self-contained-docs.md` | Rule | `github:Yehonal/agent-toolkit` | Planning and design documents must be concise and executable by a fresh agent session. |
| `rules/self-improve-on-correction.md` | Rule | `github:Yehonal/agent-toolkit` | When corrected on governed behavior, offer to persist the fix via `/self-improve`. |
| `skills/self-improve` | Skill | `github:Yehonal/agent-toolkit` | Capture user feedback into the skill or governing doc that should have prevented a mistake. |
| `skills/context-checkup` | Skill | `github:Yehonal/agent-toolkit` | Audit what auto-loads into an agent session's context window and suggest lean, reversible fixes. |
| `skills/code-review` | Skill | `github:NestDevLab/agent-core-toolkit-public` | Review code, configuration, or documentation for correctness, safety, maintainability, and missing validation. |
| `skills/plan-task` | Skill | `github:NestDevLab/agent-core-toolkit-public` | Turn an ambiguous or multi-step request into an ordered, testable execution plan with assumptions and stop points. |

## Install

```bash
agentwheel install github:NestDevLab/agent-must-have
```

Requires agentwheel >= 0.9. The short registry name `nestdev-must-have` becomes available once the registry entry is merged:

```bash
agentwheel registry update && agentwheel install nestdev-must-have
```

## Customize

Fork this repo or copy the manifest and edit the `select` arrays.
Any package can be a meta-package by declaring only `requires`.

## License

MIT.
