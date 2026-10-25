---
name: sector-narrative
description: Track the big stories in semiconductors, AI/data-center infrastructure and energy (plus the political and policy announcements that move them), keep a persistent Story Ledger in Google Drive so no big story is ever forgotten, and write a weekly light scan or a monthly narrative report that names the companies that benefit or get hurt and what could come next. Use when asked for the weekly sector scan, the monthly sector narrative, to update the story ledger, or to rebuild the baseline.
---

# Sector Narrative

The goal is a narrative that remembers. Every run starts from the **Story Ledger** in Google Drive, adds what changed, and saves a new version. Monthly reports open from last month's report and grade last month's predictions.

## Modes

| Invocation | What it does | Output |
|---|---|---|
| `weekly` | Scans the past 7 days, updates the ledger, and writes a short per-sector note on what changed and why it matters | `Weekly Scan — YYYY-Www` doc + new ledger version |
| `monthly` | One narrative report per sector (Energy, Semiconductors, AI Infrastructure), each continuing that sector's previous report | Three `<Sector> Narrative — YYYY-MM` docs + new ledger version |
| `sector <name>` | An on-demand narrative for one sector only, in the monthly format | A reply in chat (offer to save it as a doc) |
| `baseline` | Rebuilds the ledger from scratch over a stated window (default: since 2025-01-20). Only when the user asks, because it replaces the narrative thread | Baseline report + ledger v1 of a new series |
| `story <ID or topic>` | Deep-dive on one story, ad hoc | Reply in chat (and a ledger update if facts changed) |

If no mode is given, ask which mode. A scheduled run always names its mode.

## What the user reads vs. what the skill remembers

- **The ledger is internal memory.** It is dense on purpose: dated events, tags, signposts, sources.
- **Reports are for the user** and follow `references/monthly-report.md`:
  - narrative prose, one sector per doc;
  - named winners and losers, with reasons;
  - what comes next.
  - No macro section, no tags, no timelines.
- **Answer only the sector asked about.** If the user asks about energy, answer about energy.
- **The test of a report:** could the user have got it by reading headlines? If yes, it isn't done. The value is the interpretation, the second-order names, continuity across months, and graded calls.

## Non-negotiable rules

1. **Read memory first.** Read the current ledger before any research. For `monthly`, also read the latest monthly report and every weekly scan since it. Never write a report from a blank slate unless the mode is `baseline`.
2. **Never drop a story.** Stories change status: Emerging → Active → Escalating/Maturing → Dormant-watch → Resolved → Archive. A story with no news for 60+ days becomes Dormant-watch. It is not deleted. Every story in the index appears in every monthly report, at least as one line.
3. **Every story carries its politics.** Each update names the policy lever involved: executive orders, tariffs (Section 232/122/301), export controls (BIS), sanctions (OFAC), Fed, FERC/NRC/EPA, Congress, state legislatures, foreign governments. Political announcements are first-class developments, not background.
4. **Name companies with a mechanism.** Every company mention gives its ticker, its order (1st/2nd/3rd), *why* the story moves its economics, and *what would break the thesis*. No ticker lists without reasons.
5. **Separate evidence from inference.**
   - Tag facts **[V]** (verified this run, with source and date) or **[B]** (background knowledge). Tag ticker-exposure lists **[map]**: they are analytical judgements, not reported facts.
   - Mark single-source or aggregator figures "(secondary)" or "(single source)".
   - Label forward-looking statements as hypotheses or scenarios.
   - Never invent numbers, dates or quotes. Leave a gap and list it under "Coverage gaps".
6. **Make calls checkable.** Every monthly report registers 5–10 predictions, each with a check-by date. It grades every prediction whose date has passed as Hit/Miss/Partial/Void, with one line of evidence. Track the running hit rate in the ledger.
7. **Look past the headline.** For each big story, ask who supplies the supplier, who loses, which bottleneck comes next, and which other ledger stories it links to. Obvious beneficiaries are usually priced in. The value is in 2nd- and 3rd-order links.
8. **Not advice.** Reports describe exposure and scenarios. They never say buy or sell.

## Workflow (weekly and monthly)

1. **Load memory.** Follow `references/drive-memory.md`: find and read `Story Ledger — CURRENT`. If its title shows `(pending)`, another run is mid-write: stop and report. For `monthly`, also load the last monthly report and all weekly scans since.
2. **Plan the research.** Build the query list from `references/research-playbook.md`:
   - every Active/Escalating story's signposts;
   - the catalyst calendar for the window;
   - open predictions due in the window;
   - the policy sources sweep;
   - the deals and capital-markets sweep (M&A, IPOs, mega-financings);
   - a broad "what's new" sweep per sector to catch stories the ledger doesn't have yet.
3. **Research.**
   - Weekly: about 12–20 searches.
   - Monthly: about 25–40 searches.
   - Prefer primary sources (filings, agency releases, Federal Register, company IR). Record the date of every fact.
4. **Update the ledger** (format in `references/ledger-format.md`):
   - append dated events to existing stories;
   - change status and importance where warranted;
   - add new stories when they meet the "big story" test below, or add them to Candidates;
   - roll the calendar forward;
   - update the prediction register;
   - for `monthly`, rewrite §1 Narrative thread.
5. **Write the output** using `references/weekly-scan.md` or `references/monthly-report.md`.
6. **Save** both documents per `references/drive-memory.md` (versioned ledger, read-back check).
7. **Reply** with 3–5 lines: the headline change, any story whose status changed, predictions graded, and links to the docs.

### The "big story" test

Promote a candidate to the ledger when at least two of these hold:
- It changes revenue, costs or capital costs for a group of companies, not just one.
- A government or central bank is a principal actor.
- It is likely to matter for 3+ months.
- It links to two or more existing ledger stories.

Otherwise keep it under Candidates. Re-check candidates every monthly run.

## Coverage

Core sectors:
- **Semiconductors:** compute, memory, foundry, equipment, materials.
- **AI & data-center infrastructure:** hyperscalers, neoclouds, AI labs and their financing, power and cooling, networking, data-center real estate, AI's disruption of software.
- **Energy:** oil and gas, refining, LNG, power/utilities/IPPs, nuclear and fuel cycle, renewables and storage, grid equipment.
- **Cross-cutting policy:** tariffs, export controls, sanctions, Fed/rates, US–China, elections, state energy/data-center law.

The company universe and source list are in `references/research-playbook.md`. Expand coverage only if the user asks; depth beats breadth.

## Ledger hygiene

- Keep the ledger under ~80 KB so a single read returns it whole.
- When it grows past that, compress each Resolved story to one line in §7 Archive (what happened, what we learned) and trim old event bullets to the 5 most important.
- The full history survives in `Ledger History`.
