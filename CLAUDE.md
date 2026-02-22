# CLAUDE.md

This file provides guidance to Claude Code and other AI assistants when working in this repository.

## Repository Overview

**Repository:** achu037/AC-WorkStation
**Status:** Workspace initialized — no project files committed yet.
**Primary Branch:** `main` (or as established when the project is set up)
**Development Branches:** Follow the pattern `claude/<description>-<session-id>` for AI-assisted sessions.

This is a blank workspace ready for project initialization. Update this file when a project is added.

---

## Git Workflow

### Branch Naming

| Branch type | Pattern | Example |
|---|---|---|
| AI session branches | `claude/<slug>-<session-id>` | `claude/add-auth-r3YTo` |
| Feature branches | `feat/<short-description>` | `feat/user-dashboard` |
| Bug fix branches | `fix/<short-description>` | `fix/login-redirect` |
| Chore/maintenance | `chore/<short-description>` | `chore/update-deps` |

### Commit Messages

Follow the [Conventional Commits](https://www.conventionalcommits.org/) standard:

```
<type>(<scope>): <short summary>

[optional body]

[optional footer]
```

**Types:** `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`, `ci`

**Examples:**
```
feat(auth): add JWT token refresh logic
fix(api): handle null response from user endpoint
docs: update README with setup instructions
chore: bump dependencies to latest patch versions
```

- Keep the subject line under 72 characters.
- Use the imperative mood ("add", not "added" or "adds").
- Reference issue numbers in the footer: `Closes #42`.

### Push Protocol

Always push to the designated branch for the current session:

```bash
git push -u origin <branch-name>
```

- Branch names for AI sessions must start with `claude/`.
- Retry on network failure with exponential backoff: 2 s, 4 s, 8 s, 16 s.
- Never force-push to `main` or shared branches without explicit user approval.

---

## Development Conventions

These conventions apply once a project stack is chosen. Update each section when the project is initialized.

### Code Style

- Follow the style guide appropriate for the chosen language/framework.
- Lint and format before committing.
- Do not commit auto-generated files (build artifacts, `node_modules`, `.env`, etc.).

### Testing

- Write tests alongside implementation; do not defer tests to a later PR.
- All tests must pass before merging to `main`.
- Aim for meaningful coverage, not 100% coverage for its own sake.

### Environment Variables

- Never commit secrets, API keys, or credentials.
- Use `.env` for local overrides and `.env.example` (committed) to document required variables.
- Document every environment variable in `.env.example` with a description and safe default.

### Dependency Management

- Pin exact versions in lock files (`package-lock.json`, `poetry.lock`, etc.).
- Review changelogs before upgrading major versions.
- Remove unused dependencies immediately.

---

## AI Assistant Guidelines

### Before Making Changes

1. Read the files you plan to modify — never propose edits to unread code.
2. Understand the existing patterns; match them rather than introducing new ones.
3. Use `TodoWrite` to plan multi-step tasks before starting.

### Code Changes

- Make only the changes requested or clearly necessary.
- Do not refactor, add comments, or improve unrelated code while fixing a bug.
- Prefer editing existing files over creating new ones.
- Remove unused code completely; do not leave dead code with comments like `// removed`.

### Security

- Do not introduce SQL injection, XSS, command injection, or other OWASP Top 10 vulnerabilities.
- Validate all external input at system boundaries.
- Do not add unnecessary permissions or capabilities.

### Commit & Push Behavior

- Commit only when explicitly asked by the user.
- Stage specific files by name rather than using `git add -A` to avoid accidental inclusion of secrets.
- Create new commits rather than amending unless the user explicitly requests an amend.
- Never skip pre-commit hooks (`--no-verify`).

---

## Project Setup (To Be Completed)

Once a project stack is chosen, document the following here:

### Tech Stack

```
Language:   <e.g., TypeScript, Python, Go>
Framework:  <e.g., Next.js, FastAPI, Gin>
Database:   <e.g., PostgreSQL, SQLite, MongoDB>
Runtime:    <e.g., Node.js 20, Python 3.12>
Package manager: <e.g., npm, pnpm, uv, cargo>
```

### Getting Started

```bash
# Clone and install
git clone <repo-url>
cd AC-WorkStation

# Install dependencies
<install command>

# Copy environment variables
cp .env.example .env
# Edit .env with your local values

# Run development server
<dev command>
```

### Common Commands

| Command | Description |
|---|---|
| `<dev command>` | Start development server |
| `<test command>` | Run test suite |
| `<lint command>` | Run linter |
| `<format command>` | Auto-format code |
| `<build command>` | Build for production |

### Project Structure

```
AC-WorkStation/
├── CLAUDE.md          # This file
├── README.md          # Human-facing documentation
├── .env.example       # Environment variable template
└── <project dirs>     # To be documented after project init
```

---

## Updating This File

Keep CLAUDE.md current as the project evolves:

- Add the tech stack, commands, and directory structure when the project is initialized.
- Update conventions when the team adopts new tools or standards.
- Remove placeholder sections once they are filled in with real content.
