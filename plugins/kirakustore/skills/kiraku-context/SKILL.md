---
name: kiraku-context
description: Use before writing code, prompts, commands or documentation when the user may already have a saved, ranked example in KirakuStore, such as an auth snippet, a SQL pattern, a system prompt or a team rule. Also use when the user asks to find or reuse something they saved.
---

# KirakuStore context

The user keeps their best prompts, snippets, commands and links in KirakuStore, ranked by real use and health.

## When to use it

- Before writing something the user has probably done before, call `get_top_items` with a fitting lowercase tag (for example `auth` or `sql`). Follow the top item's style unless the user says otherwise.
- When the user asks to find something they saved, call `search_items` with a few distinctive words.
- After you actually use an item and it helped, call `record_use` with its id. Never call it for items you did not use.

## Rules

- Prefer the user's own ranked item over inventing a new pattern. Say which item you followed.
- Ask for at most 1 to 3 items. More context makes answers worse, not better.
- If a tool fails or returns nothing, continue without it and say so briefly.
- Never print the token or ask the user to paste it into chat. It lives in the `KIRAKU_TOKEN` environment variable.
