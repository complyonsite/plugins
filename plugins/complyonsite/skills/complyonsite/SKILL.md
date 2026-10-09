---
name: complyonsite
description: UK construction and waste questions that the ComplyOnSite tools answer directly. Use for EWC or List of Waste codes for a skip, load or material; waste transfer notes, hazardous or special waste consignment notes and which paperwork a waste movement needs; RAMS for a job; daily hand-arm vibration (HAVS) or noise exposure from tools and times; first-aid cover for a site; how much a type of power tool vibrates or how loud it is; and HSE construction injury and death figures.
---

# ComplyOnSite tools

The `complyonsite` MCP server gives calculations and reference data for UK construction and waste work. It is anonymous and read-only.

## Which tool

| The person asks about | Tool |
|---|---|
| A code for a waste, skip, load or material; what a code means | `ewc_search` |
| Starting a waste transfer note, consignment note or RAMS; a template or example | `start_document` |
| Which paperwork a waste movement needs, by nation or document | `waste_paperwork` |
| Vibration exposure for one person from tools and times | `havs_daily_exposure` |
| Noise exposure from task levels and times, or a dosemeter | `noise_daily_exposure` |
| How many first-aiders or what course for a site or workplace | `first_aid_requirements` |
| How much a type of tool vibrates or how loud it is | `power_tool_types` |
| Construction deaths, injuries or ill health in Great Britain | `construction_injury_statistics` |

## How to use them

- Waste codes: search one to three material words at a time (“plasterboard”, “treated wood”), not the person's sentence. Search each material in a mixed load separately. If `match.quality` is `weak` or `none`, try the main material or a synonym rather than guessing.
- Waste notes: find the codes with `ewc_search`, then pass the chosen codes to `start_document`. A mirror entry needs an assessment before choosing between the hazardous and non-hazardous code; say so.
- HAVS: give each tool an HSE `category` (and `variant` where the category has several) when the person has no vibration figure. Use the tool's own m/s² figure when they have one. Time is trigger time.
- Noise: task levels are LAeq in dB(A). For noise at the ear, add the protector's SNR or H/M/L and each protected task's C-weighted level.
- If an answer depends on something the person has not said (the nation, how many people per shift, trigger time), make a sensible assumption, state it, and ask.

## Presenting answers

- Each result starts with a `summary`. Give the figure or code first, in plain words, then what it means for the person.
- Results include `calculatorUrl`, `url` or `downloads`. Show them as links: the calculator opens the same calculation to adjust; `start_document` links open the form with the codes or job filled in; `downloads` are a blank template and a worked example as PDFs.
- Keep each result's `limit` in the answer when it matters, for example that a code search is not a waste classification.
