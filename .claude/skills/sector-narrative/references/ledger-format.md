# Story Ledger format

There are two ledgers with identical structure: Ledger A (`Story Ledger — CURRENT`) and Ledger B (`Story Ledger B — CURRENT`). Each is one Markdown document with these sections, in this order. Match the existing ledger's structure exactly, so the read-back check and future runs can parse it.

## Header

```
# Story Ledger — CURRENT
**Ledger version:** vN · **Updated:** YYYY-MM-DD · **Updated by:** <weekly|monthly|baseline> run
**Last monthly report:** <title>
**Last weekly scan:** <title>
**Coverage:** ...
```

## §1 Narrative thread

- The master thesis in one quoted line.
- The acts so far: one paragraph each. Add a new act only when the regime genuinely changes, at most once a quarter.
- The "working rule" that follows from the thesis.
- The biggest swing factor.
- **Questions next month's report must answer** (3–6 bullets).

Monthly runs rewrite this section. Weekly runs only append to the questions list, if something new comes up.

## §2 Story index

Table columns: `ID | Story | Sectors | Status | Importance (1–5) | Last major update`. Sort by importance, then recency.

ID prefixes:
- `POL-` policy/macro
- `SEMI-` semiconductors
- `AI-` AI & data-center infrastructure
- `ENRG-` energy
- `BANK-` banks (Ledger B)
- `CRYP-` crypto (Ledger B)
- `HLTH-` healthcare (Ledger B)

POL-, SEMI-, AI- and ENRG- stories live in Ledger A. A Ledger B story may cite a Ledger A ID ("AI-02 in Ledger A").

IDs are permanent. Never reuse one.

## §3 Stories

One block per story:

```
### <ID> · <Title>
- **Status:** ... · **Importance:** n · **Since:** YYYY-MM-DD · **Sectors:** ...
- **Thesis:** 1–3 sentences: what the story is and why it matters economically.
- **Key events:** dated, newest last, each tagged [V]/[B]; keep ≤ 12 bullets (compress older ones)
- **Policy levers:** who in government can move this, and how
- **Beneficiaries:** Company (TICKER) — order — mechanism [tags]
- **Pressured:** Company (TICKER) — mechanism
- **Signposts:** Confirm: ... / Break: ...
- **What could come next:** hypotheses, labelled as such
- **Sources:** outlet + date, short
```

## §4 Prediction register

Table columns: `ID | Made | Prediction | Story | Check by | Status`. Prediction IDs are P-001… in Ledger A and P-101… in Ledger B.
- Status values: `Open`, `Hit`, `Miss`, `Partial`, `Void`. Add a one-line evidence note when graded.
- Keep graded rows for 6 months, then move them to a one-line tally under the table.
- The tally line reads like this: `Hit rate (graded): x/y`.

## §5 Policy & catalyst calendar

Table columns: `Date | Event | Stories`. Drop past events once a report has reflected them. Write `(verify)` where a date is unconfirmed.

## §6 Candidate stories

Bullets: possible big stories that don't yet pass the big-story test, each with what would promote it.

## §7 Archive

One line per resolved story: `ID · Title · resolved YYYY-MM · outcome · lesson`.
