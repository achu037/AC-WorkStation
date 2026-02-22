# /learn — Extract and Persist Session Knowledge
#
# Usage: /learn
#        /learn <topic>   (focus extraction on a specific topic or area)
#
# Run at the end of a research session to capture what was learned.

You are updating the ClaudeOS knowledge base with insights from this session.
$ARGUMENTS will scope the extraction to a specific topic if provided; otherwise extract everything notable.

## Step 1 — Review the Session

Look at:
- The conversation so far in this session.
- Output of `git diff HEAD` and `git diff --cached` for file changes.
- List recently modified files in `knowledge-base/` (check timestamps if possible).

## Step 2 — Extract New Knowledge

Identify and categorise:

| Category | Examples |
|----------|---------|
| **New insights** | Conclusions reached, patterns identified, data points confirmed |
| **Corrections** | Anything the user corrected — what was wrong, what's correct |
| **New terminology** | Terms defined or used that aren't in the glossary |
| **Thesis changes** | New theses, conviction changes, closed positions |
| **Analytical frameworks** | New approaches or methods used |
| **Decisions & reasoning** | Choices made and why |

If $ARGUMENTS is provided, focus on insights related to that topic only.

## Step 3 — Persist to Files

Update each file only if there is something genuinely new to add:

**`knowledge-base/context/active-context.md`**
- Add new items to "Recent Insights" (keep the last 10; prune oldest).
- Update "Current Focus" if the session shifted attention.
- Add new items to "Open Questions" if questions arose and weren't answered.
- Update "Active Theses" if any thesis was created or closed.
- Add a one-line entry to "Session Log": `| YYYY-MM-DD | <1-sentence summary> |`

**`knowledge-base/context/domain-summaries/<domain>.md`**
- If significant domain-specific knowledge was gained, update the relevant summary.
- Re-read the source files for that domain before re-synthesising.
- Update `last_synthesised` date.

**`knowledge-base/meta/lessons-learned.md`**
- For each correction the user made, add: `YYYY-MM-DD — [Topic] — What was wrong → Correct approach.`

**`knowledge-base/meta/glossary.md`**
- For each new term, add a definition entry under the appropriate section.

## Step 4 — Report

Output a brief summary:
```
Updated X files: [list of filenames].
Key insights captured: [1-2 sentence summary of the most important things learned].
```

Do not update files if there is nothing genuinely new. Keep the signal high.
