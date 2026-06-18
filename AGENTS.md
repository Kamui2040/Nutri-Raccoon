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

## Validation

- Run the checks documented for the affected area.
- Distinguish local/emulator validation from physical-device validation.
- Do not claim camera, barcode, OCR, database migration, notification, accessibility, or release behavior without evidence.
- Run `git diff --check`.
- Review the final diff for secrets, personal data, generated binaries, local paths, non-free dependencies, and unintended documentation duplication.
