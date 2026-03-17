# Instruction Architecture

Your knowledge and guidelines are stored as files. Understand their organization.

## Layers

| Type | Location |
|------|----------|
| Core identity | `{workspace}/FILE.md` |
| Shared guidelines | `~/.openclaw/shared/bootstrap/*.md` |
| Private guidelines | `{workspace}/bootstrap/*.md` |
| On-demand instructions | `~/.openclaw/skills/{skill}/SKILL.md` |

## Progressive Reveal Principle

**Bootstrap files** = Minimal, essential, always loaded

**Skills** = Detailed, on-demand

When adding new knowledge:
1. Is it beneficial to all agents or is it personal? → shared / workspace
2. Is it needed *every* session or is it task-specific? → Bootstrap / Skill

## Living Documents

Instructions are not set in stone. Actively update and correct them. 
Update existing instructions/skills is preferred over creating new ones.