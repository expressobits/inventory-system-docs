## Addon Features
The inventory system addon currently contains:
### [Core](https://github.com/expressobits/inventory-system/wiki/Core-Features)
Scripts with logical inventory system (Including node scripts for using Inventory)

Located in the *core* folder.

### Craft System
Core-based system that implements item creation logic (including node scripts such as Crafter)

Located in the *craft* folder.

### Features Editor
Scripts that display a custom editor for editing addon features.

Located in the *editor* folder.

### Multiplayer Features
Scripts that extend core and craft scripts creating a version that is compatible with Godot 4's high-level network.

Located in the *multiplayer* folder

### UI
Content connecting the addon node logic with the user interface.
Attention: This feature is not mandatory, in the FPS example the use of a closet is demonstrated so that a UI is not necessary to show the contents of the inventory.
Some developers tend to confuse an inventory system with UI features.

### Icons
Folder that includes icons to be displayed by resources or the editor.


***
## Demo Features

The inventory system demo has other extra features, these should be used as an example of a possible implementation of the addon:

### Base
Folder that contains the resources created for example, such as items, recipes, craft stations, categories and the database (database.tres)
A script is also included here that configures the inputs for the demo to work (default_actions.gd and setup_keys.gd)

### FPS
Folder containing scripts to demonstrate a first person singleplayer. This includes droppable items, items that remain in the player's hand, level, materials and props.
There is also some specific logic added here, such as campfire.gd.

### MP
Folder that extends FPS features for high-level network demonstration of Godot 4.

### Assets
Folder containing graphic resources for the example, most resources are authored by Kenney (https://kenney.nl/)