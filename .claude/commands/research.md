# /research — Structured Research Session
#
# Usage: /research <topic>
#
# Example: /research BTC halving cycle
#          /research NVDA earnings Q4 2025
#          /research Fed rate cut timing

The topic to research is: **$ARGUMENTS**

## Step 1 — Gather Existing Context (do this first, before any web search)

Read these files in order:

1. `knowledge-base/context/active-context.md` — current focus and recent insights.
2. `knowledge-base/context/domain-summaries/` — identify which domain(s) the topic falls under and read the relevant summary file(s).
3. Search `knowledge-base/research/journal/` for any existing entries mentioning this topic (check filenames and frontmatter tags).
4. Search `knowledge-base/research/theses/` for any related active theses.
5. Check `knowledge-base/research/watchlists/` for related tracked assets.

## Step 2 — Present Existing Knowledge

Before researching, summarise:
- **What's already known:** key points from existing notes.
- **Related theses/watchlist items:** list with current status.
- **Prior open questions:** questions from previous sessions that this research might answer.
- **Knowledge gaps:** what's missing that the research should focus on.

## Step 3 — Conduct Research

Use web search and the fetch MCP server to gather current information.

Research principles (from `meta/preferences.md`):
- Primary sources first (SEC filings, central bank statements, on-chain data, official reports).
- Quantify — find numbers, not narratives.
- Note the source and date for every key data point.
- Cross-check claims against my existing notes; flag discrepancies.
- Identify confidence level: high / medium / low for each finding.

## Step 4 — Create Journal Entry

Create a new file at:
`knowledge-base/research/journal/YYYY-MM-DD-<slugified-topic>.md`

Use the template from `knowledge-base/templates/journal-entry.md`. Fill in all sections:
- **title:** research topic
- **date:** today's date
- **tags:** relevant domain tags + `journal`
- **assets:** any assets directly referenced
- **Key Questions:** the questions this session set out to answer
- **Analysis:** the data and reasoning (quantified, sourced)
- **Findings:** clear conclusions with confidence levels
- **Open Questions:** what remains unanswered
- **Action Items:** concrete next steps

## Step 5 — Suggest Follow-Ups

After presenting findings, recommend:
- Whether to create or update a thesis (`/thesis <asset> <direction> <conviction>`).
- Any watchlist entries to add or update.
- Open questions to track for the next session.
- Related domains to cross-check (e.g. macro implications of a crypto finding).
