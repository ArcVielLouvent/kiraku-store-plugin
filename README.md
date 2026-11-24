# KirakuStore plugin marketplace

Connect your AI coding tools to your [KirakuStore](https://kirakustore.com) library. Your tools read your best-ranked, healthy prompts, snippets and links, and mark them as useful so the ranking keeps improving.

## Install in Claude Code

```
/plugin marketplace add ArcVielLouvent/kiraku-store-plugin
/plugin install kirakustore@kiraku-store
```

1. In KirakuStore open **Ranking → Connect your AI tools** and create a token.
2. Set it in your environment: `export KIRAKU_TOKEN=kk_...`
3. Restart Claude Code. The `kirakustore` server and the `kiraku-context` skill are now available.

Updates arrive with `/plugin marketplace update kiraku-store`.

## Other tools

Cursor, VS Code, Windsurf, Cline, Zed, Gemini CLI, Codex CLI and Claude Desktop are covered with ready-to-copy setup snippets inside KirakuStore under **Ranking → Setup**.

## What the server offers

| Tool | Purpose |
|---|---|
| `get_top_items` | Your best-ranked healthy items, optionally for one tag |
| `search_items` | Search your items by words |
| `record_use` | Mark an item as useful, which raises its rank |

## Security

The token is yours alone. Create one per tool and revoke it any time from KirakuStore. Never commit it to a repository.
