To work with modules you need to either fetch existing ones or create new ones. We have utility tasks in Groovy to make this process easier.

Let us use the `Sample` module from https://github.com/Terasology/Sample for the examples below.


## Fetch an existing module

As long as you have [set up the main Terasology workspace](https://github.com/MovingBlocks/Terasology/wiki/Preparing-an-Engine-Workspace), you can fetch existing modules without working directly with Git. Simply execute the following in the root of your workspace:
 
`groovyw module get Sample`

Where `Sample` is the name of the module you want. In the case of the `Sample` module Groovy will fetch the existing GitHub repo from https://github.com/Terasology/Sample and place it in your local workspace where it should go at:

`modules/Sample`

To properly adjust your workspace you need to run Gradle again, usually by regenerating your IntelliJ project files:

`gradlew idea`

After execution finishes IntelliJ should notice (may take a moment or two) and prompt you to restart to pick up changed project files. Do so.

You may notice that additional files and directories were created in the `Sample` directory. This includes the `build.gradle` needed to build the module, along with placeholder dirs for all asset types and such.

A quick side note: Sometimes `gradlew idea` does not add the module for you. To do this, simply press (ModuleName).iml file and "Import (ModuleName) Module" or try again (sometimes the restart doesn't quite do it)

## Create a new module

For new modules there is an additional step or two. Start with a slightly different command:

`groovyw module create MySample`

The will create a module named "MySample" at `modules/MySample`

As with fetching a module be sure to adjust your workspace after your module lineup has changed. `gradlew` is enough if you're working with pure command line, but usually for IntelliJ you again would do:

`gradlew idea`

Then let IntelliJ finish and prompt you to restart to update the project structure.
 
You'll notice the new module directory has been created with some placeholder files. Adjust [[module.txt|Module.txt]] accordingly to describe your module.
 
Connecting your new module to a home on GitHub can be done in one of two ways, either of which needs you to create a new remote reference in the local Git repo.

* You can ask project staff to please create a module repo for you under the [Terasology organization on GitHub](https://github.com/Terasology) and give you access.
* You can create your own module repo on your personal GitHub account

After you have a module repo on Github, `cd` to `modules/MySample` and execute `git remote add origin https://github.com/[username]/MySample`

Where `[username]` is either your account name on GitHub for a personal repo or `Terasology` for official module repos.


## Understanding Terasology's Git setup

Having fetched or created a module you now have *two* Git repos in your local workspace.

* The root Terasology project containing the engine and everything else
* The module with its own nested Git root under `/modules/Sample` or so

This is known as having a nested Git project in your workspace. The nested Git root (the module) is excluded from tracking in the Git repo holding the main Terasology stuff.

All that means is that you treat the two pieces independently when it comes to source control. IntelliJ and other tools can handle this very easily. Here is a diagram to explain:

![One local workspace, two separate repos on GitHub](DevelopingModules.png)

## Structure of modules

Out of date, please feel free to update it:


   * `/assets` - place resources related to the module under here and our [[Asset System]] will find them. You can optionally introduce additional directory levels under each asset type to organize better
      * `/blocks` - block definitions go here, which are simple JSON files holding any special instructions related to each block (or nothing at all). Each block may reference one or more textures for its faces. See [[Block System]] for more details
      * `/blockTiles` - block textures go here and are usually matched by block definition files. However, if you place an `auto` directory under here any images there will automagically become basic blocks (same texture on all sides, no special traits)
      * `/prefabs` - these JSON files describe entity recipes that can be used by the game engine to create objects in-game. This could for instance be a Portal describing what it is able to spawn, or a chest block able to hold items. See [[Entity system concepts]]
      * `/sounds` - another asset type example. You can place an audio file here in the OGG format and then reference it using the mod's namespace, such as `portals:spawn`
   * `/src` - actual source code for custom functionality goes under here. Usually this will be custom Components and Systems that make up the core content in our [[Entity System Architecture]]

## Namespace
The typical namespace for a module is `org.terasology.<nameOfTheModule>`. It is recommended to name the source packages accordingly, otherwise the modules may not be built or loaded as expected.  
_See [#2445](https://github.com/MovingBlocks/Terasology/issues/2445) for more details._

## See also

* [[Module Dependencies]] - how to deal with modules that depend on another
* [[Dealing with Forks]] - work with your own copies of GitHub repos you can write to