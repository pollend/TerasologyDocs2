---
id: asset_system_prepare_model_export
title: Latin-ish
sidebar_label: Add A New Creature
---

### See [here](https://github.com/Terasology/TutorialAssetSystem/wiki/Installing-Blender-Add-on) for installing the addon for blender.
## Prerequisites
There are some requirements that the model needs to meet before being compatible with the exported.
* The armature must contain only one root bone.
* The bones should only contain translation and rotation transforms.
## Animation
### Duplicating an animation
> Each scene must have the same name as the action name
1. Select the ![plus](https://user-images.githubusercontent.com/14962635/29281815-1169623e-813e-11e7-93a7-5f6558a1a79c.jpg) icon next to the scene dropdown.  

![top](https://user-images.githubusercontent.com/14962635/29281241-d6cecb84-813b-11e7-897c-f45a2a17c751.jpg)
2. Select "Link Object Data" in the the menu that pops up.  

![link](https://user-images.githubusercontent.com/14962635/29282141-416485c6-813f-11e7-9cd3-cc65ecd2c9d2.jpg)
> This way the new scene will contain reference to the same object and animation data.
3. Select the armature.
4. In an editor open "Dope Sheet" and select "Action Editor" from the list of tools.
![dopesheet](https://user-images.githubusercontent.com/14962635/29282796-c87867b0-8141-11e7-8877-ee2f736208a1.jpg)
5. The current scene will contain the same animation as that of the scene it was duplicated from. Press the ![2](https://user-images.githubusercontent.com/14962635/29282877-184a762a-8142-11e7-95b4-d4723e1dee97.jpg) button in the action menu to create an independent action.
6. **Name of both action and scene name must be same and must start with an upper case letter (Example "Walk", "Run", "Attack").**
7. Edit the new animation that was created. It will automatically be updated in the Exporter Panel.

### See [here](https://github.com/Terasology/TutorialAssetSystem/wiki/Using-the-Blender-Add-on) for using the addon in blender.