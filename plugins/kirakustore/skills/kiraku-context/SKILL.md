---
name: kiraku-context
description: Use before writing code, prompts, commands or documentation when the user may already have a saved, ranked example in KirakuStore, such as an auth snippet, a SQL pattern, a system prompt or a team rule. Also use when the user asks to find, reuse, save, update, tidy or check something in their KirakuStore library.
---

# KirakuStore context

The user keeps their best prompts, snippets, commands, notes and links in KirakuStore, ranked by real use and health. The token decides what you may do: read only, write only, or both. Tools you are not allowed to use are simply not listed.

## Reading

- Before writing something the user has probably done before, call `get_top_items` with a fitting lowercase tag (for example `auth` or `sql`). Follow the top item's style unless the user says otherwise.
- To find something specific, call `search_items` with a few distinctive words, then `get_item` for the full text.
- To browse, use `list_tags` and `list_items`. Use `get_health_summary` to see what needs attention, and `list_shortcuts` to see the user's text shortcuts.

## Writing

Change the library only when the user asked.

- `save_item` saves something new. Choose a short title and a lowercase tag.
- `update_item` changes fields of an existing item. Send only what changes.
- `verify_item` marks an item healthy after you confirmed that it still works.
- `delete_item` deletes for good. Only with a clear request, and set `confirm` to true.
- After you actually use an item and it helped, call `record_use` with its id. Never call it for items you did not use.

## Rules

- Prefer the user's own ranked item over inventing a new pattern. Say which item you followed.
- Ask for at most 1 to 3 items at a time. More context makes answers worse, not better.
- If a tool fails, or says the token does not allow it, continue without it and tell the user briefly. They can create a token with the right access in KirakuStore under AI tools.
- Never print the token or ask the user to paste it into chat. It lives in the `KIRAKU_TOKEN` environment variable.
