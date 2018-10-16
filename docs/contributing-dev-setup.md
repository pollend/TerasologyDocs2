To get started with coding for Terasology just have a Java 8 SDK handy, and ideally IntelliJ.
 
 
## Quick start

* Fork https://github.com/MovingBlocks/Terasology and clone your fork to a local workspace
* If you want to work on any modules fetch them using `gradlew fetchModuleName` with `Name` being the module, or create one with `gradlew createModuleName`
  * For instance you can run `gradlew fetchModulePortals fetchModuleSpawning fetchModuleOreons` to get all three in one go
* Run `gradlew idea` and load the resulting project into IntelliJ (don't import via Gradle!)
* Code code code, test locally.
* Push to your fork for engine changes, create module forks or ask for write permissions and push module changes there
* Make PRs, get them merged, revel in open source geek Nirvana!
  * To find some issues to work on, check out the [Bite-size](https://github.com/MovingBlocks/Terasology/labels/Good%20First%20Issue) (a few hours of work, fairly easy to do) and [Mentor-size](https://github.com/MovingBlocks/Terasology/labels/Mentor-size) (doable in a week or two with advice and assistance from a casual mentor) issue lists.
* Come [introduce yourself in the forum](http://forum.terasology.org/forum/contributor-introductions.7) and let us know what you'd like to do!


## Going deeper

You can read through the intro topics for more details on exactly how to set up and develop.

* [Learn stuff about Git](http://learngitbranching.js.org) - there are plenty of Git Tutorials out there. This is one of the good ones
* [[Preparing an Engine Workspace]] - shows you how to grab the base source code needed to run the game and see it work in IntelliJ
* [[Developing Modules]] - shows you how to interact with and organize modules that hold most the content for the game
* [[Dealing with Forks]] - gives you a quick overview of how to interact with multiple repositories on GitHub and submitting Pull Requests (PRs)
* [[Module Dependencies]] - explains how you can have module `X` depend on module `Y` even at a specific version level

Also check out the general [contributing guidelines](https://github.com/MovingBlocks/Terasology/blob/develop/.github/CONTRIBUTING.md)


## A bit more Gradle

* Generate project files for Eclipse: `gradlew eclipse`
* Run the game from command line: `gradlew game`
* Start a headless server: `gradlew server` (stores data in `/terasology-server` by default)
* For even more: `gradlew tasks`