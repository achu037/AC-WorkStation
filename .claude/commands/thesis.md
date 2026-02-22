# /thesis — Create or Update an Investment Thesis
#
# Usage: /thesis <asset> <direction> <conviction>
#
# Example: /thesis NVDA long 8
#          /thesis BTC long 6
#          /thesis TSLA short 4

Parse $ARGUMENTS for: asset (ticker or name), direction (long/short), conviction (1-10).

## Step 1 — Check for Existing Thesis

Check `knowledge-base/research/theses/` for an existing file for this asset
(try `<asset-lowercase>.md`). If one exists, present its current state and ask
whether to update it or create a new entry.

## Step 2 — Gather Context

Before writing, read:
- `knowledge-base/context/active-context.md` — current focus and related open questions.
- The relevant domain summary in `knowledge-base/context/domain-summaries/`.
- Any existing watchlist entry for this asset.

## Step 3 — Draft the Thesis

Create `knowledge-base/research/theses/<asset-lowercase>.md` using the template
at `knowledge-base/templates/thesis.md`.

Pre-fill with:
- `asset`, `direction`, `conviction` from $ARGUMENTS.
- `opened` and `updated`: today's date.
- `status`: `active` if conviction ≥ 5, otherwise `watching`.

Then **suggest** content for each section based on your knowledge:
- **Thesis Statement:** Propose a 1-2 sentence statement for the user to approve or edit.
- **Key Drivers:** List 3-5 drivers you'd expect for this asset/direction.
- **Bull Case:** 2-3 points supporting the direction.
- **Bear Case:** 2-3 risks to the thesis.
- **Entry / Exit Criteria:** Suggested entry zone, stop level, and target.

Present these suggestions clearly and wait for the user to confirm, edit, or override before writing the final file.

## Step 4 — Save and Update Context

After the user approves:
1. Write the thesis file.
2. Update `knowledge-base/context/active-context.md`:
   - Add the thesis to "Active Theses" with format: `[[<asset-lowercase>]] — <direction>, conviction <X>/10`.

## Step 5 — Confirm

Report: "Thesis created: `research/theses/<asset>.md`. Conviction: <X>/10. Status: <active/watching>."
