# Build and contribution workflow

## Branch policy

- `main` is the stable baseline.
- Feature and fix work is performed on dedicated branches.
- Changes enter `main` through pull requests.
- Direct commits to `main` are reserved for explicit, exceptional decisions.

## Pull-request expectations

A change should include, where relevant:

- Implementation
- Tests
- Public documentation
- Privacy impact notes
- Translation changes
- Changelog update
- Licence or attribution changes

## Development environments

- Primary PC workflow: Android Studio, Git, GitHub CLI, local Codex/repo-aware tools, emulator, and physical-device testing.
- Secondary phone workflow: AndroidIDE, Termux, GitHub Mobile, and direct device testing.

The PC workflow remains authoritative for release builds and production signing.

## Signing

Signing configuration should exist from the initial Android scaffold but read secrets only from environment variables or ignored local files. Contributors and F-Droid must be able to build unsigned release artifacts without production secrets.
