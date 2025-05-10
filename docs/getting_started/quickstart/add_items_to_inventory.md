# Add items to Inventory

## Setup

Let's start with an empty scene

![image](https://github.com/expressobits/inventory-system/assets/1673249/73f81121-2288-46d6-b38c-2cf2d3ce63a3)

Add an inventory node, the inventory node is the main structure of this addon.

> **Note:** Understanding the basics is important to understand the flexibility of this addon.

![godot windows opt tools 64_FWHxsDbJGb](https://github.com/expressobits/inventory-system/assets/1673249/29e461a7-fa7e-474a-a89c-2525d0a103cc)

After adding the node, it will display a warning indicating that it needs to configure its database.

> **Note:** The inventoryDatabase is where the item structures and their attributes will be saved, important data, for example, an item's identifier, are contained within this resource.

This tutorial does not cover the database, we will use the database already available in the demo, to understand more about Inventory Database, check the tutorials about it.

![image](https://github.com/expressobits/inventory-system/assets/1673249/a87dd6b1-308c-4712-9483-266e8ae2b836)

Define the database, it should look like this.

![image](https://github.com/expressobits/inventory-system/assets/1673249/2cc35878-e94f-44d9-81f6-14c087b4458a)

In the node inspector, we can see the current inventory slots, we will use it to view what is available within the inventory. Don't change anything now.

![image](https://github.com/expressobits/inventory-system/assets/1673249/2c76aa84-34bc-46c3-8d1e-7fda7c2a38a5)

Create a test script on the parent node of the inventory node, it will be used for all our tests from now on.

![godot windows opt tools 64_elGgAzjtnD](https://github.com/expressobits/inventory-system/assets/1673249/b62be47d-67b6-4516-8183-e5a77fd02493)

## Add Items to Inventory

Let's create a variable pointing to the inventory, dragging it to the script while holding the control key.

![godot windows opt tools 64_emNvmbmg6P](https://github.com/expressobits/inventory-system/assets/1673249/80ee0177-c02c-43d4-bf9f-f19bbd2b9782)

We added code to display slots each time we click the configured action "interact" which in the demo is the E key
```gdscript title="add_items.gd" linenums="1"
func _process(delta):
	if Input.is_action_just_pressed("interact"):
		print("Inventory Slots:")
		for slot in inventory.slots:
			print("A Slot")
```

The result is this:
```
Inventory Slots:
A Slot
A Slot
A Slot
A Slot
A Slot
A Slot
A Slot
A Slot
A Slot
A Slot
A Slot
A Slot
A Slot
A Slot
A Slot
A Slot
```

Modify the code now to display when there is an item in the slot, its name and quantity, if not it displays the message "Empty"
```gdscript title="add_items.gd" linenums="1"
func _process(delta):
	if Input.is_action_just_pressed("interact"):
		print("Inventory Slots:")
		for slot in inventory.slots:
			if slot.item != null:
				print(slot.item.definition.name," x ", slot.amount)
			else:
				print("Empty")
```

Let's configure an item to be added, add a variable to link an item to the script, so we can add it to the inventory:
```gdscript title="add_items.gd" linenums="1"
...
@onready var inventory = $Inventory

# Add this 👇
@export var item : Item

# Called when the node enters the scene tree for the first time.
func _ready():
...
```

Place an item in the inspector, here we place the 'wood' item that is in the demo database
![image](https://github.com/expressobits/inventory-system/assets/1673249/ddda5ce5-1d37-4373-8e90-9f4b299c2200)


We added code that adds an item each time we click the Q key
```gdscript title="add_items.gd" linenums="1"
			print(slot.item.definition.name," x ", slot.amount)
			else:
				print("Empty")
        # Add this 👇
	if Input.is_action_just_pressed("add_item_a"):
		inventory.add(item, 1)
```

Now after typing F1 (key that adds item configured in the demo) and then E (interaction key configured in the demo), you can see that an item has been added to the inventory.
```
Inventory Slots:
Wood x 1
Empty
Empty
Empty
Empty
Empty
Empty
Empty
Empty
Empty
Empty
Empty
Empty
Empty
Empty
Empty
```
