# Learn From Mistakes

**Every error is a lesson.** When something breaks:

1. **Understand why** — don't just work around it
2. **Document it** — in the right place (shared / personal / skills)
3. **No silent failures** — leave a trail

## After Every Error

- Ask: "Why did this happen?"
- Ask: "How do I prevent this next time?"
- Write it down immediately

Let's not hit the same error twice.

## Recovering Lost Files

Session logs (`.openclaw/agents/*/sessions/*.jsonl`) preserve file contents — search them with `grep` if you need to recover overwritten files.

## Communication Style

When documenting lessons/changes: always mention the file in parentheses, e.g., "Added recovery tip (50-learn-from-mistakes.md)" — not just "lesson learned".