# knowledge-base/CLAUDE.md

Local context for Claude Code when working inside the knowledge base directory.

## Two-Layer System

| Layer | Directories | Maintained by | Rules |
|-------|------------|--------------|-------|
| Human layer | `domains/`, `research/`, `meta/` | User (Obsidian) | Never modify unless explicitly asked |
| Machine layer | `context/` | Claude | Freely update to reflect latest knowledge |

## Rules

- **Never** modify files in `domains/`, `research/`, or `meta/` without explicit instruction.
- **Freely** update `context/active-context.md` and `context/domain-summaries/` at session end or when `/learn` is called.
- When updating a domain summary, always record `last_synthesised` and `source_files` at the top.
- If the user corrects something, add an entry to `meta/lessons-learned.md` before the session ends.
- New terms go in `meta/glossary.md`.

## File Conventions

- **Frontmatter:** All notes use YAML frontmatter (`---` delimited) with at minimum `title`, `tags`, `updated`.
- **Wikilinks:** Use `[[filename]]` for cross-references between notes (Obsidian-native).
- **Journal entries:** Filename pattern `YYYY-MM-DD-slug.md` in `research/journal/`.
- **Theses:** One file per asset in `research/theses/asset-name.md`.

## Templates

All templates are in `templates/`. Use them when creating new entries:
- `templates/journal-entry.md` — for new research journal entries.
- `templates/thesis.md` — for new investment theses.
- `templates/watchlist.md` — for new watchlist files.

## Tagging Taxonomy

Use consistent tags in frontmatter:

`equities` `crypto` `macro` `commodities` `thesis` `watchlist` `journal` `earnings` `technical-analysis` `fundamental-analysis` `risk` `position-sizing` `meta` `domain` `reference`

## Updating Domain Summaries

When re-synthesising a domain summary:
1. Read all files in the relevant `domains/<domain>/` directory.
2. Read `research/watchlists/<domain>.md` if it exists.
3. Read any active theses in `research/theses/` tagged with that domain.
4. Write a structured summary to `context/domain-summaries/<domain>.md`.
5. Update `last_synthesised` date and list all `source_files` consulted.
