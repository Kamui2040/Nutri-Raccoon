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

## Current UI direction

- Top bar: mascot/app symbol left, **Nutri** centred, Settings right.
- Main meals: Breakfast, Lunch, Dinner, Snacks, plus future custom sections.
- Bottom navigation: Home, History, central Camera, Products.
- Camera actions: barcode/product scan and meal-photo recognition.
- Label OCR is a fallback inside the product workflow.
- Themes: System, Standard Light, Standard Dark, Cozy Pastel Light, Cozy Pastel Dark.
- Language defaults to the system language with manual overrides.
- About uses the established K2040 Android dialog pattern and opens Ko-fi externally.
- Reusable meal templates support one-tap logging and optional weekday schedules.

## Unresolved foundation decisions

- Stable Android application ID.
- Minimum and target Android SDK levels.
- JDK, Gradle, Android Gradle Plugin, Kotlin, and Compose baselines.
- FLOSS barcode-scanning and OCR dependencies.
- Initial product-data provider integration and cache policy.
- Initial database and migration baseline.
- Reproducible release-build procedure and signing variable names.
- Final scope of the first Android scaffold.

Do not resolve these implicitly. Record reviewed decisions in the appropriate authoritative document.

## Document map

- Public summary: `README.md`
- Repository rules: `AGENTS.md`
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
2. Select and document the Android/application baseline.
3. Create the Android scaffold only after explicit approval.
4. Configure deterministic builds, signing hooks, licence checks, and CI with the scaffold.
5. Begin Phase 1 only after the foundation decisions are recorded.

## Private-only material

Keep raw research, internal QA, release operations, infrastructure details, private assets, and unpublished cross-app interoperability plans in `Kamui2040/Nutri-Raccoon-Internal`. Promote only reviewed and sanitised information.
