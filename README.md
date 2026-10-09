# ComplyOnSite plugins

A plugin for Claude Code and Codex that adds the [ComplyOnSite MCP server](https://complyonsite.com/docs/mcp) and a short skill telling the assistant when to use it.

The server answers UK construction and waste questions: EWC waste codes, which waste paperwork a movement needs, links to start a waste transfer note, consignment note or RAMS with blank and worked-example PDFs, daily HAVS and noise exposure, first-aid cover, power tool vibration and noise, and HSE construction injury statistics. No account or key. It only reads; it never saves, signs or sends anything.

## Claude Code

```sh
claude plugin marketplace add complyonsite/plugins
claude plugin install complyonsite@complyonsite
```

Or inside a session: `/plugin marketplace add complyonsite/plugins`, then `/plugin install complyonsite@complyonsite`.

## Codex

```sh
codex plugin marketplace add complyonsite/plugins
codex plugin add complyonsite@complyonsite
```

## Without the plugin

Add the server on its own:

```sh
claude mcp add --transport http complyonsite https://mcp.complyonsite.com/mcp
codex mcp add complyonsite --url https://mcp.complyonsite.com/mcp
```

Other clients, limits and privacy: [complyonsite.com/docs/mcp](https://complyonsite.com/docs/mcp).

## What is in it

```
.claude-plugin/marketplace.json                 marketplace (read by Claude Code and Codex)
plugins/complyonsite/.claude-plugin/plugin.json Claude Code manifest
plugins/complyonsite/.codex-plugin/plugin.json  Codex manifest
plugins/complyonsite/.mcp.json                  the server address
plugins/complyonsite/skills/complyonsite/       when to use each tool
```

Problems or wrong answers: [hello@complyonsite.com](mailto:hello@complyonsite.com?subject=MCP%20plugin).
