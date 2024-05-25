# Commands

* `/phantomworlds backup <world>` - Backup a world.

* `/phantomworlds compatibility` - Run a compatibility check for your server.

* `/phantomworlds create <world> <environment> [options...]` - Start the process of creating a new world.
  * Argument 1: `world` (required) - World name.
  * Argument 2: `environment` (required) - The world environment.
    * Valid options are as follows:
      * `NORMAL` (aka. the overworld [you are probably looking for this one])
      * `NETHER`
      * `THE_END`
      * `CUSTOM` (advanced users only)
  * Argument 3: `options...` (optional) - Additional world options to be specified, such as world generators, seeds, etc.
    * `generateStructures:` - Whether structures, such as villages will be generated in this world.
      * Valid options: `true` and `false`; e.g. `generateStructures:false`
    * `generator` - The world generator to use for this world.
      * Valid options: `<YourGeneratorHere>`; e.g. `generator:CleanroomGenerator:.` if you are using [CleanroomGenerator](https://dev.bukkit.org/projects/cleanroomgenerator)
    * `generatorSettings` - Advanced generator settings, supplied in JSON.
      * Valid options: Too many to supply here; read more about it [here](https://minecraft.wiki/w/Java_Edition_level_format#generatorOptions_tag_format).
    * `hardcore` - Whether this world will follow the hardcore ruleset.
      * Valid options: `true` and `false`; e.g. `hardcore:true`
    * `seed` - The seed to use.
      * Valid options: `<YourSeedHere>`; e.g. `seed:847479976687857`
    * `type` - The type of world you want generated.
      * Valid options: `AMPLIFIED`, `FLAT`, `LARGE_BIOMES` and `NORMAL`; e.g. `type:FLAT`
    * `spawnMobs` - Whether monsters can spawn in this world.
      * Valid options: `true` and `false`; e.g. `spawnMobs:false`
    * `spawnAnimals` - Whether animals can spawn in this world.
      * Valid options: `true` and `false`; e.g. `spawnAnimals:false`
    * `keepSpawnInMemory` - Whether the spawn area will be loaded in memory at all times (for high traffic areas, leave this on)
      * Valid options: `true` and `false`; e.g. `keepSpawnInMemory:false`
    * `allowPvP` - Whether players will be able to attack other players in this world.
      * Valid options: `true` and `false`; e.g. `allowPvP:false`
    * `difficulty` - The difficulty for this world.
      * Valid options: `PEACEFUL`, `EASY`, `NORMAL` and `HARD`; e.g. `difficulty:HARD`

* `/phantomworlds debug <method>` - Debug a method from PhantomWorlds (for assisting a developer find bugs).

* `/phantomworlds delete <world>` - Delete a world.

* `/phantomworlds import <world>` - Import a world.

* `/phantomworlds info` - Learn more about PhantomWorlds.

* `/phantomworlds list` - List all worlds currently being handled by PhantomWorlds.

* `/phantomworlds load <world>` - Load an unloaded world

* `/phantomworlds reload` - Reload configuration files and world files from PhantomWorlds.

* `/phantomworlds set effects <world> [effects]` - Set the potion effects to be applied to players in this world.

* `/phantomworlds set gamemode <world> <gamemode>` - Set the gamemode for this world.

* `/phantomworlds set portal <world> <portal type> <world to>` - Set where the specified portal type takes players in this world.

* `/phantomworlds set whitelist <world> <whitelist(true/false)>` - Set whether there is a whitelist for this world or not.

* `/phantomworlds setspawn [x] [y] [z] [world] [yaw] [pitch]` - Set the spawn location for a world.

* `/phantomworlds spawn [player]` - Teleport yourself or another player to the spawn location for a world.

* `/phantomworlds teleport <world>` - Teleport to a world.

* `/phantomworlds unload <world>` - Unload a world from the server (does NOT delete world data).

(Thanks [@ArtelGG](https://github.com/ArtelGG/) for contributing this part of the Wiki!)

# Permissions

```yaml
permissions:
  phantomworlds.*:
    default: op
    description: 'All PhantomWorlds permissions, ideally given to administrators.'
    children:
      phantomworlds.knows-vanished-users: true
      phantomworlds.command.phantomworlds.*: true


  phantomworlds.world.bypass.gamemode:
    default: op
    description: 'Used to bypass the gamemode setting for worlds.'


  phantomworlds.world.bypass.effects:
    default: op
    description: 'Used to bypass the effects setting for worlds.'

  phantomworlds.knows-vanished-users:
    default: op
    description: 'Users with this permission will ignore the status of vanished players when using commands from PhantomWorlds, such as in tab-completion suggestions.'

  phantomworlds.command.phantomworlds.*:
    default: op
    description: 'Ability to run all /pw commands.'
    children:
      phantomworlds.command.phantomworlds: true
      phantomworlds.command.phantomworlds.backup: true
      phantomworlds.command.phantomworlds.compatibility: true
      phantomworlds.command.phantomworlds.create: true
      phantomworlds.command.phantomworlds.debug: true
      phantomworlds.command.phantomworlds.import: true
      phantomworlds.command.phantomworlds.info: true
      phantomworlds.command.phantomworlds.list: true
      phantomworlds.command.phantomworlds.load: true
      phantomworlds.command.phantomworlds.setspawn: true
      phantomworlds.command.phantomworlds.set.effects: true
      phantomworlds.command.phantomworlds.set.gamemode: true
      phantomworlds.command.phantomworlds.set.portal: true
      phantomworlds.command.phantomworlds.set.whitelist: true
      phantomworlds.command.phantomworlds.teleport: true
      phantomworlds.command.phantomworlds.spawn: true
      phantomworlds.command.phantomworlds.unload: true
      phantomworlds.command.phantomworlds.reload: true

  phantomworlds.command.phantomworlds:
    default: op
    description: 'Ability to run /pw'

  phantomworlds.command.phantomworlds.backup:
    default: op
    description: 'Ability to run /pw backup'

  phantomworlds.command.phantomworlds.compatibility:
    default: op
    description: 'Ability to run /pw compatibility'

  phantomworlds.command.phantomworlds.debug:
    default: op
    description: 'Ability to run /pw debug'

  phantomworlds.command.phantomworlds.create:
    default: op
    description: 'Ability to run /pw create'

  phantomworlds.command.phantomworlds.import:
    default: op
    description: 'Ability to run /pw import'

  phantomworlds.command.phantomworlds.info:
    default: true
    description: 'Ability to run /pw info'

  phantomworlds.command.phantomworlds.list:
    default: op
    description: 'Ability to run /pw list'

  phantomworlds.command.phantomworlds.load:
    default: op
    description: 'Ability to run /pw load'

  phantomworlds.command.phantomworlds.setspawn:
    default: op
    description: 'Ability to run /pw setspawn'

  phantomworlds.command.phantomworlds.set.effects:
    default: op
    description: 'Ability to run /pw set effects'

  phantomworlds.command.phantomworlds.set.gamemode:
    default: op
    description: 'Ability to run /pw set gamemode'

  phantomworlds.command.phantomworlds.set.portal:
    default: op
    description: 'Ability to run /pw set portal'

  phantomworlds.command.phantomworlds.set.whitelist:
    default: op
    description: 'Ability to run /pw set whitelist'

  phantomworlds.command.phantomworlds.teleport:
    default: op
    description: 'Ability to run /pw teleport'

  phantomworlds.command.phantomworlds.spawn:
    default: op
    description: 'Ability to run /pw spawn'

  phantomworlds.command.phantomworlds.unload:
    default: op
    description: 'Ability to run /pw unload'

  phantomworlds.command.phantomworlds.reload:
    default: op
    description: 'Ability to run /pw reload'
```
