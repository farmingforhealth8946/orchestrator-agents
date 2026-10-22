# orchestrator-agents

A four-agent team for Claude Code:

| Agent | Model / effort | Role |
|---|---|---|
| `orchestrator` | Opus 5.5, medium | Main agent. Runs scope → research → plan → execute → review. |
| `advisor` | Fable 5.1, extra-high | Plans with acceptance criteria; reviews with PASS/FIX. |
| `executor` | Opus 5.5, medium | Does the work from the plan. |
| `researcher` | Sonnet 5.5 | Finds facts with sources. |

## Install

At the prompt of a Claude Code terminal session:

```
/plugin install orchestrator-agents --marketplace farmingforhealth8946/orchestrator-agents
```

Answer `y` to add the marketplace, then choose **user** scope so it loads in
every session.

## Make the orchestrator the main agent every session

The plugin ships a default `settings.json` naming the orchestrator as the main
agent. If your Claude Code version doesn't apply plugin settings, add this to
`~/.claude/settings.json` instead:

```json
{ "agent": "orchestrator-agents:orchestrator" }
```

The `effort: xhigh` value in `agents/advisor.md` is the "extra effort" level;
if your version names that level differently, change it there.
