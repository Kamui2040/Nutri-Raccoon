# Nutri Raccoon Public Repository Instructions

This repository is the **public canonical source of truth for all Nutri Raccoon application code**. It must remain complete, buildable, privacy-respecting, and suitable for public contribution and F-Droid distribution.

The formal project and application name is **Nutri Raccoon**. Normal in-app page headers may use the shorter title **Nutri**.

## Repository role and workflow

- Treat `main` as the stable baseline.
- Use focused feature branches and pull requests for implementation, documentation, assets, translations, tests, build configuration, and release metadata.
- Do not commit directly to `main` unless explicitly requested.
- Keep application code only in this public repository. Do not maintain a duplicate private code fork in the internal repository.
- Inspect `README.md`, this file, and any later `PROJECT_CONTEXT.md` or relevant documentation before making assumptions.
- Update public documentation whenever behavior, architecture, privacy, compatibility, build instructions, release requirements, known issues, or durable project decisions change.
- Keep private research, raw QA notes, sensitive operational details, and internal publication checklists in `Kamui2040/Nutri-Raccoon-Internal`.

## FLOSS and F-Droid baseline

- Keep the complete core application fully FLOSS and buildable without proprietary services.
- Design for F-Droid compatibility from the beginning.
- Do not add Google Play Services, Firebase, Crashlytics, proprietary analytics, advertising SDKs, tracking SDKs, or other non-free runtime dependencies.
- Barcode lookup, OCR, nutrition tracking, the local database, and normal offline use must remain functional without proprietary services.
- Optional online or AI-assisted features must be explicit opt-in enhancements and must not be required for core functionality.
- Prefer dependencies available from reproducible, redistribution-friendly sources.
- Document every third-party dependency and its licence.
- Planned licensing direction:
  - application code: `GPL-3.0-or-later`;
  - original project artwork and assets: `CC BY-SA 4.0`;
  - third-party components retain their compatible licences.
- Public contributions are licensed inbound under the repository's applicable project licence. Do not introduce a CLA or DCO requirement unless the contribution model is deliberately changed later.

## Privacy and data protection

- Keep the app local-first.
- Do not add ads, mandatory accounts, subscriptions, telemetry, behavioural analytics, automatic crash reporting, or background tracking.
- Do not commit real nutrition histories, body data, meal records, personal notes, account identifiers, device identifiers, or other personal user data.
- Do not commit screenshots, logs, test fixtures, or metadata containing personal names, email addresses, local machine paths, device identifiers, or private content.
- Strip image metadata from any public example images.
- Use synthetic or deliberately anonymised test data.
- A future community product catalogue may contain only sanitised non-personal product information.
- Public product records must not contain usernames, account IDs, contributor IDs, device IDs, or any stable identifier that can link a contribution to a person.

## Signing and release safety

- Configure release signing through environment variables or ignored local configuration only.
- Never commit keystores, signing keys, passwords, API keys, service credentials, tokens, certificates containing private material, or machine-specific secret files.
- Keep unsigned or reproducible release builds possible for contributors and F-Droid.
- Use a stable application ID before the first public release.
- Aim for reproducible builds so F-Droid can verify developer-signed releases without signature conflicts.
- Publish only the production signing certificate fingerprint, never the private key.
- Releases must remain free of charge with no paid unlocks, mandatory purchases, subscriptions, or ads.
- The Ko-fi link is an optional external donation link only and must never unlock or alter app functionality.

## Product architecture

- Preserve the established top app bar: mascot or app symbol on the left, `Nutri` centred, and Settings on the right.
- Keep Settings out of bottom navigation.
- Keep the core nutrition database and meal history local.
- Barcode lookup should be attempted before label scanning or AI-assisted extraction.
- Save retrieved or confirmed products locally with clear source and verification information.
- Theme and language selections must persist locally and default to the system setting.
- Standard theme choices are System, Standard Light, Standard Dark, Cozy Pastel Light, and Cozy Pastel Dark.
- Language selection defaults to the system language with explicit manual choices available.
- The About dialog should include the established external Ko-fi button without feature gating.

## Validation

- Run the repository's documented Gradle build, lint, unit tests, formatting, and relevant Android checks before reporting implementation complete.
- Distinguish emulator/local validation from physical-device testing.
- Do not claim barcode, OCR, camera, database migration, notification, or accessibility behavior works without appropriate evidence.
- Review the final diff for secrets, private data, generated binaries, machine-specific paths, and non-free dependencies.
- Keep APKs, AABs, signing output, local databases, captured labels, user photos, and generated build directories out of Git unless a documented release process explicitly publishes an allowed artifact.

When a compact public `PROJECT_CONTEXT.md` is added later, use it for current architecture, active implementation stage, stable paths, build baseline, and public project constraints. Keep detailed private planning and raw operational history out of this repository.

## Project Workflow Rules

For all projects under `D:\Projects`, the following hard rules apply:
- **Default Environment**: Windows + PowerShell 7.
- **Default Project Path**: `D:\Projects\<Platform>\<Project>\repo\<Repo>`.
- **Single-Step Instructions**: Commands are provided one at a time with explicit `Set-Location` if needed.
- **Automation Preferred**: Scripts are provided over manual steps.
- **Default Download Folder**: `C:\Users\kamui\Downloads` is the starting point for files.
- **Confirmation Required**: Wait for explicit "OK" before proceeding to the next step.
