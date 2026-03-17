# OpenClaw Bootstrap

Personal bootstrap prompts for OpenClaw agents.

## Structure

```
bootstrap/
├── 00-context.md           # General context (year, location, timezone)
├── 02-initialization.md    # Session startup message
├── 10-core-values.md       # Core principles
├── 11-red-lines.md         # Boundaries and safety rules
├── 39-architecture.md      # Instruction architecture
├── 40-memory-management.md # Memory and continuity
├── 50-learn-from-mistakes.md
├── 60-research-workflow.md
├── 70-group-chats.md
├── 80-tools.md             # Tool reference
├── 85-subagents.md         # Sub-agent strategy
├── 90-workspace-folders.md
├── 91-user.md              # User profile
├── 92-command-shorthands.md
└── 95-openclaw-paths.md    # Key paths
```

## Usage

Add to your `openclaw.json`:

```json
{
  "hooks": {
    "internal": {
      "entries": {
        "advanced-bootstrap": {
          "enabled": true,
          "sources": [
            {
              "path": "~/.openclaw/shared/bootstrap/*.md",
              "mode": "prepend"
            }
          ]
        }
      }
    }
  }
}
```

## License

MIT