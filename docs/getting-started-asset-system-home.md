---
id: asset_system_home
title: Latin-ish
sidebar_label: Add A New Creature
---


This is a small tutorial about basic usage of assets.

Prerequisites: You should have your workspace ready with Terasology in Eclipse or IntelliJ and be ready to launch gradle commands on the project. See the [Dev Setup](https://github.com/MovingBlocks/Terasology/wiki/Dev-Setup) for a full guide.
This tutorial will be written from an Eclipse perspective but should be easy to follow with IntelliJ though.

Every step from the tutorial is reflected in the module hosted in this repository.
You should be able to fetch the entire module via ```gradlew fetchModuleTutorialAssetSystem```.
It is not required to follow the tutorial but can be used to get a quick overview.

There are some pages with short documentation for different topics.
They are referenced from the tutorial pages but in case you need one of them right now:
* [[Block Definition|Block Definition]]
* [[Deltas and Overrides|Deltas and Overrides]]
* [[Damage Types|Damage Types]]
* [[Texture Atlas|Texture Atlas]]
* [[Block Families|Block Families]]

Apart from that feel free to get started:

## Setup the module
Create a module and add it to your workspace.

[[Setup|Setup]]

## Add a new block to the game
Define a simple block and place it ingame.

[[Add New Block|Add New Block]]

## Add a new item to the game
Create a tool to break the new block in a faster way.

* [[Add New Item|Add New Item]]
* [[Custom Block Shapes|Custom Block Shapes]]

## Blender Addon for Creatures
* [Installing Blender Add on](https://github.com/Terasology/TutorialAssetSystem/wiki/Installing-Blender-Add-on)  
* [Preparing Model for Export](https://github.com/Terasology/TutorialAssetSystem/wiki/Preparing-Model-for-Export)  
* [Using the Blender Add on](https://github.com/Terasology/TutorialAssetSystem/wiki/Using-the-Blender-Add-on)  



## Make a block activateable and create your own block family
Create a dice block which rotates on activation

[[Add A Dice|Add A Dice]]

## Related

If you are curious about asset formats and such themselves check out the [Gestalt Asset quick start](https://github.com/MovingBlocks/gestalt/wiki/Gestalt%20Asset%20Core%20Quick%20Start).

There are also further topics on how to use assets, for example the [[use of prefabs for module configuration|Prefab based Configuration]].

***
Anything wrong, outdated or missing? Feel free to open a new [issue](https://github.com/Terasology/TutorialAssetSystem/issues/new) or contribute to the tutorial yourself :)