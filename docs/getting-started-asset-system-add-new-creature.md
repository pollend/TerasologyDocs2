---
id: asset_system_new_creature
title: Latin-ish
sidebar_label: Add A New Creature
---

## Create Model
To add a creature in the game, you'd first need to model it in Blender. There is a collection of creature models present [here](https://github.com/MetaTerasology/WildAnimals/) that are not yet exported to the game.

## Set Up the Exporter
Use glasz's exporter to export the .blend file as md5 (mesh and animation).

1. Save/Download the exporter script from [here](https://raw.githubusercontent.com/MovingBlocks/TeraMisc/master/blender_addons/io_md5_exporter/io_export_md5.py).
2. Open Blender. Go to: File -> User Preferences (Ctrl + Alt + U). Switch to the 'Addons' tab. At the bottom of the screen (see screenshot below), click on 'Install from File...'. Browse and select the downloaded script (io_export_md5.py).

![Preferences](http://blobisme.free.fr/blendert2md5/01.png)

3. The new add-on should be present in the list, named "Import-Export: MD5 exporter for Terasology (.md5)". This can be found by using the filter "User" or "Import-Export" from the categories on the left (see below). Once found, check the checkbox for the item.

![Enable Script](https://ibin.co/3FrDoBxWt8ox.png)

4. Click on "Save User Settings" on the bottom and voila! You have the script enabled. You can check for this by going to File->Export and finding a new option that allows you to export to md5, as shown.

![export](https://ibin.co/3FrErRgG3gpr.png)

## Export .blend to .md5mesh and .md5anim
The following steps are condensed from [glasz's tutorial](http://forum.terasology.org/threads/blender-to-md5-howto.1020).
md5 is only for rigged models; you will need a mesh attached to a skeleton. For a static mesh to be used as voxels, you should use the specific Terasology blender exporter.

### Root Bone
One last thing that is not relevant to md5-export, but useful to know: skeletons should always have a root bone, with coordinates (0, 0, 0), that is a parent to all other bones and remains still at (0, 0, 0) regardless of the animation activity. This bone will be used in code for the actual positioning of the animated model. From my testing, it can be added at the end if it was omitted, but it's better to keep this in mind from the start.

### Triangulate Faces
So, there is one important step to have the exporter work, which is to triangulate all faces of the mesh. By default, blender mesh creates quads, so they have to be broken into triangles. Go into edit mode, select all faces (with 'a' or 'a'-'a') and Mesh->Faces->Triangulate faces.

![Triangulate faces](http://blobisme.free.fr/blendert2md5/03.png)

### Remove Non-skeleton Vertex Groups
This next step might be optional: remove all vertex groups that don't belong to a skeleton bone. Vertex groups are useful for mesh editing, but they are also used for attaching part of the mesh to a specific bone. You can do this manually by assigning a number of vertices to a vertex group with the same name as a skeleton bone, which will attach the vertices to that bone. This is also done automatically when you use weight painting. In both cases, having vertex groups other than the ones used by the bones will mess up the export.

In this case, pompom is not used by a bone and must be deleted:

![bone](http://blobisme.free.fr/blendert2md5/05.png)

Some other common errors are: **armature not attached**, **no UV Layer**, **extra vertex groups** etc. More discussion can be found on the [forum thread](http://forum.terasology.org/threads/blender-to-md5-howto.1020/).

### Scale and Export
Once all this is done, go to File->Export->md5 export. You'd find an option here at the bottom left to scale the creature. Scale the creature according to how you want it to appear in the Terasology world (In Terasology, 1 unit = 1 meter). 

![scale](http://blobisme.free.fr/blendert2md5/06.png)

Click on "MD5 Export". If this completes successfully and resulted in a .md5mesh and .md5anim file, move on. Otherwise, there will be an error message, meaning that there was a problem with the model or the exporter. Reach out to [glasz](http://forum.terasology.org/members/glasz.66/) for some help, if you can't figure this out.

## Add to Game
Addition to the game is fairly straightforward once you have the two md5 files.

### Run from Source
If you aren't running from source yet, follow the [Dev-Setup guide](https://github.com/MovingBlocks/Terasology/wiki/Dev-Setup) to fork and run from source. 
 
### Get the WildAnimals module
Open terminal/cmd and do a `./gradlew fetchModule WildAnimals`/`gradlew fetchModule WildAnimals` from the working directory. This will clone the WildAnimals repo into your /modules/ directory. Do a `./gradlew idea` to update your ipr file if you're using IntelliJ.  

### Duplicate Deer Files
For this example let us assume you're trying to import a bird.  
  1. Goto `/modules/WildAnimals/assets/animations` and paste the generated `bird.md5anim` file.
  2. Goto `/modules/WildAnimals/assets/skeletalMesh` and paste the generated `bird.md5mesh` file.
  3. Goto `/modules/WildAnimals/assets/materials` and duplicate `deerSkin.mat` and rename it to `birdSkin.mat`. Change `"diffuse" : "deer"` to `"diffuse" : "bird"`, to get
```
{
    "shader" : "engine:genericMeshMaterial",
    "params" : {
        "diffuse" : "bird",
        "colorOffset" : [1.0, 1.0, 1.0],
        "textured" : true
    }
}

```
  4. Go to `/modules/WildAnimals/assets/prefabs` and duplicate 'deer.prefab' and rename it to 'bird.prefab'. Find-Replace `deer` with `bird` to create a file that looks like this: 

```
{
    "skeletalmesh" : {
        "mesh" : "bird",
        "heightOffset" : -0.8,
        "material" : "birdSkin",
        "animation" : "bird",
        "loop" : true
    },
    "Behavior" : {
        "tree" : "stray"
    },
    "Stand" :{
        "animationPool": [
            "bird"
            ]
    },
    "Walk" :{
        "animationPool": ["bird"]
    },
    "persisted" : true,
    "location" : {},
    "Character": {},
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
        "destroyEntityOnNoHealth" : true
    },
    "BoxShape" : {
        "extents" : [1.5, 1.5, 1.5]
    },
    "Trigger" : {
        "detectGroups" : ["engine:debris", "engine:sensor"]
    }
}
```
  5. Go to `/modules/WildAnimals/assets/textures` and duplicate 'deer.png' and rename it to 'bird.png'. 

## Run Game
Once you're done with all of this, it's time to test the creatures in-game. Run the game, create a new world, enable the WildAnimals module and start.
Open the console (~) and type `spawnPrefab bird`. A bird should spawn right in front of you.

Maybe create your very own ecosystem: 

![animals](https://ibin.co/3FrSRUuPCg9V.jpg)

Have fun!