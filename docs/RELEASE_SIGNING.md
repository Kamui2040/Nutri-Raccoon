# Release signing policy

## Principles

- Select a stable application ID before the first public APK.
- Create the long-lived production signing key before the first publicly distributed build.
- Never commit a keystore, password, key alias secret, token, or local signing configuration.
- Store the production key outside Git with encrypted backups in at least two secure locations.
- Publish only the signing certificate and fingerprint.

## Build configuration

The future Gradle setup should support:

- Debug builds without release secrets.
- Unsigned release builds for contributors and F-Droid.
- Signed release builds when environment variables or an ignored local properties file are present.

## Distribution goal

Aim for reproducible builds so F-Droid can verify and distribute the developer-signed APK, reducing signature conflicts between F-Droid, GitHub releases, and direct downloads.
