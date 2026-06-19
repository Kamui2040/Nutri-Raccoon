# Nutri Raccoon Public Repository Instructions

This repository is the public canonical source for all Nutri Raccoon application code, public documentation, licensed assets, translations, tests, CI, and release metadata.

Use **Nutri** in normal app headers and **Nutri Raccoon** for repositories, documentation, licences, About, releases, and metadata.

## Read order

1. Global Codex `AGENTS.md`
2. This file
3. `PROJECT_CONTEXT.md`
4. Task-relevant documents referenced by `PROJECT_CONTEXT.md`

Read current `main` before making assumptions. Use `PROJECT_CONTEXT.md` for current project state and specialist documents for detail.

## Repository workflow

- Keep `main` stable.
- Use focused branches and pull requests.
- Do not commit directly to `main` unless explicitly requested.
- Keep all application code in this public repository; never maintain a private code fork.
- Keep private research, raw QA, sensitive operations, and unpublished interoperability plans out of this repository.
- Update only the authoritative documents affected by a change.
- Do not duplicate specialist specifications across instruction or overview files.

## Non-negotiable constraints

- Keep the app local-first, private, offline-capable, fully FLOSS, and F-Droid-compatible.
- Do not require Google Play Services, Firebase, proprietary SDKs, analytics, tracking, ads, accounts, subscriptions, paid unlocks, or mandatory network services.
- Keep barcode scanning, OCR, nutrition tracking, product storage, and the local database FLOSS-compatible.
- Make online and AI features explicit opt-in, replaceable, and non-essential.
- Keep personal diary data separate from shareable product data.
- Any future public product exchange must be opt-in, product-only, sanitised, and contain no contributor or device identity.
- Never commit secrets, signing material, credentials, private configuration, local paths, personal data, real nutrition records, private images, image metadata, or sensitive logs.
- The app remains free; Ko-fi is an optional external donation link only.
- Licensing status is defined by repository licence files. Do not change it without explicit review.

## Build and release safety

- Configure signing and reproducible builds from the Android scaffold.
- Contributors and F-Droid must be able to build without the production key.
- Read signing values only from environment variables or ignored local configuration.
- Select a stable application ID before public distribution.
- Never publish or commit private signing material.

## Gemini in Android Studio

- The project is currently in research and planning. Gemini MUST NOT create the Android scaffold, application code, build files, scripts, or implementation changes unless implementation has been explicitly approved.
- Gemini in Android Studio MAY be used for supervised, read-only Android and F-Droid research, compatibility analysis after relevant files exist, Android API or accessibility explanations, and low-risk test or acceptance-criteria suggestions.
- After an approved scaffold exists, Gemini MAY also assist with supervised build, manifest, resource, and Logcat diagnostics.
- Gemini MUST NOT implicitly resolve the unresolved foundation decisions listed in `PROJECT_CONTEXT.md`.
- Gemini recommendations MUST preserve the existing local-first, FLOSS, privacy, and F-Droid constraints.
- Gemini MUST NOT access ignored files, sensitive files, signing material, or files outside the repository.
- Web search and URL access SHOULD remain disabled unless the current task explicitly requires and approves them.
- Commands, writes, renames, deletions, MCP access, and connected-device actions MUST require explicit approval.
- Gemini MUST NOT commit, push, create or merge pull requests, mark pull requests ready, delete branches, or perform releases.
- Before any Gemini-assisted file change, create a focused feature branch and verify a clean working tree.
- After each Gemini session, inspect the exact changed-file set and run the required deterministic validation.
- Gemini output is advisory; repository files, reviewed project decisions, and deterministic tools remain authoritative.

## Validation

- Run the checks documented for the affected area.
- Distinguish local/emulator validation from physical-device validation.
- Do not claim camera, barcode, OCR, database migration, notification, accessibility, or release behavior without evidence.
- Run `git diff --check`.
- Review the final diff for secrets, personal data, generated binaries, local paths, non-free dependencies, and unintended documentation duplication.
