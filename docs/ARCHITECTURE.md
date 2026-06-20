# Architecture direction

## Selected application architecture

Nutri Raccoon will use **Kotlin with Jetpack Compose** for the Android application UI.

The initial implementation should use a state-driven, modular architecture rather than concentrating screen construction, navigation, and feature logic in one activity. A single activity may host Compose navigation, while screen state and behavior remain separated by feature and responsibility.

This decision selects the architectural direction only. Exact Kotlin, Compose, Android Gradle Plugin, Gradle, JDK, minimum SDK, and target SDK versions remain foundation decisions that must be reviewed and recorded separately.

## Suggested layers

- **UI:** Compose screens, navigation, themes, accessibility, camera flows, reusable visual tokens, and reusable components.
- **Presentation:** ViewModels, immutable UI state, user events, validation state, and screen coordination.
- **Domain:** products, portions, meals, daily logs, targets, provenance, validation, and import/export rules.
- **Data:** local database, settings persistence, repositories, product lookup clients, OCR adapters, and optional AI adapters.
- **Platform:** camera, barcode recognition, notifications, file access, and external browser intents.

## UI structure

Start with one app module and feature-oriented packages rather than premature Gradle modularisation. A practical initial structure is:

```text
ui/
  theme/
  components/
  navigation/
  home/
  history/
  products/
  settings/
  about/
  scanner/

presentation/

domain/
  model/
  usecase/
  validation/

data/
  local/
  repository/
  productlookup/
  ocr/
  ai/

platform/
  camera/
  files/
  browser/
```

Introduce separate Gradle modules only when their isolation, testability, ownership, or build-performance benefit clearly outweighs the additional maintenance.

## UI foundation requirements

Before building many screens, establish shared Compose design foundations for:

- spacing, typography, colour, shape, elevation, and touch-target tokens;
- app bars and bottom navigation;
- rounded cards and section containers;
- primary and secondary actions;
- meal-section headers and product rows;
- portion controls and form fields;
- information strips, empty states, dialogs, and sheets;
- light, dark, Cozy Pastel Light, and Cozy Pastel Dark themes.

The mascot artwork and other static illustrations should remain normal resources. Custom drawing should be limited to contained elements that genuinely need it, such as scanner guides, progress graphics, or small charts. Whole-screen custom Canvas rendering is not the application baseline.

## State and navigation

- Use Compose navigation for app destinations and nested flows.
- Derive visible UI from explicit state rather than imperatively mutating large view trees.
- Keep screen state in ViewModels where lifecycle persistence and coordination are needed.
- Keep domain and data rules outside composables.
- Do not let camera, OCR, network, or database implementation details become direct UI dependencies.

## Required separations

- Personal diary data must be separate from shareable product data.
- Online providers must be replaceable and optional.
- AI-assisted extraction must never be treated as verified label truth.
- F-Droid-compatible builds must not depend on proprietary SDKs.
- Release signing secrets must remain outside the source tree.
- Optional camera, barcode, OCR, network, and AI capabilities must remain behind replaceable interfaces.

## Offline-first behaviour

Previously confirmed products and all diary features should work offline. Network requests should populate or refresh the local catalogue rather than becoming a permanent runtime dependency for common entries.
