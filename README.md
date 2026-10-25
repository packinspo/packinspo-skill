# Packinspo for AI agents

Give your AI packaging taste. This repository connects Claude Code, Codex, Cursor, Gemini CLI and other agents to [Packinspo](https://packinspo.com), a free library of real, shipped packaging from beauty, food and drink brands, and teaches them to research before they design.

It contains:

- **The Packinspo MCP server** (`https://packinspo.com/mcp`): search curated packaging references and researched pack styles, read full studies, and export a style as PACK.md, design tokens, CSS variables or a Tailwind theme. Free, read-only, no account and no API key.
- **The `packinspo-research` skill** (`skills/packinspo-research/`): a research-first method for packaging work. Frame the brief, search wide then narrow, read the studies, extract patterns instead of copying, commit to a direction, check before handoff.

## Install

### Claude Code

```
/plugin marketplace add packinspo/packinspo-skill
/plugin install packinspo@packinspo
```

Or only the MCP server:

```
claude mcp add --transport http packinspo https://packinspo.com/mcp
```

### Codex

Add to `~/.codex/config.toml`:

```toml
[mcp_servers.packinspo]
url = "https://packinspo.com/mcp"
```

### Cursor

Add to `.cursor/mcp.json`:

```json
{ "mcpServers": { "packinspo": { "url": "https://packinspo.com/mcp" } } }
```

### VS Code

Add to `.vscode/mcp.json`:

```json
{ "servers": { "packinspo": { "type": "http", "url": "https://packinspo.com/mcp" } } }
```

### Gemini CLI

```
gemini extensions install https://github.com/packinspo/packinspo-skill
```

### Claude (web and desktop), ChatGPT and other clients

Add a custom connector with the URL `https://packinspo.com/mcp`. Clients that only speak stdio can use `npx -y mcp-remote https://packinspo.com/mcp`.

### The skill on its own

```
npx skills add https://github.com/packinspo/packinspo-skill --skill packinspo-research
```

Or copy `skills/packinspo-research/` (with its `references/` folder) into your agent's skills directory.

## Tools

| Tool | What it does |
|---|---|
| `search_styles` | Find pack styles by look, brand, category or format |
| `get_style` | Get a style as PACK.md (extended or compact), DTCG tokens, CSS variables or a Tailwind v4 theme |
| `search_packs` | Search curated references by category, format, confirmed material or colour |
| `get_pack` | Read a reference's full study, sources and photo URLs |
| `list_taxonomy` | List the categories, formats and materials used as filters |

## Try

- "Use Packinspo to find three bold snack pack styles, then write a PACK.md brief for my granola brand."
- "Find skincare references in amber glass on Packinspo and compare their label hierarchies."
- "Get the Graza pack style as CSS variables and build a product page in that style."

## Good to know

- Typefaces in Packinspo studies are lookalikes unless a source confirms them; colours are sampled from photographs.
- Images belong to their owners. Agents should use them as references, cite the Packinspo page and never reuse them as finished artwork.
- The MCP server is free with a fair-use limit per connection. Packinspo does not give regulatory advice.

## License

The skill and configuration files in this repository are MIT licensed. Packinspo's library content (studies, styles, photographs) is not covered by this license and remains with its owners.

Questions or corrections: hello@packinspo.com
