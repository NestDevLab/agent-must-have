# nestdev must-have

Curated OpenPack meta-packages for baseline agent rules and skills. These packs ship no resources of their own; each profile aggregates selected resources from the NestDev-maintained `github:Yehonal/agent-toolkit` fork, `github:NestDevLab/agent-core-toolkit-public`, and selected external skill sources.

## Profiles

| Profile | Registry name | Source ref | Use when |
|---|---|---|---|
| Core | `nestdev-must-have-core` | `github:NestDevLab/agent-must-have#core` | You want only the essential conduct, documentation, self-improvement, and context-audit baseline. |
| Standard | `nestdev-must-have-standard` | `github:NestDevLab/agent-must-have#standard` | You want Core plus the NestDev code-review and task-planning skills. |
| Guarded | `nestdev-must-have-guarded` | `github:NestDevLab/agent-must-have#guarded` | You want Standard plus a Git read-only-by-default rule for stricter repository safety. |

`standard` is the default recommendation for development agents. Use `core` for lean shared fleets and `guarded` where Git mutations should require explicit approval.

## Install

After refreshing the Agentwheel registry:

```bash
agentwheel registry update
agentwheel install nestdev-must-have-core
agentwheel install nestdev-must-have-standard
agentwheel install nestdev-must-have-guarded
```

You can also install directly from GitHub refs:

```bash
agentwheel install github:NestDevLab/agent-must-have#core
agentwheel install github:NestDevLab/agent-must-have#standard
agentwheel install github:NestDevLab/agent-must-have#guarded
```

Requires agentwheel >= 0.9.

## What Each Profile Installs

### Core

| Resource | Type | From | Purpose |
|---|---|---|---|
| `rules/no-nonsense-comments.md` | Rule | `github:Yehonal/agent-toolkit` | Code comments are written for future readers with no process narration or self-reference. |
| `rules/self-contained-docs.md` | Rule | `github:Yehonal/agent-toolkit` | Planning and design documents must be concise and executable by a fresh agent session. |
| `rules/self-improve-on-correction.md` | Rule | `github:Yehonal/agent-toolkit` | When corrected on governed behavior, offer to persist the fix via `/self-improve`. |
| `skills/self-improve` | Skill | `github:Yehonal/agent-toolkit` | Capture user feedback into the skill or governing doc that should have prevented a mistake. |
| `skills/context-checkup` | Skill | `github:Yehonal/agent-toolkit` | Audit what auto-loads into an agent session's context window and suggest lean, reversible fixes. |

### Standard

Includes Core, plus:

| Resource | Type | From | Purpose |
|---|---|---|---|
| `skills/code-review` | Skill | `github:NestDevLab/agent-core-toolkit-public` | Review code, configuration, or documentation for correctness, safety, maintainability, and missing validation. |
| `skills/plan-task` | Skill | `github:NestDevLab/agent-core-toolkit-public` | Turn an ambiguous or multi-step request into an ordered, testable execution plan with assumptions and stop points. |
| `skills/grill-me` | Skill | `skillkit:github:mattpocock/skills` | Stress-test a plan or design through one-question-at-a-time interrogation, with a recommended answer for each question. |

### Guarded

Includes Standard, plus:

| Resource | Type | From | Purpose |
|---|---|---|---|
| `rules/git-read-only-by-default.md` | Rule | `github:FrancescoBorzi/agent-toolkit` | Git is read-only unless the user explicitly asks for a write action. |

## Customize

Fork this repo or copy the manifest and edit the `select` arrays. Any package can be a meta-package by declaring only `requires`.

## License

MIT.
