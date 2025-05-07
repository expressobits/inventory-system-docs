This page demonstrates how an inventory [database](#feature/database){ data-preview } is used by the addon nodes.

After creating a database and filling it with information, such as items, you can start using it in your project through nodes that extend `NodeInventorySystemBase`:
* Inventory
* Hotbar
* InventoryHandler
* Crafter
* CraftStation

Let's take an example of adding an inventory node, after adding it we get a warning warning that we need to configure the database for this node

![image](https://github.com/expressobits/inventory-system/assets/1673249/7f560dae-7011-4782-95d4-b962d11cb8c3)

![image](https://github.com/expressobits/inventory-system/assets/1673249/a01d229d-83b5-44a8-9610-172cd7afd73f)

See the inventory node inspector, there we have the base class with the database property waiting to be configured:

![image](https://github.com/expressobits/inventory-system/assets/1673249/d09dc058-c0d4-4642-89a0-e9ed5e6fe17a)

Select the previously created database:

![image](https://github.com/expressobits/inventory-system/assets/1673249/40310ea4-c334-408d-96c8-e504ca3778bc)

Okay, now all items that will be added to the inventory will correspond to the database

Continue to the next tutorials:
[TODO] Using the Inventory node


