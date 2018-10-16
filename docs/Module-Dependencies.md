Modules can depend on other modules, just like Java libraries and projects can have dependencies, usually configured via Gradle or Maven.

For Terasology we've developed a module system later extracted into its [own library "Gestalt Module"](https://github.com/MovingBlocks/gestalt) that our engine project then itself depends on.


## module.txt

Rather than a `pom.xml` or Gradle build file our modules use a simple `module.txt` file to hold all configuration for the module including its dependencies.

For examples simply look at any module in our [module-holding Terasology organization on GitHub](https://github.com/Terasology)

For more details of how it works you can check out the [Gestalt wiki](https://github.com/MovingBlocks/gestalt/wiki)


## Resolving dependencies

You may end up fetching or creating a module that depends on other modules. Again our Gradle setup makes this super easy to handle!

If you fetch a module `X` that has a dependency on module `Y` the next execution of any `gradlew` command will automatically fetch a binary copy of module `Y` including in turn any of *its* dependencies (a "transitive" dependency).

Any binary module dependency will be stored both in your local Gradle cache as well as in `/modules` where the game will use it from at runtime.

If you later fetch the source code for module `Y` it will automatically take precedence over any old binary copy of `Y`
 
You can delete any binary copies of modules at any time then rerun `gradlew` to have them re-fetched.


## Using dependencies

To declare a dependency of your own simply name the module you need in `module.txt` and rerun something like `gradlew idea` - Gradle will handle the rest!

You can include version requirements. Usually this is just whatever is the latest at the time you declare the dependency. See [[Versioning]] to understand that piece better.

Declaring an *optional* dependency isn't formally supported yet but in `.prefab` files you can place a Component from a class that's found in a module *not* listed as a dependency, and it'll be ignored gracefully.

For example the `player.prefab` as of this writing has a `"Breather": {},` meaning the player is a "breather" and needs air to survive, but if the Breathing module is not enabled it has no effect and nothing crashes!