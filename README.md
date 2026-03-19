<div align="center">
  <h1>CODEX_GodMode_ON</h1>
  <p><strong>Install once globally. Then start any Codex session with the prompts below.</strong></p>
  <p>This repository packages a globally installable Codex workflow inspired by <a href="https://github.com/cubetribe/ClaudeCode_GodMode-On">ClaudeCode_GodMode-On</a>.</p>
  <p>
    <a href="./docs/blueprint.md">Blueprint</a>
    &middot;
    <a href="./docs/roadmap.md">Roadmap</a>
    &middot;
    <a href="./docs/local-development.md">Local Dev</a>
    &middot;
    <a href="./docs/global-codex-setup.md">Global Setup</a>
  </p>
</div>

## Start Here

Users should not need to pull this repository into every new session.

Install the workflow once:

```bash
./scripts/apply-global-codex-setup.sh
```

After that, start Codex in any workspace and copy one of these prompts exactly as-is.

These prompts intentionally use skill mentions such as `$godmode-workflow`, `$web-platforms`, `$apple-platforms`, and `$flutter-dart`. That is the documented Codex skill invocation path.

This repository is the installer, reference implementation, and contribution surface for the global setup.

Files:

- [docs/prompts/dev-start-prompt.md](./docs/prompts/dev-start-prompt.md)
- [docs/prompts/debug-start-prompt.md](./docs/prompts/debug-start-prompt.md)
- [docs/prompts/review-start-prompt.md](./docs/prompts/review-start-prompt.md)
- [docs/prompts/web-start-prompt.md](./docs/prompts/web-start-prompt.md)
- [docs/prompts/apple-start-prompt.md](./docs/prompts/apple-start-prompt.md)
- [docs/prompts/flutter-start-prompt.md](./docs/prompts/flutter-start-prompt.md)

Dev:

```text
$godmode-workflow

GODMODE DEV

Goal: <goal>

Inspect the current workspace first.
Loop: research -> plan -> build -> validate.
```

Debug:

```text
$godmode-workflow

GODMODE DEBUG

Goal: <bug / symptom / expected result>

Inspect the current workspace first.
Loop: reproduce -> isolate -> fix -> re-test.
```

Review:

```text
$godmode-workflow

GODMODE REVIEW

Goal: <system / change / problem to assess>

Inspect the current workspace first.
Loop: inspect -> analyze -> verify -> report.
Findings first. No code changes unless asked.
```

Stack-specific dev starters:

Web:

```text
$godmode-workflow
$web-platforms

GODMODE WEB

Goal: <goal>

Inspect the current workspace first.
Loop: research -> plan -> build -> validate.
```

Apple:

```text
$godmode-workflow
$apple-platforms

GODMODE APPLE

Goal: <goal>

Inspect the current workspace first.
Loop: research -> plan -> build -> validate.
```

Flutter:

```text
$godmode-workflow
$flutter-dart

GODMODE FLUTTER

Goal: <goal>

Inspect the current workspace first.
Loop: research -> plan -> build -> validate.
```

## How To Use It

1. Install the global runtime once with `./scripts/apply-global-codex-setup.sh`.
2. Open any workspace in the Codex app or CLI.
3. Paste one of the prompts from this README into a new thread.
4. Replace `Goal` with the real task.
5. Let Codex inspect the workspace first, then follow the requested loop.

## Skills, Slash Commands, and Agents

### Skills

- Skills are invoked with `$`, not with `@`.
- Example: `$godmode-workflow`, `$web-platforms`, `$apple-platforms`, `$flutter-dart`
- In Codex, you can type `$` in the composer to mention a skill directly.
- In the Codex app, enabled skills can also appear in the slash-command list.

### Slash commands

- In the Codex app, type `/` in the composer to open the slash-command list.
- Useful built-in commands include `/status`, `/review`, and `/plan-mode`.
- In interactive Codex sessions, slash commands are for session control; the workflow prompts in this repo are for task startup.

### Agents and subagents

