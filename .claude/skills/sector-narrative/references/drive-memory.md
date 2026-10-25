# Drive memory: locations and save procedure

All memory lives in the user's Google Drive (Google Drive connector, `mcp__Google_Drive__*`).

| Item | Drive ID |
|---|---|
| Root folder `Sector Narratives` | `1xJtv5JGR6eBP0beQM_m7bF0FO3m_8Wwk` |
| `Monthly Reports` folder | `1clhRM53SrPEkU5pTVoAxgoGVzHXgmefx` |
| `Weekly Scans` folder | `1r0e5_K1uY4VMy2hjT86sTCB8MWmyjn2X` |
| `Ledger History` folder | `1DWYo9Pf80nEsQlG73ELfZK85hgXAr5ug` |
| Ledger v1 (2026-10-25, archived in Ledger History) | `1ID7M6JzgD-aAX2s6eiOGvfZ-oFfv4ds6ryIexmUx4PA` |
| Baseline report (2026-10) | `15CPr8iMFubeNEvUP3jvz0LhV8DNPfHsvyHxPTg6V6YI` |

The ledger's file ID changes with every version. Always **find it by title**; never hard-code the latest ID.

## Reading

- **Current ledger:** `search_files` with
  `title = 'Story Ledger — CURRENT' and parentId = '1xJtv5JGR6eBP0beQM_m7bF0FO3m_8Wwk'`.
  - Exactly one result is expected.
  - If there are two, use the most recently modified one and say so in the reply.
  - If there are none, look for a `(pending)` title (a crashed run), and read the newest file in `Ledger History`. Stop and tell the user rather than rebuilding.
- **Last monthly report:** `search_files` with `parentId = '1clhRM53SrPEkU5pTVoAxgoGVzHXgmefx'` and take the newest `modifiedTime`.
- **Weekly scans since then:** `parentId = '1r0e5_K1uY4VMy2hjT86sTCB8MWmyjn2X' and createdTime > '<last monthly createdTime>'`.
- Read each with `read_file_content`. Large reads may be saved to a file; read that file fully.

## Writing

The connector cannot edit a document in place. It can only create files and change their metadata. So every run writes a **new version**:

1. Write the full new ledger as Markdown in the scratchpad first. Bump the `Ledger version` and `Updated` lines.
2. `create_file`:
   - title `Story Ledger — v<N+1> (pending)`;
   - `parentId` = root;
   - `contentMimeType: text/markdown`;
   - `textContent` = the whole ledger. Markdown converts to a formatted Google Doc.
3. `read_file_content` on the new file. Check that the number of `### <ID> ·` story headers equals the story-index row count, and that the file ends with the Archive section. If not, trash the pending file and stop with an error. Do not touch the old ledger.
4. `update_file` on the old ledger: title `Story Ledger — v<N> (<YYYY-MM-DD>)`, `parentId` = Ledger History.
5. `update_file` on the new file: title `Story Ledger — CURRENT`.
6. Create the report doc the same way (Markdown → Doc):
   - monthly: in Monthly Reports, titled `Sector Narrative — YYYY-MM`;
   - weekly: in Weekly Scans, titled `Weekly Scan — YYYY-Www (MM-DD → MM-DD)`.
7. Return the `viewUrl`s.

Never trash a previous ledger version. History is part of the memory.

## Formatting notes

- Markdown headings, bold, lists and tables convert cleanly. Code blocks and ASCII diagrams don't: use bullet chains ("A → B → C") instead.
- Keep tables to 6 or fewer columns so they stay readable in Docs.
