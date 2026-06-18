# Vibe Workflow

Last reviewed: 2026-06-18

Vibe CLI is the default repository-aware assistant for the public Nutri Raccoon application repository. Start it with `vibe` from the repository root after checking `git status` and reading `AGENTS.md`, `README.md`, and task-relevant public documentation.

Use a focused branch and pull request. Prefer Vibe's file tools for repository files. When a Windows shell command requires PowerShell syntax, invoke PowerShell 7 explicitly with `pwsh -NoLogo -NoProfile -NonInteractive -Command "..."`.

## Continue on Vibe Code Web

Run `/teleport` inside an active Vibe CLI session to move the session into a Vibe Code Web sandbox.

Teleport is one-way and currently requires a Git repository, a supported Mistral session and eligible account, a current CLI, and Mistral GitHub App access. Commit and push the branch state the cloud session needs before handoff. Do not assume uncommitted files, local databases, captured labels, photos, signing files, or machine-specific configuration will transfer.

Use the web sandbox for repository-only FLOSS source, public documentation, tests supported by the sandbox, dependency review, and draft pull-request preparation. Keep release signing, private keys, physical-device camera/OCR/barcode testing, local database migration checks, and release verification local.

The public repository must remain complete, buildable, sanitised, F-Droid-compatible, and free of private internal planning. Inspect the final diff, report checks that actually ran, and do not merge without explicit approval.

References:

- [Teleport from CLI to web](https://docs.mistral.ai/vibe/code/cli/teleport-cli-web)
- [CLI commands and shortcuts](https://docs.mistral.ai/vibe/code/cli/commands-shortcuts)
