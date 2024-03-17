# Example Usage

Here's a simple example using `MenuBuilder` to create a basic menu:

```java
import net.tnemc.menu.bukkit.BukkitMenuHandler;
import net.tnemc.menu.bukkit.BukkitPlayer;
import net.tnemc.menu.core.Menu;
import net.tnemc.menu.core.MenuHandler;
import net.tnemc.menu.core.builder.IconBuilder;
import net.tnemc.menu.core.builder.MenuBuilder;
import net.tnemc.menu.core.builder.PageBuilder;
import net.tnemc.menu.core.icon.action.impl.ChatAction;
import net.tnemc.menu.core.icon.action.impl.SwitchMenuAction;
import net.tnemc.menu.core.icon.constraints.IconStringConstraints;
import net.tnemc.menu.core.manager.MenuManager;
import net.tnemc.menu.core.utils.SlotPos;
import net.tnemc.menu.core.viewer.MenuViewer;
import org.bukkit.Bukkit;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.event.player.PlayerJoinEvent;
import org.bukkit.plugin.java.JavaPlugin;

import java.util.Locale;
import java.util.Optional;

/**
 * BukkitTNML
 *
 * @author creatorfromhell
 * @since 1.5.0.0
 */
public class BukkitTNML extends JavaPlugin implements Listener {

  private MenuHandler menu;

  @Override
  public void onEnable() {

    Bukkit.getPluginManager().registerEvents(this, this);

    this.menu = new BukkitMenuHandler(this, true);

    // Example Menu
    final Menu exampleMenu = new MenuBuilder("example")
            .withTitle("Example GUI")
            .withRows(5)
            .withPages(
                    new PageBuilder(1)
                            .withIcons(
                                    new IconBuilder(menu.stackBuilder().display("Example Icon").of("RED_WOOL", 1))
                                            .withSlot(new SlotPos(2, 3))
                                            .withConstraint(IconStringConstraints.ICON_MESSAGE, "You switched a menu!")
                                            .withActions(new SwitchMenuAction("example2"))
                                            .build(),

                                    new IconBuilder(menu.stackBuilder().display("Example Icon2").of("GREEN_WOOL", 1))
                                            .withSlot(new SlotPos(2, 6))
                                            .withConstraint(IconStringConstraints.ICON_MESSAGE, "Please type: hello")
                                            .withActions(new ChatAction(callback -> {

                                              if(!callback.getMessage().equalsIgnoreCase("hello")) {
                                                //Make the player type their message again since they didn't type hello.
                                                return false;
                                              }

                                              final Optional<MenuViewer> viewer = MenuManager.instance().findViewer(callback.getPlayer().identifier());
                                              if (viewer.isPresent()) {
                                                viewer.get().addData("example-data", callback.getMessage());
                                              }
                                              return true;
                                            })).build()
                            ).build()
            )
            .build();

    // Example Menu2
    final Menu exampleMenu2 = new MenuBuilder("example2")
            .withTitle("Example2 GUI")
            .withRows(3)
            .withPages(
                    new PageBuilder(1)
                            .withIcons(
                                    new IconBuilder(menu.stackBuilder().display("Example2 Icon").of("STONE", 1))
                                            .withSlot(new SlotPos(2, 5))
                                            .withConstraint(IconStringConstraints.ICON_MESSAGE, "You switched a menu and found the new button!")
                                            .withActions(new SwitchMenuAction("example"))
                                            .build(),
                                    new IconBuilder(menu.stackBuilder().display("Dynamic Input-based Icon").of("STONE", 1))
                                            .withItemProvider(player -> {
                                              Optional<MenuViewer> viewer = MenuManager.instance().findViewer(player.identifier());
                                              if (viewer.isPresent()) {
                                                Optional<Object> display = viewer.get().findData("example-data");
                                                if (display.isPresent()) {
                                                  return menu.stackBuilder().display((String) display.get()).of("GRASS", 1);
                                                }
                                              }
                                              return menu.stackBuilder().display("Default Display").of("STONE", 1);
                                            })
                                            .withSlot(new SlotPos(2, 2))
                                            .build(),

                                    new IconBuilder(menu.stackBuilder().display("Default State").of("BLACK_WOOL", 1))
                                            .withStateID("TEST-STATE")
                                            .withDefaultState("STATE-0")
                                            .withStateHandler(currentState -> {
                                              switch (currentState.toUpperCase(Locale.ROOT)) {
                                                case "STATE-0":
                                                  return "STATE-1";
                                                case "STATE-1":
                                                  return "STATE-2";
                                                case "STATE-2":
                                                  return "STATE-3";
                                                default:
                                                  return "STATE-0";
                                              }
                                            })
                                            .withState("STATE-1", menu.stackBuilder().display("State 1").of("BROWN_WOOL", 1))
                                            .withState("STATE-2", menu.stackBuilder().display("State 2").of("BLUE_WOOL", 1))
                                            .withState("STATE-3", menu.stackBuilder().display("State 3").of("GREEN_WOOL", 1))
                                            .build()
                            ).build()
            ).build();

    // Adding menus to the manager
    MenuManager.instance().addMenu(exampleMenu);
    MenuManager.instance().addMenu(exampleMenu2);
  }

  @EventHandler
  public void onJoin(final PlayerJoinEvent event) {

    final BukkitPlayer player = new BukkitPlayer(event.getPlayer(), this);
    MenuManager.instance().open("example", 1, player);
  }
}
```

This example demonstrates creating two menus with various actions and a state icon, which is able to change items based on a "state" variable.