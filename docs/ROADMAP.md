# Public roadmap

## Phase 0 — Foundation

### Completed decisions and policies

- Public/private repository structure established.
- Public canonical source and branch/pull-request workflow established.
- Kotlin with Jetpack Compose selected as the Android UI architecture.
- Stable application ID and Android platform/toolchain baseline selected.
- Licences, contribution rules, privacy model, and signing policy established.

### Remaining work

- Approve and create the initial Android project scaffold within the documented scope.
- Add deterministic local and CI build validation.
- Configure signing hooks without committing production secrets.
- Add licence and attribution validation.
- Select FLOSS barcode-scanning and OCR dependencies.
- Select the initial product-data provider and cache policy.
- Select the initial local database and migration baseline.
- Verify the first unsigned release build and document the reproducible-build procedure.

## Phase 1 — Manual local diary

- Cozy theme system and app shell.
- Home, History, Products, Settings, and About interfaces.
- Meal sections and manual product/portion entry.
- Reusable meal templates, one-tap logging, and optional weekday scheduling.
- Local database and import/export foundations.

## Phase 2 — Barcode-first products

- FLOSS barcode scanning.
- Open product lookup integration.
- Product review, correction, caching, and provenance.
- Practical slice, piece, serving, and package portions.

## Phase 3 — Label assistance

- Nutrition-table and ingredient OCR fallback.
- Structured confirmation workflow.
- Allergen and additive display with clear source information.

## Phase 4 — Optional assistance

- Meal-photo recognition experiments.
- Matching recognised foods against saved local products.
- Clearly labelled estimates and user confirmation.

## Future

- Opt-in community product catalogue or upstream contribution support.
- Regional/offline product packs.
- Additional languages and accessibility improvements.
