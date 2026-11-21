# Source review and crash fix (Minecraft 1.21.11)

Inspected the Java classes, mixin configuration, Fabric metadata, Gradle build files, GitHub Actions workflow and existing README.

## Confirmed crash
The provided crash log identifies `SoundOptionsSecretMixin` attempting to inject `init` into a Minecraft screen class that does not contain the expected target. This is a fatal mixin application failure.

## Change
Removed the entire SoundOptionsSecretMixin and its accessor interface. The secret button is now registered through Fabric API `ScreenEvents.AFTER_INIT` and `Screens.getButtons`, with visibility controlled on the client tick while holding either Option/Alt key. This avoids injecting into the Music & Sounds screen.

## Other review observations
- Existing KeyMapping mixin and accessor remain; they are necessary for the extra-key mechanism and were not implicated in the provided crash.
- Configuration remains in `config/mbkeys.json`; this is compatible with previous versions.
- `fabric.mod.json` still uses the existing mod ID `mbkeys` to preserve config and mod identity.
- The UI is called MB Keys internally in some labels; this is cosmetic, not a crash cause.
- No Java/Gradle build or Minecraft runtime test was performed in this environment. GitHub Actions must compile the project, and in-game behavior must be tested.

## Installation
Upload all repository contents to a **new empty GitHub repository** preserving directories. Run Actions -> build. Download artifact, extract and install only the main `lumaboost-1.0.0.jar` (not the `-sources.jar`). Remove the old mod JAR first.
