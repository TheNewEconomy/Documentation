## Requirements
* Requires a Spigot/Bukkit-based server (SpigotMC, PaperMC, CraftBukkit, etc).
* Oldest supported version is `MC 1.7`. Older versions may work but are unsupported. I will prioritize the newer versions over the older.

## Instructions
1. Download the plugin's `.jar` file from the [SpigotMC resource page](https://www.spigotmc.org/resources/phantomworlds.84099/).
2. Move the downloaded file into the `/plugins/` directory in your Minecraft server's folder.
3. If your server is running, stop your server with `/stop`.
4. Start your server. PhantomWorlds will generate its own directory consisting of various files which you may edit in `/plugins/PhantomWorlds/`.

## Optional Extra Steps
* If you wish to change any settings in the configuration files, go ahead. If you do make any changes, make sure you save your edits, then run `/pw reload` for the changes to take effect (or restart your server).
* You may want to allocate the various permissions to your permission plugin's rank groups - I recommend [LuckPerms](https://www.spigotmc.org/resources/luckperms.28140/).
  * See the [Commands and Permissions page](commands.md) for documentation concerning the assignment of these permissions.