- The GodMode runtime installs custom agents such as `researcher`, `architect`, `builder`, `validator`, `tester`, `scribe`, and `api_guardian`.
- The documented prompt surface in this repo uses skills to start the workflow, not `@agent` mentions.
- To use the installed agents, ask Codex directly to use or split work across those roles.
- In the CLI, `/agent` lets you switch between active agent threads after subagents have been spawned.

## Which Prompt To Use

- Use `GODMODE DEV` for general implementation.
- Use `GODMODE DEBUG` for reproduce -> isolate -> fix work.
- Use `GODMODE REVIEW` for analysis-only or findings-first review.
- Use `GODMODE WEB` for React, Next.js, and Node.js work.
- Use `GODMODE APPLE` for SwiftUI, macOS, and iOS work.
- Use `GODMODE FLUTTER` for Flutter and Dart work.

## What This Repo Is

This repository is the documented reference and installer source for a Codex-native version of the GodMode workflow:

- explicit orchestration instead of hidden automation
- a clear main thread acting as orchestrator
- focused specialist agents
- persistent reports and state artifacts
- hard quality gates before completion

It is not just a prompt pack. It is the bootstrap repo for the globally installed system.

## What You Get

| Area | Purpose |
| --- | --- |
| `README.md` | the public entry point and copy-paste prompts |
| `docs/blueprint.md` | the architecture and workflow design |
| `docs/roadmap.md` | phased delivery plan |
| `docs/local-development.md` | maintainer operating guide for this repo |
| `docs/global-codex-setup.md` | reproducible install guide for the global runtime |
| `docs/prompts/` | standalone prompt documents |
| `.codex/agents/` | canonical GodMode agent role definitions that the installer publishes to `~/.codex/agents/` |
| `.agents/skills/` | canonical GodMode skills that the installer publishes to `~/.agents/skills/` |
| `templates/global-codex/` | global `AGENTS.md` and `config.toml` templates |
| `scripts/check-local-env.sh` | local repo validation |
| `scripts/apply-global-codex-setup.sh` | install the documented global setup, agents, and skills |
| `reports/` | persistent report conventions |
| `state/` | persistent workflow state conventions |

## Core Decisions

- The main thread stays the orchestrator.
- The normal code writer is `builder`; validation and testing stay read-heavy.
- `validator` and `tester` form a joint quality gate.
- `api_guardian` is mandatory for API, schema, CLI, or config-surface changes.
- Reports and state live in the repo, not only in chat history.
- Push and deploy remain explicit human decisions.
- This repository now operates on `main` by default.
- Daily use should work from any workspace after a one-time global install.

## Read Next

| If you want to... | Start here |
| --- | --- |
| understand the full target architecture | [docs/blueprint.md](./docs/blueprint.md) |
| see what gets delivered in what order | [docs/roadmap.md](./docs/roadmap.md) |
| run and evolve the repo locally | [docs/local-development.md](./docs/local-development.md) |
| install the matching global Codex setup | [docs/global-codex-setup.md](./docs/global-codex-setup.md) |

## Sources

- Source repo: [cubetribe/ClaudeCode_GodMode-On](https://github.com/cubetribe/ClaudeCode_GodMode-On)
- Codex docs: [Subagents](https://developers.openai.com/codex/subagents/)
- Codex docs: [Slash commands in Codex CLI](https://developers.openai.com/codex/cli/slash-commands)
- Codex docs: [Codex app commands](https://developers.openai.com/codex/app/commands)
- Codex docs: [Custom instructions with AGENTS.md](https://developers.openai.com/codex/guides/agents-md/)
- Codex docs: [Configuration reference](https://developers.openai.com/codex/config-reference/)
- Codex docs: [Agent Skills](https://developers.openai.com/codex/skills/)

## Contributing

If you contribute here:

1. Keep the README truthful and immediately usable.
2. Keep prompts copy-paste friendly.
3. Keep architecture docs explicit and auditable.
4. Keep the repository aligned around `main` unless a branch is explicitly requested.
