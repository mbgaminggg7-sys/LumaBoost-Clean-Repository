# LumaBoost options-button test

This build restores the secret Music & Sounds button without injecting into the screen render method.
The button is anchored near the bottom-right of the Music & Sounds screen (not inside the scrolling list).
Hold either Mac Option key (Alt) while that screen is open. Release it to hide the button.

1. Back up your previous JAR.
2. Replace the entire source tree on GitHub, including the updated mixin JSON and new interface.
3. Run Actions and install only the regular JAR, not the sources JAR.
4. Confirm Options and FOV work.
5. Open Music & Sounds and hold Option. Click the tiny dot near the lower-right area.
6. Verify keybindings and ON/OFF switch separately.

This project has NOT been compiled or tested in Minecraft here. If Options fails again, remove the JAR and send the runtime log.
