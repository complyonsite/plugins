# ComplyOnSite — UK construction and waste tools

![ComplyOnSite](assets/logo.png)

Find candidate waste codes, understand paperwork requirements and estimate workplace exposure through eight tools from [ComplyOnSite](https://complyonsite.com/docs/mcp). Available in Claude apps, Cowork and Claude Code through the Claude Directory, and in Codex through this marketplace. The plugin connects to the ComplyOnSite MCP server and includes a skill that helps the assistant choose the right tool.

No ComplyOnSite account or API key is required. Tool requests are sent to ComplyOnSite's remote server. The tools are read-only: they do not save records, sign documents or submit anything to a regulator.

## What you can do

| Task | What the tools return |
|---|---|
| Search EWC / List of Waste codes | Candidate codes, descriptions and guidance on mirror entries |
| Choose waste paperwork | Requirements for waste transfer notes and hazardous or special waste consignment notes, by UK nation |
| Start a waste note or RAMS | Links to preparation forms, plus blank and worked-example PDFs |
| Estimate hand-arm vibration exposure | Daily exposure from tool vibration values and trigger times, compared with action and limit values |
| Estimate daily noise exposure | Exposure from task levels and durations, with separate action-value and hearing-protection limit checks |
| Plan first-aid cover | Guidance based on workplace risks, staffing and shift cover |
| Look up power-tool reference data | Vibration and noise figures by tool type |
| Explore HSE construction statistics | Retained Great Britain injury, fatality and ill-health figures with sources |

## Try asking

- “Find candidate EWC codes for separate plasterboard, timber and rubble wastes.”
- “What paperwork does a hazardous waste movement in Wales need?”
- “Estimate daily vibration exposure for a breaker used for 90 minutes and a grinder for 45 minutes.”
- “What first-aid cover should I plan for a construction site with 30 people per shift?”
- “Open a RAMS preparation form for installing plasterboard partitions.”

## Scope and limits

These tools support UK construction and waste decisions; they do not certify compliance or make legal decisions. Waste search results are candidates, not a waste classification. Mirror entries need an assessment before selecting a hazardous or non-hazardous code. Exposure estimates depend on the supplied values and working conditions and do not establish that work is safe.

Document tools provide preparation links and templates, not completed or issued records or a completed RAMS pack. The plugin does not check live waste-carrier registers, permits or exemptions, convert SDS files, or look up individual power-tool makes and models. HSE statistics are retained reference data, not a live feed. Results include relevant sources and limits.

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

## Publisher and support

Published by [ComplyOnSite](https://complyonsite.com). See the [documentation](https://complyonsite.com/docs/mcp), [support](https://complyonsite.com/support), [privacy policy](https://complyonsite.com/legal/privacy) and [terms of service](https://complyonsite.com/legal/terms). The plugin source is released under the [MIT licence](../../LICENSE).
