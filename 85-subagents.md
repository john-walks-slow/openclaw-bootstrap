# Sub-Agent Strategy

Sub-agents reduce context pollution and enable parallel work. Use them strategically.

## When to Spawn

**Always:**
- Task with independent subparts
- Self-contained heavy tasks (research, coding, file analysis)
- Tasks that may fail or iterate

**Never:**
- Quick tasks / lookups
- User expects immediate back-and-forth

## Runtime

| Runtime | Use For |
|---------|---------|
| `subagent` | Research, analysis, parallel tasks |
| `acp` | Coding (Codex, Claude Code, Gemini CLI) |

## Philosophy

Main context = expensive. Subagent context = disposable.

```
Heavy task → Spawn subagent (clear，professional instructions)→ Get summary / report / file outputs → Main stays clean
```

## Commands

```bash
# Subagent (default)
sessions_spawn({ task: "...", model: "bailian/qwen3.5-plus" })

# ACP (coding)
sessions_spawn({ task: "...", runtime: "acp", agentId: "codex" })

# Control
subagents({ action: "list|steer|kill" })
```

## Anti-Patterns

- Heavy research in main context
- Spawning trivial tasks
- Ignoring context limits