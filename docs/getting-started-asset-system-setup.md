---
id: getting-started-asset-system-setup
title: Latin-ish
sidebar_label: Add A New Creature
---

Lets create a new module to get started. For your own experiments you can select a different name.
Launch the following command on the Terasology project:
```
gradlew createModuleTutorialAssetSystem
```
(Note: the `gradlew createModule...` and similar tasks are deprecated and will be removed in the v2 engine release - new `groovyw module create [name]` and similar variants are available)

This will create a new module ```TutorialAssetSystem``` in the ```Terasology/modules``` directory.
For Eclipse now run
```
gradlew eclipse
```
to generate the required project files.

Now from the eclipse workspace, select ```File -> Import -> Existing Projects into Workspace```. Select the Terasology directory as root directory and make sure the checkbox ```Search for nested projects``` is checked (good practice to import multiple modules anyway). Select the created module and import it.
The module should appear as new project in the workspace.

For IntelliJ IDEA run
```
gradlew idea
```
to generate the required project files for IntelliJ IDEA IDE.

Now you can open the project directly from the project file generated Terasology.ipr or by opening the project from Idea IDE.


Creating a new module will also create a new git repository inside the module folder. Eclipse will not find the repository if you import the project as described above.
In case you need the Eclipse git support (e.g. to make your commits)  you can switch to the git perspective, add the folder ```modules/TutorialAssetSystem``` as new git repository and import the project from this repository afterwards.

You are now ready for the next step: [[Add New Block|Add New Block]]