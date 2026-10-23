# orchestrator-agents

A four-agent team for Claude Code:

| Agent | Model / effort | Role |
|---|---|---|
| `orchestrator` | Opus 5.5, medium | Sizes the task, then runs scope → research → plan → execute → check, using only the agents it needs. |
| `advisor` | Fable 5.1, extra-high | Plans with acceptance criteria. |
| `executor` | Opus 5.5, medium | Does the work from the plan. |
| `researcher` | Sonnet 5.5 | Finds facts with sources. |

## Install

At the prompt of a Claude Code terminal session:

```
/plugin install orchestrator-agents --marketplace farmingforhealth8946/orchestrator-agents
```

Answer `y` to add the marketplace, then choose **user** scope so it loads in
every session.

## Opt in per session

A `SessionStart` hook asks at the start of each new chat whether to use the
orchestrator ruleset. Say yes to load `agents/orchestrator.md` for that
session; say no to work normally. To always use it instead, add this to
`~/.claude/settings.json`:

```json
{ "agent": "orchestrator-agents:orchestrator" }
```

The `effort: xhigh` value in `agents/advisor.md` is the "extra effort" level;
if your version names that level differently, change it there.
