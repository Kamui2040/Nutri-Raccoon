# Nutri Raccoon Project Context

## Current state

- Status: research and planning.
- Public canonical repository: `Kamui2040/Nutri-Raccoon`
- Private planning/operations repository: `Kamui2040/Nutri-Raccoon-Internal`
- Active phase: Phase 0 - Foundation.
- Android application code and scaffold: not yet created.
- `main`: stable public baseline.
- Normal app header name: **Nutri**
- Formal project name: **Nutri Raccoon**

## Current product truth

- Local-first, private, offline-capable, FLOSS, and F-Droid-compatible.
- Core use must not require proprietary services, accounts, ads, subscriptions, paid unlocks, or mandatory networking.
- Primary workflow: local product lookup, optional barcode lookup, local saving, then OCR or optional AI-assisted fallback.
- Personal diary data is private and separate from potentially shareable product data.
- Future community product exchange is opt-in, product-only, sanitised, and identity-free.
- The app remains free; Ko-fi support is external and optional.
- Licensing status is defined by `LICENSE` and `LICENSES/README.md`.

## Current UI and architecture direction

- Android UI architecture: Kotlin with Jetpack Compose.
- Use a state-driven, feature-oriented structure with reusable design tokens and Compose components from the initial scaffold.
- A single activity may host Compose navigation; ViewModels, domain rules, data access, and platform integrations remain separated by responsibility.
- Whole-screen custom Canvas rendering is not the baseline; use contained custom drawing only where it is materially useful.
- Top bar: mascot/app symbol left, **Nutri** centred, Settings right.
- Main meals: Breakfast, Lunch, Dinner, Snacks, plus future custom sections.
- Bottom navigation: Home, History, central Camera, Products.
- Camera actions: barcode/product scan and meal-photo recognition.
- Label OCR is a fallback inside the product workflow.
- Themes: System, Standard Light, Standard Dark, Cozy Pastel Light, Cozy Pastel Dark.
- Language defaults to the system language with manual overrides.
- About uses the established K2040 Android dialog pattern and opens Ko-fi externally.
- Reusable meal templates support one-tap logging and optional weekday schedules.

## Selected Android baseline

- Application ID and namespace: `io.github.kamui2040.nutriraccoon`
- Minimum SDK: API 26 (Android 8.0)
- Compile SDK: API 37
- Target SDK: API 37
- JDK and JVM target: 17
- Android Gradle Plugin: 9.2.1
- Gradle wrapper: 9.4.1
- Kotlin: AGP built-in Kotlin, backed by Kotlin Gradle Plugin 2.3.10
- Compose compiler Gradle plugin: 2.3.10
- Stable Compose BOM: `2026.06.00`
- Build scripts: Kotlin DSL with a Gradle version catalog
- Initial Gradle structure: one `app` module; no premature multi-module split
- Recommended development IDE: Android Studio Quail 1 | 2026.1.1 Patch 2
- Authoritative detail: `docs/ANDROID_BASELINE.md`

## Unresolved foundation decisions

- FLOSS barcode-scanning and OCR dependencies.
- Initial product-data provider integration and cache policy.
- Initial database and migration baseline.
- Reproducible release-build procedure and signing variable names.
- Explicit approval to create the first Android scaffold.

Do not resolve these implicitly. Record reviewed decisions in the appropriate authoritative document.

## Document map

- Public summary: `README.md`
- Repository rules: `AGENTS.md`
- Android application baseline: `docs/ANDROID_BASELINE.md`
- UI and themes: `docs/DESIGN_NOTES.md`
- Architecture: `docs/ARCHITECTURE.md`
- Data and schemas: `docs/DATA_MODEL.md`
- Privacy: `docs/PRIVACY_MODEL.md`
- Product exchange: `docs/COMMUNITY_CATALOGUE.md`
- Signing: `docs/RELEASE_SIGNING.md`
- Builds and contributions: `docs/BUILD_WORKFLOW.md`
- Scope and phases: `docs/ROADMAP.md`
- Contribution policy: `CONTRIBUTING.md`
- Security reporting: `SECURITY.md`
- Licence mapping: `LICENSES/README.md`

## Next safe work

1. Keep public documentation compact and non-duplicative.
2. Obtain explicit approval before creating the first Android scaffold.
3. Create only the scaffold scope defined in `docs/ANDROID_BASELINE.md`.
4. Configure deterministic builds, signing hooks, licence checks, and CI with the scaffold.
5. Select and document FLOSS barcode/OCR, product-provider, and database baselines before implementing the related features.
6. Establish reusable Compose theme tokens and components before implementing many screens.
7. Begin Phase 1 only after the remaining foundation decisions are recorded.

## Private-only material

Keep raw research, internal QA, release operations, infrastructure details, private assets, and unpublished cross-app interoperability plans in `Kamui2040/Nutri-Raccoon-Internal`. Promote only reviewed and sanitised information.
