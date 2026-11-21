# LumaBoost 1.21.11 — build repair

This project uses official Mojang mappings, Fabric, and Java 21.

Changes from previous LumaBoost build:
- Removed obsolete Yarn-mapped `KeyBindingAccessor.java` and `KeyBindingMixin.java` (not used by the mixin config).
- Replaced the unavailable `sendOverlayMessage(Component)` call with `displayClientMessage(Component, true)`.
- Kept `KeyMappingMixin` instant key handling and the toggle and Music & Sounds access code.

The uploaded `simple-mb-keys (7).zip` is a reference JAR plus source JAR, not a Gradle project. Its source was inspected as reference for original behavior. No local Minecraft build/test was possible here.

IMPORTANT: GitHub's web uploader does NOT delete files absent from the ZIP. Delete the obsolete files from your repository manually, or use Git locally to replace the project and commit the deletions. Also delete `InventoryButtons.java` if still present.
