# CLAUDE.md — AI Assistant Guide for eudaimons

## Repository Overview

**Repository:** m0camb0/eudaimons
**Current state:** Early-stage / bootstrapping. As of February 2026 the repository contains only a `README.md` with the project title. No source code, build system, or configuration files exist yet.

The name *eudaimons* derives from the Greek *eudaimonia* (flourishing, well-being). The project direction beyond the name is not yet declared in the codebase.

---

## Working in This Repository

Because the codebase is currently empty, the guidance below covers **what to do as the project grows** as well as **immediate conventions** that should be followed from the first commit.

### Git Workflow

- The default long-lived branch is **`master`**.
- Feature/fix branches should be created from `master` and named descriptively:
  - `feature/<short-description>` for new work
  - `fix/<short-description>` for bug fixes
  - `chore/<short-description>` for maintenance/tooling
- Claude Code branches follow the pattern `claude/<task-slug>-<session-id>`.
- Commit messages should be written in the **imperative mood** (e.g., "Add user model", not "Added user model").
- Never push directly to `master` without a review step once collaborators are added.

### Branching Conventions (Claude Code)

When operating as Claude Code, always:

1. Develop on the designated `claude/…` branch for the session.
2. Commit with descriptive messages that explain *why*, not just *what*.
3. Push with `git push -u origin <branch-name>`.
4. Never force-push to `master` or any shared branch.

---

## Repository Structure (Anticipated)

As the project grows, the following layout is recommended (update this section as directories are added):

```
eudaimons/
├── CLAUDE.md          # This file — AI assistant guide
├── README.md          # Human-facing project overview
├── src/               # Application source code (add when created)
├── tests/             # Test suite (add when created)
├── docs/              # Additional documentation (add when created)
└── ...
```

Update this section whenever significant new top-level directories or config files are introduced.

---

## Development Commands

> These commands do not yet exist. Populate this section once a build system / package manager is chosen.

| Purpose | Command |
|---------|---------|
| Install dependencies | *(TBD)* |
| Run tests | *(TBD)* |
| Lint / format | *(TBD)* |
| Build | *(TBD)* |
| Start dev server | *(TBD)* |

**When commands are established**, always run the test suite and linter before committing.

---

## Code Style & Conventions

Until a linter / formatter config is committed, follow these defaults:

- **Indentation:** 2 spaces (adjust to match whatever config is added).
- **Line length:** ≤ 100 characters.
- **Quotes:** Prefer double quotes for strings unless the language convention differs (e.g., single quotes in Python is fine).
- **Naming:** `camelCase` for JS/TS identifiers, `snake_case` for Python, `PascalCase` for types/classes in any language.
- **File names:** `kebab-case` for web assets and config files; follow language ecosystem norms for source files.
- **No commented-out dead code** — remove it or use a TODO comment explaining why it is kept.
- **TODOs** should include a brief explanation: `// TODO: replace with API call once endpoint is ready`.

---

## Testing Expectations

- All non-trivial logic should have accompanying tests.
- Tests live alongside or near the code they exercise (e.g., `src/foo.test.ts` or `tests/test_foo.py`).
- Tests must pass before merging.
- Do not delete or skip tests to make a build pass; fix the underlying issue instead.

---

## Documentation

- Keep `README.md` up to date with setup instructions, project purpose, and usage examples.
- Update **this file** (`CLAUDE.md`) whenever the project structure, build commands, or key conventions change.
- Inline comments should explain *why* something is done, not restate *what* the code does.

---

## Security

- Never commit secrets, credentials, API keys, or tokens — use environment variables or a secrets manager.
- Add a `.gitignore` before committing any generated files, build artifacts, or dependency directories.
- Validate all external input at system boundaries.

---

## Key Facts for AI Assistants

- **Read files before modifying them.** Never guess at existing code.
- **Minimal changes.** Only make changes that are directly requested or clearly necessary.
- **No unrequested refactors.** A bug fix does not need surrounding cleanup.
- **No new files without cause.** Prefer editing existing files; only create new files when genuinely required.
- **No emojis** in source files or commit messages unless explicitly requested.
- **Verify before assuming.** If the codebase structure is unclear, explore first.

---

*Last updated: 2026-02-19 by Claude Code (session claude-md-mlspcc0i0khr7eq2-wo1Mg)*
