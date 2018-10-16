---
id: getting-started-asset-system-add-new-block
title: Latin-ish
sidebar_label: Add A New Block
---

Let's add a simple block first:
* It should be solid
* It should have a simple texture (how about an "information"-I?)
* It should be hard to destroy as gaining new information may be tough ;)

To understand which file defines which aspect of a block and where to put all these files please have a look at the [[Block Definition|Block Definition]] page.

Using this information, the definition of our new block is straightforward:

1. The block will be named ```information```, as said before: use the same name for all files.  
    For the texture, place the ```information.png``` inside the ```blockTiles``` folder:  
    ```information.png```: [[images/information.png]]. Feel free to experiment with any other image you like.

2. Now we define the actual block in a new file ```blocks/information.block``` with the following content:
    ```
    {
        "displayName": "Information",
        "categories" : ["information"],
        "hardness": 42    
    }
    ```
    The definition only requires non-default values, so we will be fine with this. For example our ```information.png```-Texture will be picked automatically for us, based on the filename. Omit the category for now, this will define the material type which is required later in the tutorial.

We omit the shape and prefab part here, so we are ready to test our block ingame.
Launch the game, create a new game and don't forget to enable the module before starting :)

Once ingame, open the console and execute the ```give information``` command.
If other information blocks are present, the full command for exact this block is ```give TutorialAssetSystem:Information```

If everything works as expected, the block is ready to be used ingame.

[[images/screen1.png]]

If you want a tool for this block, you may continue with the next step: [[Add New Item|Add New Item]]