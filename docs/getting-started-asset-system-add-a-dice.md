---
id: getting-started-asset-system-add-a-dice
title: Latin-ish
sidebar_label: Add A Dice
---

Static blocks are cool but how about a block which provides some interactivity?

Lets add a dice block with the following requirements:
* 6 different sides (surprise surprise, it is a dice ;) )
* The block should be interactable ('e' key by default)
* If activated, the dice should rotate randomly and stop in a different state
* When rolled, the dice should play a little sound
* And of course we want dices in different colors ;)

We will start with a simple dice, without any interaction first:

1. Add the ```dice1.png``` to ```dice6.png```  textures to the ```assets/blockTiles``` folder:  
    [[images/dice1.png]] [[images/dice2.png]] [[images/dice3.png]] [[images/dice4.png]] [[images/dice5.png]] [[images/dice6.png]]

2.  Create the block definition at ```blocks/dice.block```:
    ```
    {
        "displayName": "Dice 6",
        "categories" : ["dice"],
        "hardness": 1,
        "tiles" : {
            "top" : "dice1",
            "bottom" : "dice6",
            "front" : "dice2",
            "back" : "dice5",
            "left" : "dice3",
            "right" : "dice4"
        }
    }
    ```

    With a short check ingame, we can continue:  

    [[images/screen3.png]]

3. Now comes the tricky part:  
We need all possible rotations for this dice and defining them all as individual blocks would be a total mess ;) And that is the part, where [[Block Families|Block Families]] come into play. There is only one problem: At the state of this tutorial, there are only the ```horizontal``` and the ```attachedToSurface``` families predefined.  
The first one will rotate a block but keeps top and bottom unchanged which is great for blocks like chests or a furnance but not what we want for our dice.  
The second one allows the definition of 3 block instances via shapes, one for the floor, one for the walls (will be rotated to face each wall) and one for the ceiling. This is great for items like the torch but not what we want for our dice.  

    For this reason, the tutorial comes with the ```RotateableBlockFamily``` which can be defined by setting ```"rotation" : "all"``` in the ```.block```-file. If you are not interested how exactly the Family works, you can continue here.  
In case you want some additional information about how to implement your own block family, you may read the full documentation of the [RotateableBlockFamily](https://github.com/Terasology/TutorialAssetSystem/blob/master/src/main/java/org/terasology/tutorial/assetsystem/block/family/RotatableBlockFamily.java).

    Last but not least, we need a component on our block which will be a marker annotation for us, that the block is rotateable like a dice. We add a prefab (we will define it in the next step) to the block definition, using the ```entity``` section.  
    The final ```dice.block``` should look like this:
    ```
    {
        "displayName": "Dice 6",
        "categories" : ["dice"],
        "hardness": 1,
        "tiles" : {
            "top" : "dice1",
            "bottom" : "dice6",
            "front" : "dice2",
            "back" : "dice5",
            "left" : "dice3",
            "right" : "dice4"
        },
        "rotation" : "all",
        "entity" : {
            "prefab" : "dice"
        }
    }
    ```
4. As said, we need a prefab for the dice. Define ```assets/prefabs/dice.prefab``` like:
    ```
    {
        "RotateBlockOnActivate" : {},
        "PlaySoundAction": {
            "sounds": "rollDice"
        }
    }
    ```
    The ```PlaySoundActionComponent``` is defined in the engine and plays a sound on activation. Just drop the [rollDice.ogg](https://raw.githubusercontent.com/Terasology/TutorialAssetSystem/master/assets/sounds/rollDice.ogg) to ```assets/sounds/rollDice.ogg``` and be fine.   
    The ```RotateBlockOnActivateComponent``` does not exist yet. We can define it like this:
    ```java
    package org.terasology.tutorial.assetsystem.components;

    import org.terasology.entitySystem.Component;

    /**
     * Marker component for a block which will be rotated if activated
     */
    public class RotateBlockOnActivateComponent implements Component {
    
    }
    ```
    _Note that the concept of components and entity-systems is beyond the scope of this tutorial._
    _You can check issue [#2153](https://github.com/MovingBlocks/Terasology/issues/2153) and if it should be fixed or any tutorial is linked there, please update this section with a link ;)_

5. Everything is in place now. The dice knows it can be rotated and we have all rotated instances of the dice ready.
    Last step is the definition of a ComponentSystem which rotates our block. It can be defined as following:
    ```java
    package org.terasology.tutorial.assetsystem.systems;
    
    import java.util.List;
    
    import org.slf4j.Logger;
    import org.slf4j.LoggerFactory;
    import org.terasology.entitySystem.entity.EntityRef;
    import org.terasology.entitySystem.event.ReceiveEvent;
    import org.terasology.entitySystem.systems.BaseComponentSystem;
    import org.terasology.entitySystem.systems.RegisterMode;
    import org.terasology.entitySystem.systems.RegisterSystem;
    import org.terasology.logic.common.ActivateEvent;
    import org.terasology.math.Side;
    import org.terasology.registry.In;
    import org.terasology.tutorial.assetsystem.components.RotateBlockOnActivateComponent;
    import org.terasology.utilities.random.FastRandom;
    import org.terasology.utilities.random.Random;
    import org.terasology.world.WorldProvider;
    import org.terasology.world.block.Block;
    import org.terasology.world.block.BlockComponent;
    
    import com.google.common.collect.Lists;
    
    @RegisterSystem(RegisterMode.AUTHORITY)
    public class RotateBlockOnActivationSystem extends BaseComponentSystem {
    
        @In
        private WorldProvider worldProvider;
    
        private Random random = new FastRandom();
    
        private static final Logger LOG = LoggerFactory.getLogger(RotateBlockOnActivationSystem.class);
    
        @ReceiveEvent(components = {RotateBlockOnActivateComponent.class, BlockComponent.class})
        public void onActivate(ActivateEvent event, EntityRef entity) {
            BlockComponent blockComponent = entity.getComponent(BlockComponent.class);
            Block block = blockComponent.getBlock();
            List<Block> blocks = Lists.newArrayList(block.getBlockFamily().getBlocks());
            //-1 because we omit the block with the same rotation as the current one
            int index = random.nextInt(blocks.size() - 1);
            Side currentDirection = block.getDirection();
            for (int i = 0; i < blocks.size(); i++) {
                Block newBlock = blocks.get(i);
                if (newBlock.getDirection() != currentDirection) {
                    index--;
                }
                if (index == 0) {
                    LOG.info(newBlock.getURI().toString());
                    worldProvider.setBlock(blockComponent.getPosition(), newBlock);
                }
            }
        }
    }
    ```
    - we receive only events for blocks with our marker component
    - we randomly select another instance from the same block family
    - the current block is replaced with the instance

Time to place a dice ingame and activate it some times ;)

[[images/dice.gif]]