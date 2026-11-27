# KirakuStore for your AI tools

Connect your AI tools to your [KirakuStore](https://kirakustore.com) library. Your tools read your best-ranked, healthy prompts, snippets and links, save new ones, and mark what helped so the ranking keeps improving.

KirakuStore uses MCP, an open standard. This repository holds the plugin for Claude Code. Every other tool connects with a short setup shown inside KirakuStore (see "Other AI tools" below).

## Install in Claude Code

```
/plugin marketplace add ArcVielLouvent/kiraku-store-plugin
/plugin install kirakustore@kiraku-store
```

1. In KirakuStore open **AI tools** and create a token. Choose what it may do: read only, write only, or both.
2. Set it in your environment: `export KIRAKU_TOKEN=kk_...`
3. Restart Claude Code. The `kirakustore` server and the `kiraku-context` skill are now available.

Updates arrive with `/plugin marketplace update kiraku-store`.

## Other AI tools

Cursor, VS Code, Windsurf, Cline, Zed, Gemini CLI, Codex CLI and Claude Desktop each have a ready-to-copy setup in KirakuStore under **AI tools**. There is also a universal prompt: paste it into any AI tool and it sets the connection up itself.

The plugin format in this repository is specific to Claude Code. Chat apps that only offer connectors, such as web versions of AI assistants, need a remote connector with sign-in. That is not available yet.

## Access levels

| Token | What your AI can do |
|---|---|
| Read only | Search and read items, see tags, health and shortcuts |
| Write only | Save and update items, verify them, mark them used |
| Read and write | Everything. The browser extension needs this |

A tool only sees the tools its token allows, and the database refuses anything else.

## What the server offers

| Tool | Needs | Purpose |
|---|---|---|
| `get_top_items` | read | Best-ranked healthy items, optionally for one tag |
| `search_items` | read | Search items by words |
| `get_item` | read | One item in full |
| `list_items` | read | Browse in ranking order by tag or kind |
| `list_tags` | read | Tags with item counts and top items |
| `get_health_summary` | read | Library health and items that need attention |
| `list_shortcuts` | read | Your text shortcuts |
| `save_item` | write | Save a new item. Secrets are hidden automatically |
| `update_item` | write | Change fields of an item |
| `record_use` | write | Mark an item as useful, which raises its rank |
| `verify_item` | write | Mark an item healthy again |
| `delete_item` | write | Delete an item. Needs `confirm: true` |

## Security

The token is yours alone. Create one per tool and revoke it any time from KirakuStore. Never commit it to a repository. Your token should never be pasted into a chat.

## License

MIT. See `LICENSE`.
