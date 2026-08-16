---
name: journal
description: Append a short free-text diary entry to JOURNAL.md describing what was just done and when. Use after finishing a piece of work, or when the user says "journal", "log this", "write it down", "update the journal", or asks what has been done so far.
---

# Journal

`JOURNAL.md` in the repo root is a diary. Newest entries at the top — insert new ones above the existing entries. Never rewrite history.

## Writing an entry

Get the timestamp from the shell (`date '+%Y-%m-%d %H:%M'`) — never guess it.

Format:

```markdown
## 2026-07-27 12:56
Swapped the polling loop for a websocket feed in `feed.py` — the REST endpoint
was rate-limiting during market open. Backtests still pass.
```

Rules:

- One heading with the timestamp, then 1-3 sentences of plain prose.
- Write what changed and *why*, not a file-by-file diff — the diff is in git.
- Mention files inline with backticks when it helps the reader find things.
- Note dead ends and things left unfinished; that context is the point.
- No bullet lists, no status tables, no "Summary/Next steps" sections.
- If nothing meaningful happened, write nothing.

## Reading

When asked what was done recently, read the top of `JOURNAL.md` rather than
scanning git history — the journal has the reasoning.
