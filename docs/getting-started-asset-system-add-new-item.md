---
id: asset_system_new_item
title: Latin-ish
sidebar_label: Add A New Creature
---

We now have our information block, now let's add a tool for this block:
* It should work like the other items known from the inventory (icon, equipable, ...)
* It should have a cool icon, why not use some glasses to retrieve the information?
* It should help us to get our information really fast ;)
Ok, we have a new block, let's add a tool to work with the block.
Items are defined as prefabs and are commonly based on the ```engine:iconItem``` or a subtype of it.
In terms of programming, this is like an extension. You may want to have a look at the engine prefabs ```iconItem.prefab``` and ```itemBase.prefab``` to see what is defined by default.

The icon for a tool is defined as a [[Texture Atlas|Texture Atlas]].
For the additional damage, we need a special [[Damage Type|Damage Types]].


We need only one icon for our glasses. There are three spaces left on the atlas texture for your own experiments (32x32 texture and one 16x16 icon on the top left):

[[images/tutorialTools.png]]

1. Add the image to ```assets/textures/tutorialTools.png```.

2. Now we will create an atlas, to tell the game where the icon is located:
    
    Create a new file for the atlas at ```assets/atlas/tutorialTools.atlas``` with the following content:
    ```
    {
        "texture" : "TutorialAssetSystem:tutorialTools",
        "textureSize" : [32, 32],
        "grid" : {
            "tileSize" : [16, 16],
            "gridDimensions" : [2, 2],
            "tileNames" : [
                "theGlasses", "", "", ""
            ]
        }
    }

    ```
    As you can see, we defined an atlas for a 32x32 texture, with a size of 16x16 for each icon and an overall dimension of 2x2 tiles. The first tile 
    - texture points to our png file
    - textureSize defines the overall size of the atlas texture
    - grid defines the size of each tile and the dimensions of the entire atlas
    - tileNames is a list of the icons. As our atlas contains only one item, we have only the glasses :)

3. Now bring it all together and define the prefab for the item:

    Create a new file at `assets/prefabs/theGlasses.prefab` with the following content:
    ```
    {
        "parent" : "engine:iconItem",
        "DisplayName" : {
            "name" : "The Glasses"
        },
        "Item" : {
            "icon" : "TutorialAssetSystem:tutorialTools#theGlasses",
            "damageType" : "TutorialAssetSystem:glassesDamage"
        }
    }
    ```
    - parent is the parent prefab. The ```engine:iconItem``` defines most of the stuff required for a default item.
    - DisplayName should be self explanatory
    - The icon defines the icon from our atlas. The path reads as: Search in the ```TutorialAssetSystem``` module for an atlas named ```tutorialTools``` and use the icon with the name `theGlasses`.
    - The damageType refers to the _damageTypes_ prefabs. We will define now in a new file at ```assets/prefabs/damageTypes/glassesDamage.prefab``` with the following content:
    ```
    {
        "parent" : "engine:physicalDamage",
        "blockDamageModifier" : {
            "materialDamageMultiplier" : {"information" : 21}
        }
    }
    ```
    _Remember the block category we used in the [Add New Block](https://github.com/Terasology/TutorialAssetSystem/wiki/Add-New-Block)?_
    ```
    {
        "displayName": "Information",
        "categories" : ["information"],
        "hardness": 42    
    }
    ```
    _The `materialDamageMultiplier` refers to the `categories` values. Multiple entries can be added to both fields using a comma-separated list (image something like a chest which is a wooden item but may also be some kind of furniture)._
    - We used the physicalDamage from the engine as default, as it is the common one for tools.
    - The damage modifier refers to the material category from our block definition. Our glasses should do 21 times the damage of a pickaxe on our information block.

You can now give yourself your glasses ingame using ```give theGlasses```. If you placed the information block using the steps from above, you should be able to smash it super fast with your brand new glasses ;)

[[images/screen2.png]]