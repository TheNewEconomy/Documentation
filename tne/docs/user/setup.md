# TNE Setup

## Download Pages

List Of Download Pages:

- [Spigot](https://www.spigotmc.org/resources/the-new-economy.7805/)

- [Paper Hangar](https://hangar.papermc.io/TNE/TheNewEconomy)

- [Sponge](https://ore.spongepowered.org/TheNewEconomy/TheNewEconomy)

- Fabric **Coming Soon**

- [Bungee](https://ci.codemc.io/job/creatorfromhell/job/TNE/lastBuild/net.tnemc$BungeeCore/)

- [Velocity](https://ci.codemc.io/job/creatorfromhell/job/TNE/lastBuild/net.tnemc$VelocityCore/)

- Redis **Built-in, no download needed**

## Installation Steps

=== "Basic Installation"

    1. **Download the TNE jar for your platform from the download links above**

    2. **Place in the downloaded jar in the plugin/mod folder for your server software**

    3. **Startup the server**

    4. **Shutdown, configure accordingly, and restart**


=== "Proxy Installation"

    1. **Download your proxy platform's jar from the download links above**

    2. **Place the jar in your proxy's plugin/mod folder**

    3. **Start your proxy server**


=== "Share Balances Across Servers"

    **Use this step only if you want to share balances across servers**

    **Server Configuration**

    1. **Ensure Consistency in Server Names and Default World Names**

        - Check and ensure that the server name and default world name are the same in each server's `config.yml`.
        - If the default world name differs and needs to be overridden in TNE, update the `Core.Region.DefaultRegion` value accordingly.

       ![Config.yml Image](https://i.imgur.com/6ZzWXgZ.png)

    2. **Update Server Names (Optional)**

        - Optionally, update the server name in each server's `config.yml`.
        - Ensure that the updated server name is consistent across all connected servers by updating the `Core.Server.Name` in each `config.yml`.

    3. **Ensure Unique Core.ServerID**

        - Verify that the `Core.ServerID` is different in each `config.yml`.
        - If you've copied and pasted the `config.yml`, remove the `ServerID` configuration to let it regenerate on the next startup.

       ![Config.yml Image](https://i.imgur.com/iTS6zyI.png)

    **Currency Configurations**

    1. **Ensure Consistency in Currency Configurations**

        - Verify that the currency UUID is the same across all servers.
        - Configure the currency settings as required.
        - Start each server and let it generate a UUID for the currency's YAML.
        - Copy over the configurations to ensure consistency.

       ![Currency Config Image](https://i.imgur.com/huEu64e.png)

    2. **Verify Currency Configurations**

        - Double-check the currency configurations to ensure they match across all servers.
        - Adjust settings as necessary to maintain consistency.