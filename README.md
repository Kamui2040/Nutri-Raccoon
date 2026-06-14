# Nutri Raccoon

Nutri Raccoon is a planned cozy, privacy-first, open-source nutrition tracker for Android.

The app is intended to reduce repetitive food logging through a barcode-first product workflow, a local product database, label scanning as a fallback, and optional meal-photo assistance. The project is designed for a fully FLOSS Android build and future distribution through F-Droid and other no-fee channels.

> Project status: documentation and architecture planning. No application code has been added yet.

## Core direction

- Local-first nutrition diary with Breakfast, Lunch, Dinner, Snacks, and custom meal lists.
- Barcode lookup first, using open product-data sources where possible.
- Nutrition-label and ingredient OCR when a product is missing or incomplete.
- Reusable local products with practical portions such as slices, pieces, servings, and package fractions.
- Reusable meal templates for recurring meals, with one-tap addition and optional weekday schedules.
- Optional meal-photo recognition that clearly labels estimated values.
- Cozy raccoon-chef visual identity with standard and custom pastel themes.
- No ads, subscriptions, mandatory accounts, or paid feature unlocks.
- Optional Ko-fi support through the About dialog, opening in the external browser.
- German and English localisation initially, with system language as the default.
- Future opt-in community product-data exchange containing no contributor identity or personal diary data.

## Repository role

This public repository is the canonical source of truth for all application code, public documentation, licensed assets, translations, tests, CI configuration, and release metadata.

The private internal repository contains planning, raw QA material, unpublished research, and release operations. It must not contain a separate private fork of the application code.

## Licensing

- Application code: GPL-3.0-or-later.
- Original project artwork and documentation: CC BY-SA 4.0 unless a file states otherwise.
- Third-party components retain their original compatible licences.
- External product datasets retain their own database and content licences.

See [LICENSE](LICENSE) and [LICENSES/README.md](LICENSES/README.md).

## Privacy

Nutri Raccoon is intended to work without an account. Personal meal history, goals, body data, favourites, usage history, and private notes must remain local unless the user explicitly exports them. Community product contributions must contain product information only and no contributor identity.

See [PRIVACY.md](PRIVACY.md) and [docs/PRIVACY_MODEL.md](docs/PRIVACY_MODEL.md).

## Development workflow

`main` is the stable baseline. Implementation changes are made on branches and merged through pull requests. Public documentation, tests, privacy notes, and changelog entries should be updated with the related change.

See [docs/BUILD_WORKFLOW.md](docs/BUILD_WORKFLOW.md) and [CONTRIBUTING.md](CONTRIBUTING.md).
