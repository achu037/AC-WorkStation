# CLAUDE.md — ClaudeOS Master Context

## What Is This

ClaudeOS is a personal AI workstation for **investment research and software development**. This repo contains a knowledge base (notes, research, theses) and project workspaces. The knowledge base is also an **Obsidian vault** — the owner writes notes by hand, and Claude uses them as context.

This file is read automatically at the start of every Claude Code session.

---

## Repo Structure

```
AC-WorkStation/
├── knowledge-base/     # Notes + context; also an Obsidian vault
│   ├── research/       # Journal entries, theses, watchlists
│   ├── domains/        # Domain reference notes (equities, crypto, macro, commodities)
│   ├── context/        # AUTO-MAINTAINED by Claude — synthesised AI-readable summaries
│   ├── meta/           # Preferences, glossary, lessons learned
│   └── templates/      # Templates for new entries
├── projects/           # Code project workspaces (future)
├── packages/           # Shared tooling (future)
└── .claude/commands/   # Slash command prompts
```

`knowledge-base/context/` is the machine-maintained layer. Everything else in `knowledge-base/` is human-maintained via Obsidian.

---

## How the Context System Works

1. Notes are written by hand in Obsidian (in `domains/`, `research/`).
2. Files use standard markdown with YAML frontmatter.
3. `context/active-context.md` — current focus, recent insights, open questions, active theses. **Claude updates this.**
4. `context/domain-summaries/*.md` — synthesised summaries of each domain's knowledge. **Claude updates these.**
5. Before doing deep research on any topic, read the relevant `domains/` files AND the `context/domain-summaries/` file for that domain.

---

## Self-Improvement Protocol

When new knowledge is gained during a session (a correction, a domain insight, a new pattern):

1. Update `context/active-context.md` — add to Recent Insights, update Current Focus.
2. Update `context/domain-summaries/<domain>.md` if domain-specific.
3. Add corrections to `meta/lessons-learned.md` (format: `YYYY-MM-DD — [Topic] — Wrong → Correct`).
4. Add new terminology to `meta/glossary.md`.

Trigger: via `/learn` command or when the user says "update context" / "remember this".

---

## My Preferences

Full details in `knowledge-base/meta/preferences.md`. Key points:

- Data-driven. Numbers first, narratives second.
- Skeptical. Identify the source and its incentives.
- Quantify confidence (high / medium / low or %).
- Primary sources preferred (SEC filings, on-chain data, central bank statements).
- Challenge anchoring — if I seem stuck on a prior view, push back.
- Communication: concise, no padding, bullet facts, prose reasoning.

---

## Working With Notes

- **Do NOT modify** files in `domains/`, `research/`, or `meta/` unless explicitly asked.
- **Freely update** `context/` files — that is your layer to maintain.
- Notes are informal and may be incomplete — work with what's there.
- When the user writes new notes, offer to extract structured insights into `context/`.
- Cross-reference related notes using [[wikilinks]] style when writing to `context/`.

---

## Key Commands

| Command | Purpose |
|---------|---------|
| `/learn` | Extract insights from the session and persist to context layer |
| `/research <topic>` | Structured research session with journal entry output |
| `/thesis <asset> <direction> <conviction>` | Create a new investment thesis file |
| `/status` | Overview of knowledge base state (staleness, active theses, open questions) |
| `/context-update [domain]` | Re-synthesise context layer from latest notes |

---

## Current Focus

Phase 1 setup — establishing the knowledge base and context system. Research focus: to be defined.
