# Android application baseline

## Status

This document records the reviewed Android application baseline for Nutri Raccoon.

The baseline was selected during Phase 0 on 2026-06-20. It defines the identity, supported Android range, build toolchain, Compose baseline, and permitted scope of the first scaffold. It does not authorise scaffold creation by itself; implementation still requires explicit approval.

## Application identity

- Formal application name: **Nutri Raccoon**
- Normal in-app header name: **Nutri**
- Gradle root project name: `NutriRaccoon`
- Application ID: `io.github.kamui2040.nutriraccoon`
- Android namespace: `io.github.kamui2040.nutriraccoon`

The application ID and namespace start identical. The application ID is treated as permanent once any public APK is distributed. Future source-package refactoring must not silently change the published application ID.

## Android platform baseline

| Setting | Selected value |
| --- | --- |
| Minimum SDK | API 26 — Android 8.0 |
| Compile SDK | API 37 |
| Target SDK | API 37 |
| Expected SDK Build Tools | 36.0.0 |

API 26 is the compatibility floor for the initial release. Raising it later requires a reviewed compatibility decision and clear release notes.

The project compiles and targets the latest stable Android platform selected for this baseline rather than a preview SDK. Preview SDKs must not be introduced into `main` without an explicit reviewed experiment.

## Build toolchain

| Component | Selected value |
| --- | --- |
| JDK | 17 |
| Java source/target compatibility | 17 |
| Kotlin JVM target | 17 |
| Android Gradle Plugin | 9.2.1 |
| Gradle wrapper | 9.4.1 |
| Kotlin support | AGP built-in Kotlin |
| Built-in Kotlin/KGP baseline | 2.3.10 |
| Compose compiler Gradle plugin | 2.3.10 |
| Stable Compose BOM | `2026.06.00` |
| Build-script language | Kotlin DSL |
| Dependency/plugin catalogue | `gradle/libs.versions.toml` |

Use exact versions. Do not use dynamic versions such as `9.2.+`, version ranges, or unreviewed preview releases.

AGP built-in Kotlin remains enabled. Do not apply `org.jetbrains.kotlin.android` or `kotlin-android` to Android modules. The Compose compiler Gradle plugin remains separately declared at the Kotlin-matching version.

Use the Gradle wrapper as the build entry point. The locally installed Gradle version is not authoritative.

## Development environment

The recommended initial IDE is **Android Studio Quail 1 | 2026.1.1 Patch 2** or a later compatible stable patch release.

The IDE is not part of the reproducible-build identity. The Gradle wrapper, AGP version, JDK baseline, SDK packages, and pinned dependencies remain authoritative.

The primary release workflow remains Windows and PowerShell 7. Contributors may use other supported environments when the same wrapper-based validation succeeds.

## Gradle structure

Start with one Android application module:

```text
NutriRaccoon/
  app/
  gradle/
    libs.versions.toml
    wrapper/
  build.gradle.kts
  settings.gradle.kts
  gradle.properties
```

Do not create feature or library modules during the first scaffold. Introduce additional modules only when isolation, testability, ownership, or build-performance benefits clearly exceed their maintenance cost.

The app module uses the selected feature-oriented package structure documented in `docs/ARCHITECTURE.md`.

## First scaffold scope

After explicit approval, the first scaffold may add only:

- Gradle wrapper and root Gradle configuration;
- Kotlin DSL build files and version catalogue;
- one `app` module using the selected identity and SDK levels;
- an application manifest with the minimal required declarations;
- a minimal single-activity Compose entry point;
- baseline Material 3 and Compose dependencies through the stable BOM;
- placeholder theme tokens for Standard Light, Standard Dark, Cozy Pastel Light, and Cozy Pastel Dark;
- minimal app strings and launcher-resource placeholders that are safe to publish;
- baseline unit and instrumentation test directories;
- deterministic debug and unsigned-release build tasks;
- CI for wrapper validation, build, tests, lint, and licence checks where the scaffold supports them;
- signing hooks that read only environment variables or ignored local configuration.

The scaffold must not include production features merely to demonstrate architecture.

## Explicitly excluded from the first scaffold

Do not add any of the following until their own decisions and implementation tasks are approved:

- barcode-scanning libraries or camera flows;
- OCR libraries or label-recognition flows;
- product lookup providers or networking clients;
- AI integrations;
- Room or another production database;
- meal-photo recognition;
- accounts, analytics, telemetry, ads, subscriptions, or proprietary services;
- production signing keys, passwords, aliases, tokens, or local machine paths;
- private assets, private test data, or real nutrition records;
- unnecessary dependency-injection, navigation, persistence, or modularisation frameworks.

A minimal Compose navigation dependency may be added only when the first app-shell destinations are implemented, not merely for an empty scaffold.

## Dependency rules

- Prefer stable FLOSS dependencies with active maintenance and clear licences.
- Keep core offline use independent of proprietary or mandatory network services.
- Record every direct dependency and plugin in the version catalogue where supported.
- Do not add dependencies speculatively.
- Review transitive licences before merging.
- Keep online providers, camera, OCR, and optional AI behind replaceable interfaces when implemented.
- Prefer KSP over kapt where code generation is later required.
- Do not add `com.android.legacy-kapt` unless a reviewed dependency makes it temporarily unavoidable.

## Build and signing rules

- Debug and unsigned release builds must work without production signing secrets.
- Signed release builds may activate only when the documented environment variables or ignored local configuration are present.
- Never commit a keystore or signing secret.
- Contributors and F-Droid must be able to reproduce the unsigned release build from the public repository.
- Pin wrapper and plugin versions and review dependency upgrades through pull requests.
- Record the final signing variable names and reproducible release procedure before the first public APK.

## Validation for the scaffold PR

The initial scaffold pull request must, at minimum:

1. verify the exact application ID, namespace, SDK levels, and toolchain versions;
2. run the Gradle wrapper validation;
3. run the debug build;
4. run the unsigned release build;
5. run unit tests;
6. run lint;
7. run `git diff --check`;
8. inspect the complete changed-file set;
9. verify that no secret, signing material, personal data, private path, generated APK, or restricted asset is committed;
10. distinguish emulator validation from physical-device validation;
11. document any validation that cannot yet run and why.

No camera, barcode, OCR, database migration, notification, accessibility, reproducibility, or release-signing claim may be made without direct evidence.

## Upgrade policy

This baseline is deliberately pinned for the first scaffold. A newer stable version does not update the project automatically.

Toolchain, SDK, Kotlin, Compose, or minimum-SDK changes require:

- a focused branch and pull request;
- official compatibility verification;
- exact version updates in the authoritative files;
- successful deterministic validation;
- review of F-Droid and reproducible-build implications;
- documentation of any user compatibility impact.

## Official reference points

- Android Gradle Plugin release notes: <https://developer.android.com/build/releases/gradle-plugin>
- AGP 9.2 release notes: <https://developer.android.com/build/releases/agp-9-2-0-release-notes>
- Built-in Kotlin migration: <https://developer.android.com/build/migrate-to-built-in-kotlin>
- Compose dependency setup: <https://developer.android.com/develop/ui/compose/setup-compose-dependencies-and-compiler>
- Compose BOM guidance: <https://developer.android.com/develop/ui/compose/bom>
- Android Studio stable releases: <https://developer.android.com/studio/releases>
