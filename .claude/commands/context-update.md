# /context-update — Re-synthesise the Context Layer
#
# Usage: /context-update           (updates all domains)
#        /context-update <domain>  (updates one domain: equities, crypto, macro, commodities)
#
# Example: /context-update crypto
#          /context-update

Determine scope from $ARGUMENTS:
- If a domain name is provided, update only that domain's summary.
- If empty, update all four domain summaries and `active-context.md`.

## For Each Domain in Scope

### Read Source Files

1. All files in `knowledge-base/domains/<domain>/`.
2. `knowledge-base/research/watchlists/<domain>.md` (if it exists).
3. Any files in `knowledge-base/research/theses/` tagged with this domain.
4. Recent journal entries in `knowledge-base/research/journal/` related to this domain.

### Synthesise

Write an updated `knowledge-base/context/domain-summaries/<domain>.md` with:

- `last_synthesised`: today's date.
- `source_files`: list of files read.
- **Watchlist Snapshot:** current assets tracked with direction and key trigger.
- **Analytical Framework:** how analysis is approached for this domain.
- **Active Themes:** top 3-5 themes currently being tracked.
- **Key Indicators:** most important metrics to watch.
- **Cross-Domain Links:** `[[wikilinks]]` to related domain summaries.
- **Gaps:** what's missing, underdeveloped, or needs more research.

Keep each summary under 80 lines. Optimise for fast Claude parsing, not human readability.

## Update active-context.md (always, regardless of scope)

After updating domain summaries:
- Update "Current Focus" if the notes suggest a shift.
- Carry over any open questions found in source files that aren't already listed.
- Add a session log entry: `| YYYY-MM-DD | Context re-synthesised for: <domains> |`

## Report

Output:
```
Updated: [list of files written]
Key changes: [1-2 sentence summary of what changed vs. previous version]
```
