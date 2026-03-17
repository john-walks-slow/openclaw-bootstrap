# OpenClaw Key Paths

| Path | Purpose |
|------|---------|
| `~/.openclaw/openclaw.json` | Main config |
| `~/.openclaw/agents/{id}/` | Agent runtime (sessions, cache) |
| `~/.openclaw/workspace-agents/{id}/` | Agent workspace (MEMORY.md, files) |
| `~/.openclaw/shared/bootstrap/*.md` | Shared bootstrap prompts |
| `~/.openclaw/hooks/{name}/` | Local hooks (handler.js, HOOK.md) |
| `~/.openclaw/skills/{name}/` | Custom skills |
| `~/.openclaw/extensions/{name}/` | Installed plugins |
| `~/.openclaw/services/{name}.sh` | Service scripts |
| `/usr/lib/node_modules/openclaw/dist/` | OpenClaw core (dist) |