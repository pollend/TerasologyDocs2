---
id: asset_system_using_blender_addon
title: Latin-ish
sidebar_label: Add A New Creature
---

## Setup
1. Refer to [this](https://github.com/Terasology/TutorialAssetSystem/wiki/Installing-Blender-Add-on) guide on how to install the Blender Add-on.
2. The directory can be selected using the ![directory](https://user-images.githubusercontent.com/14962635/29182627-3c00d802-7e1d-11e7-94c7-e5a0f8590a96.JPG) button. **This directory can be the asset directory of the game where the files can be exported directly. An existing module directory can be selected and the files are exported there.** Click [here](https://github.com/MovingBlocks/Terasology/wiki/Dev-Setup) for a tutorial on how to setup Terasology development environment.
3. The directory can also be selected using the ![module](https://user-images.githubusercontent.com/14962635/29183776-8883c1c2-7e21-11e7-8c9b-4f43fdc7f630.jpg) button to export the module. Further details are provided below.  
4. As an example the [skeleton model](https://github.com/MetaTerasology/GooeysQuests/tree/master/skeleton) can be used to follow along for this tutorial. It contains model, texture and animations for the skeleton.  

> The directory path can be saved by navigating to File->User Preferences->Save User Settings.  

## Exporting Model  
> See [here](https://github.com/Terasology/TutorialAssetSystem/wiki/Preparing-Model-for-Export) for instructions on how to prepare the model before exporting.

1. The model created in Blender can be exported for Terasology in .md5mesh format.
2. The mesh will be exported in the directory specified in a folder called **skeletalMesh**.  

3. Click **Export <modelName>.md5mesh** to export the mesh.  

![export_model](https://user-images.githubusercontent.com/14962635/29182662-5c4b4eb2-7e1d-11e7-8cd3-f2eba5b18322.JPG)

> Make sure the model has UV laid out otherwise the script will throw an error.

## Exporting the Animations

> Make sure all the actions are created under a new scene and the scene has the same name as that of action.  

![action_scene](https://user-images.githubusercontent.com/14962635/29183061-e4d1fb2c-7e1e-11e7-98b8-7d5810558c60.JPG)
***
1. Animations are exported in a **.md5anim** format.
1. List of animations to be exported can be selected in the UI. The animations that are selected will be exported to a folder called **animations** inside the directory that is selected.
2. After selecting the animations click the **Export Selected Animations** button to export the animations to the directory.  

![animationexport](https://user-images.githubusercontent.com/14962635/29183204-6a9aab50-7e1f-11e7-8c24-5afc1f314f68.JPG)

## Exporting Prefab  

Prefab contains a basic definition for the model that can be spawned using the `spawnPrefab` command.
The structure of prefab looks like this:
```
{
  "skeletalmesh" : {
    "mesh" : "",
    "heightOffset" : -0.8,
    "material" : "",
    "animation" : "",
    "loop" : true
  },
  "Behavior" : {
    "tree" : "stray"
  },
  "FleeOnHit" : {
    "minDistance" : 5,
    "speedMultiplier" : 1.2
  },
  "StrayIfIdle" : {
    "defaultSpeedMultiplier" : 0.3
  },
  "BlockDropGrammar": {
    "blockDrops": [],
    "itemDrops": ["2*WildAnimals:meat"]
  },
  "Stand" :{
    "animationPool": []
  },
  "Walk" :{
    "animationPool": []
  },
  "Die" :{
    "animationPool": []
  },
  "persisted" : true,
  "location" : {},
  "Character" : {},
  "AliveCharacter": {},
  "WildAnimal" : {
    "name": "",
    "icon": ""
  },
  "NPCMovement" : {},
  "CreatureNameGenerator" : {
    "genderRatio" : 0.5,
    "nobility" : 0.5,
    "theme": "DWARF"
  },
  "CharacterMovement" : {
    "groundFriction" : 16,
    "speedMultiplier" : 0.3,
    "distanceBetweenFootsteps" : 0.2,
    "distanceBetweenSwimStrokes" : 2.5,
    "height" : 1.6,
    "radius" : 0.3,
    "jumpSpeed" : 12
  },
  "CharacterSound" : {
    "footstepSounds" : ["FootGrass1", "FootGrass2", "FootGrass3", "FootGrass4", "FootGrass5"],
    "footstepVolume" : 0.03
  },
  "Network" :{},
  "MinionMove" : {},
  "Health" : {
    "destroyEntityOnNoHealth" : true,
    "currentHealth": 7
  },
  "BoxShape" : {
    "extents" : [1.5, 1.5, 1.5]
  },
  "Trigger" : {
    "detectGroups" : ["engine:debris", "engine:sensor"]
  }
}
```
* `skeletalmesh->mesh` defines the name of the mesh that is to be used (Example for a model name `deer` the mesh field should be `deer`)
* `skeletalmesh->material` contains the name of the material file (*.mat*) which will be used for the mesh. Further details about the material file are given [below](https://github.com/Terasology/TutorialAssetSystem/wiki/Using-the-Blender-Add-on/#exporting-material-file).
* Fields like `Stand`, `Walk`, `Die` contains the list of animations out of which one is played at random. These fields are filled according to the naming convention of the animations. Further modifications can be done by the user.

The prefab is exported inside a folder called **prefabs** in the directory that is selected.
The prefab is created from a template file. Actions present in the blender file are added to the prefab file according to their name.
* Action name containing **stand** or **idle** in their name are put under the **Stand** "animation Pool".
* Action name containing **walk** in their name are put under **Walk** "animation Pool".
* Action name containing **die** in their name are put under **Die** "animation Pool".
* All other actions are put under **Stand** "animation Pool".

## Exporting Texture  

> The texture must be present in the directory of the folder of **.blend** file. named **modelNameTexture.png**.

The texture is exported inside a folder called **textures** in the directory that is selected.

## Exporting Material file

The material file contains details about the texture that the model needs to use. 
Its structure looks something like this: 
```
{
    "shader" : "engine:genericMeshMaterial",
    "params" : {
        "diffuse" : "deer",
        "colorOffset" : [1.0, 1.0, 1.0],
        "textured" : true
    }
}
```
* The `params->diffuse` field contains the texture file name that needs to be used. 

## Exporting Module inside a folder

The entire module can be exported using the ![module](https://user-images.githubusercontent.com/14962635/29183776-8883c1c2-7e21-11e7-8c9b-4f43fdc7f630.jpg) button in the Panel.  
After the export the default directory path becomes the one where the module was exported. This facilitates in exporting modified content for the same module.

![moduleexport](https://user-images.githubusercontent.com/14962635/29184031-77c2e934-7e22-11e7-993c-c7915f330bc1.JPG)

## Exporting Module (.jar) for use in Terasology  

1. Navigate to File->Export->**Export zip for Terasology**.
2. Select the directory to export and click **Export Zip**.  

![exportjar](https://user-images.githubusercontent.com/14962635/29184814-24e61bca-7e25-11e7-95d4-f7dca0331e41.jpg)
The file exported is a ready to use module file. It can be copied into the modules folder(or better created there) and can be activated in game.
> The command **spawnPrefab modelName** can be used to spawn an entity.

## Spawning the model in game
> The .jar file (module) must be moved to the `modules` directory.

[Here](https://github.com/MovingBlocks/Terasology/wiki/Dev-Setup) is how to setup terasology.  

The model can be spawned in game using the `spawnPrefab` command.
1. Create a new game.
2. Enable the newly created module in the module selection screen.
3. Press *`* in game to open up the console.
4. Type `spawnPrefab ` followed by the file name of the model. For example if the the model name is "deer.blend" the command would be `spawnPrefab deer`. This will spawn a deer which the definitions from the prefab file. The prefab file can be edited as mentioned above for various customization.