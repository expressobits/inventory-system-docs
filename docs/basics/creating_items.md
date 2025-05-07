### Create Resource Item Definition

To create new items in a database, select the "_**New Item**_" option

![image](https://github.com/expressobits/inventory-system/assets/1673249/18413bc9-a9e1-41cc-a588-05ee0318ceed)

Here we have two options, one creates the ItemDefinition resource and also adds it to the open database, the other has the option of choosing an ItemDefinition resource that already exists in the project.
For this tutorial choose the first option, which creates a new resource and adds it to the database.

![image](https://github.com/expressobits/inventory-system/assets/1673249/a6ad6e21-8980-4c05-a977-5b8fc887a7c3)

Choose name of ItemDefinition and your location:
![image](https://github.com/expressobits/inventory-system/assets/1673249/c3ded3ef-7d3b-4083-8cd4-060dac1dda5b)

If created successfully your editor will update to show the item in the "Items" tab
![image](https://github.com/expressobits/inventory-system/assets/1673249/765545f7-13f6-413a-8608-2424b7c98b06)

### Setup New Item Definition
Here we can demonstrate a little of the editor.
It contains various information about the item:
- Name: Name to be displayed or used as additional identification (It is your responsibility to use this field)
- ID: Integer identification of the item, used to get the item based on a list of items easily using the id
Note: The base node (NodeInventories) has two methods that use the database field (InventoryDatabase) that use this id to facilitate access to items

```gdscript
# Get id of item
int get_id_from_item(item: ItemDefinition)
# Get resource (ItemDefinition) from id param
ItemDefinition get_item_from_id(id: int)
```

