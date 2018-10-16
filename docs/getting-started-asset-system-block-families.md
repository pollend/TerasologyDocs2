---
id: asset_system_block_families
title: Latin-ish
sidebar_label: Add A New Creature
---

A block family is a group of multiple variations of one block, such as the same base block but in different shapes. The main purpose of a block family is to allow the user to collect multiple of those block variants for a given family that'll then join into the same single generic stack again. 

For example a wall-torch and a ground-torch will both be collected to the same stack of torches. However, there is a separate block for the wall torch (in fact, there are 4 of them, one for each rotation) and a separate block for the ground torch. Likewise fence blocks will adjust their shape to connect to neighbors, but all count as a single generic fence block.

A block family for a block is defined in the ```.block``` file via the ```family``` section(see [[Block Definition|Block Definition]]).

When a family is generated from a block, it will create multiple instances for the block, all referenced by different ```BlockUri```.  

You may want to have a look at the documentation of [org.terasology.world.block.BlockUri](https://github.com/MovingBlocks/Terasology/blob/develop/engine/src/main/java/org/terasology/world/block/BlockUri.java).