# KirakuStore for your AI tools

Connect your AI tools to your [KirakuStore](https://kirakustore.com) library. Your tools read your best-ranked, healthy prompts, snippets and links, and mark them as useful so the ranking keeps improving.

KirakuStore uses MCP, an open standard. This repository holds the plugin for Claude Code. Every other tool connects with a short setup shown inside KirakuStore (see "Other AI tools" below).

## Install in Claude Code

```
/plugin marketplace add ArcVielLouvent/kiraku-store-plugin
/plugin install kirakustore@kiraku-store
```

1. In KirakuStore open **AI tools** and create a token.
2. Set it in your environment: `export KIRAKU_TOKEN=kk_...`
3. Restart Claude Code. The `kirakustore` server and the `kiraku-context` skill are now available.

Updates arrive with `/plugin marketplace update kiraku-store`.

## Other AI tools

Cursor, VS Code, Windsurf, Cline, Zed, Gemini CLI, Codex CLI and Claude Desktop each have a ready-to-copy setup in KirakuStore under **AI tools**. There is also a universal prompt: paste it into any AI tool and it sets the connection up itself.

The plugin format in this repository is specific to Claude Code. Chat apps that only offer connectors, such as web versions of AI assistants, need a remote connector with sign-in. That is not available yet.

## What the server offers

| Tool | Purpose |
|---|---|
| `get_top_items` | Your best-ranked healthy items, optionally for one tag |
| `search_items` | Search your items by words |
| `record_use` | Mark an item as useful, which raises its rank |

## Security

The token is yours alone. Create one per tool and revoke it any time from KirakuStore. Never commit it to a repository. Your token should never be pasted into a chat.

## License

MIT. See `LICENSE`.
