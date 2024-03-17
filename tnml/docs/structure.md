# TNML Structure

The TNML (The New Menu Library) provides a robust framework for creating graphical user interfaces (GUIs) in Minecraft plugins. This markdown page outlines the essential classes and builders within TNML, highlighting their functionalities and use cases.

## Menu Class

The `Menu` class represents a menu in TNML, providing methods for managing pages, handling player interactions, and defining menu properties.

### Key Features
- **Pages:** Allows the addition of pages containing icons.
- **Interactions:** Defines click actions and handles player interactions.
- **Callbacks:** Supports open and close callbacks for additional customization.

## Page Class

The `Page` class in TNML represents an individual page within a menu. It contains methods for adding icons and defining click handlers.

### Key Features
- **Icons:** Manages a collection of icons on the page.
- **Click Handlers:** Defines a click handler function for custom actions.

## Icon Class

The `Icon` class represents an icon within a menu, providing functionalities for handling click actions, constraints, and dynamic item display.

### Key Features
- **Click Actions:** Allows the definition of actions upon clicking the icon.
- **Constraints:** Supports constraints for conditional behaviors.
- **Dynamic Item Display:** Can dynamically change its displayed item based on conditions.

## StateIcon Class

The `StateIcon` class extends the `Icon` class and represents an icon with dynamic states. It allows the icon to change its appearance based on a state handler.

### Key Features
- **Dynamic States:** Supports multiple states with associated items.
- **State Handler:** Dynamically determines the state of the icon based on the current state.

## IconBuilder Class

The `IconBuilder` class is a builder for creating instances of the `Icon` and `StateIcon` classes. It provides methods for configuring items, slots, click handlers, and constraints.

### Key Methods
- **withItemProvider:** Sets the item provider function for dynamic item display.
- **withSlot:** Sets the slot for the icon.
- **withClick:** Sets the click handler for the icon.
- **withConstraint:** Adds a constraint to the icon.
- **withActions:** Adds actions to the list of actions for the icon.
- **withStateID, withDefaultState, withStateHandler:** Configures state-specific properties for StateIcon.

## MenuBuilder Class

The `MenuBuilder` class is a builder for creating instances of the `Menu` class. It provides methods for setting menu properties, adding pages, and specifying open/close callbacks.

### Key Methods
- **withTitle, withRows:** Sets the title and number of rows for the menu.
- **withOpenCallback, withCloseCallback:** Sets the open and close callbacks.
- **withPages:** Adds pages to the menu using varargs.

## PageBuilder Class

The `PageBuilder` class is a builder for creating instances of the `Page` class. It provides methods for adding icons, setting click handlers, and configuring the page.

### Key Methods
- **withIcons:** Adds icons to the page.
- **withClickHandler:** Sets the click handler for the page.

## Useful Classes

### Constraint Interface

The `Constraint` interface represents a constraint applied to an object, serving as a property. It includes methods for validation, conversion, and obtaining default values.

#### Built-In

Currently, TNML only has two built-in Constraints via the `IconStringConstraints` class.

##### ICON_PERMISSION
The `ICON_PERMISSION` sets the permission node required to use the click action for an icon.

##### ICON_MESSAGE
The `ICON_MESSAGE` sets a message sent to a player when they click an icon.

### IconAction Class

The `IconAction` class represents an action performed on an icon within a menu. It provides a common structure for different types of icon actions.

#### Built-In
TNML provides a few built-in icon action classes for developers to utilize out of the box.

##### ChatAction
The `ChatAction` allows an icon to accept chat-based player input. It provides a Predicate that is called on the following chat message from the viewer.

##### DataAction
The `DataAction` stores data attached to the `MenuViewer` that clicked the icon. This data stays with the viewer until they close out of a menu to allow for temporary data storage purposes.

##### RunnableAction
The `RunnableAction` runs code when an icon is clicked.

##### SwitchMenuAction
The `SwitchMenuAction` switches menus when an icon is clicked.

##### SwitchPageAction
The `SwitchPageAction` switches pages when an icon is clicked.

## Conclusion

Understanding the structure of TNML involves familiarizing yourself with the `Menu`, `Page`, and `Icon` classes, along with their respective builder classes. These components offer a flexible and robust framework for creating interactive menus and graphical interfaces in Minecraft plugins.