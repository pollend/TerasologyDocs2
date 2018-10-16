---
id: asset_system_block_definitions
title: Latin-ish
sidebar_label: Add A New Creature
---

Block data can be defined on four locations, all inside the ```assets``` folder:

1. ```blocks``` contains the block definitions. All files in this folder should have a ```.block``` extension.

    Block definitions are limited to a number of properties. See [https://github.com/Terasology/TutorialAssetSystem/wiki/Block-Attributes](https://github.com/Terasology/TutorialAssetSystem/wiki/Block-Attributes) for a complete list.

2. ```blockTiles``` contains the block tile textures. They should be ```.png``` files with a size of 16x16.

3. ```shapes``` contains special shapes for blocks with a unique model. Files in this folder should have a ```.shape``` extension. See [https://github.com/MovingBlocks/Terasology/wiki/Shape-Architecture](https://github.com/MovingBlocks/Terasology/wiki/Shape-Architecture) for a full reference on how to generate these files from blender.

4. ```prefabs``` contains additional definitions for a block. Files in this folder should have a ```.prefab``` extension. Everything which can not be defined in the ```.block```-file should be defined here. In most of the cases, this will be Components and their initial values. Think about a spike component on a cactus block, which defines how many damage you will take if you touch the block.

By naming conventions, all files for one block must have the same name. So for our cactus block, we would define ```blocks/cactus.block```, ```blockTiles/cactus.png```, ```shapes/cactus.shape```, ```prefabs/cactus.prefab```
