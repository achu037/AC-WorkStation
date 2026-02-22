# /status — Knowledge Base Overview
#
# Usage: /status
#
# Gives a full snapshot of the knowledge base state.

## Step 1 — Read Active Context

Read `knowledge-base/context/active-context.md` and extract:
- Current Focus
- Recent Insights (last 5)
- Open Questions
- Active Theses

## Step 2 — Count Files

Report file counts:
- `knowledge-base/domains/equities/` — N notes
- `knowledge-base/domains/crypto/` — N notes
- `knowledge-base/domains/macro/` — N notes
- `knowledge-base/domains/commodities/` — N notes
- `knowledge-base/research/journal/` — N entries
- `knowledge-base/research/theses/` — N theses

## Step 3 — Active Theses Summary

Read all files in `knowledge-base/research/theses/`. For each, extract:
- Asset, direction, conviction, status, last updated.

Present as a table:

| Asset | Direction | Conviction | Status | Updated |
|-------|-----------|-----------|--------|---------|

## Step 4 — Recent Activity

Using file modification times or git log, identify:
- Files modified in the last 7 days.
- Most recently updated journal entry.

## Step 5 — Staleness Check

Read each `knowledge-base/context/domain-summaries/*.md` and check `last_synthesised`.
Flag any domain summary not updated in the last 7 days:
> ⚠️ `<domain>` summary last synthesised <N> days ago — consider running `/context-update <domain>`.

## Step 6 — Recommendations

Based on the above, suggest 2-3 actions:
- Stale domains that need a context update.
- Open questions that haven't been researched.
- Theses with no recent status log entry.
- Watchlist items that haven't been reviewed recently.

Format the full output clearly with headers. Keep it scannable.
