# Architecture direction

No Android implementation has been selected or committed yet. The initial architecture should support the following boundaries.

## Suggested layers

- **UI:** Compose-based screens, navigation, themes, accessibility, and camera flows.
- **Domain:** products, portions, meals, daily logs, targets, provenance, validation, and import/export rules.
- **Data:** local database, settings persistence, product lookup clients, OCR adapters, and optional AI adapters.
- **Platform:** camera, barcode recognition, notifications, file access, and external browser intents.

## Required separations

- Personal diary data must be separate from shareable product data.
- Online providers must be replaceable and optional.
- AI-assisted extraction must never be treated as verified label truth.
- F-Droid-compatible builds must not depend on proprietary SDKs.
- Release signing secrets must remain outside the source tree.

## Offline-first behaviour

Previously confirmed products and all diary features should work offline. Network requests should populate or refresh the local catalogue rather than becoming a permanent runtime dependency for common entries.
