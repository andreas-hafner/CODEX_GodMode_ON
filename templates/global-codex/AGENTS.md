# ~/.codex/AGENTS.md

## Default working style

- Work only inside the currently opened workspace unless I explicitly ask for a separate clone or worktree.
- Inspect the current workspace first. Do not assume it is a Git repo, app, package, monorepo, or empty folder until verified.
- Keep diffs small, safe, and buildable.
- Do not touch unrelated files.
- Prefer official framework docs when guidance is version-sensitive.
- Record assumptions briefly when repo rules are unclear.

## Execution flow

- For non-trivial work: Research -> Plan -> Build -> Validate -> Release Summary.
- Before editing, report workspace root, current branch if present, touched files, and expected impact when that is not already obvious.
- Run only the checks that match the changed scope.
- Use the installed global workflow, custom agents, and skills by default.
- If the current workspace provides its own `AGENTS.md`, `.codex/agents/`, or `.agents/skills/`, treat them as local overrides and adapt to them instead of ignoring them.

## Global workflow

- Prefer the GodMode loop for non-trivial work.
- Available global agents: `researcher`, `architect`, `api_guardian`, `builder`, `validator`, `tester`, `scribe`, `github_manager`.
- Available global skills: `godmode-workflow`, `apple-platforms`, `web-platforms`, `flutter-dart`, `release-manager`.

## Profile intents

- `swiftui`: prioritize Apple platform guidance, SwiftUI state ownership, and `xcodebuild`-based validation.
- `web`: prioritize React purity, Next.js App Router rules, Node.js contract clarity, and version-sensitive web docs.
- `flutter`: prioritize analyzer cleanliness, repository boundaries, unidirectional data flow, and `flutter test` / `dart analyze`.
- `review`: default to review mode with findings first, severity ordering, and file or line references before summaries.

## Stack defaults

- SwiftUI: keep a single source of truth, use `@State` only for transient UI state, use bindings for child edits, and keep business logic out of views.
- React / Next.js: prefer Server Components by default in App Router projects, keep client boundaries explicit, and avoid using effects for normal derived data flow.
- Node.js: keep public entry points explicit, centralize configuration loading, and avoid hidden side effects during module import.
- Flutter / Dart: keep widgets presentation-focused, keep repositories as the data source of truth, prefer unidirectional data flow, and treat analyzer output as correctness.

## Git safety

- Classify changes as major, minor, patch, or none.
- When a repo uses a manual changelog, update `[Unreleased]` for behavior or setup changes.
- Suggest Conventional Commit style titles when preparing commits.
- Never commit or push without explicit approval.
- Never force-push a shared branch.
- Never rewrite shared history.
