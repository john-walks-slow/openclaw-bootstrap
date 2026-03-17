# Tools Reference

## Service Control

```bash
q serve    # Start all
q halt     # Stop all
q status   # Show status
q <name>   # Toggle service
```

→ See skill: `services` for details, adding services, PM2 commands

## Termux

→ See skill: `termux` for package management, Termux-API, device integration

## Web Search

Local SearXNG on port 8889:
```bash
curl -s "http://127.0.0.1:8889/search?q=QUERY&format=json" | jq .
```

## Models

| Model | Use |
|-------|-----|
| qwen3.5-plus | Fast subtasks |
| kimi-k2.5 | Creative, conversational |
| glm-5 | Research, coding |

## Sub-Agents

Background tasks with isolated context. Use for heavy work, research, coding.

```bash
sessions_spawn({ task: "...", model: "bailian/qwen3.5-plus" })
sessions_spawn({ task: "...", runtime: "acp", agentId: "codex" })  # Codex/Claude Code
subagents({ action: "list|steer|kill" })
```

→ See: `85-subagents.md` for **when** to spawn (strategy, context discipline)

## Gateway Config (Critical)

⚠️ Flawed config = restart failure. Follow strictly.

**Protocol:**
1. Lookup schema: `gateway({ action: "config.schema.lookup", path: "agents.defaults" })`
2. Validate: `openclaw doctor --non-interactive`
3. Apply: `gateway({ action: "config.patch", raw: { ... } })` — auto-restarts

**Correct usage:**
```javascript
// ✅ Use "raw" for partial updates (merges with existing config)
gateway({ action: "config.patch", raw: { agents: { defaults: { model: "bailian/glm-5" } } } })

// ❌ NEVER call config.patch without "raw" parameter
```

**Manual restart (if needed):**
```bash
pm2 restart gateway    # Gateway is managed by PM2
```

**Full recovery (last resort):**
```bash
pm2 restart gateway && openclaw doctor
```