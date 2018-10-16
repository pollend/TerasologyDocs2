The engine repository at https://github.com/MovingBlocks/Terasology is the heart and central workspace of mostly everything Terasology.

To set up the workspace is a fairly easy process:

* Git clone or download a source zip from GitHub to some location on your computer 
  * See GitHub or Google for various Git tutorials. In short you'd clone with `git clone https://github.com/MovingBlocks/Terasology.git` into a local workspace directory
* Run `gradlew` once in the root of the chosen directory via command prompt / terminal

That's it, really! You now should have a functioning game workspace.

## Requirements

Okay, you might want a little more than that. The only mandatory requirement is a Java 8 SDK which you either download from Oracle or get via OpenJDK.

* [Oracle Java 8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) - pick the appropriate flavor for your OS
* [OpenJDK](http://openjdk.java.net) - find out how to get the right version for your OS here
  * *Note:* Using OpenJDK has a slightly higher risk for encountering [[Common Issues]] - for instance the [Launcher](https://github.com/MovingBlocks/TerasologyLauncher) requires JavaFX which isn't always bundled with OpenJDK.

Beyond that you might want an IDE and some IDE plugins, see below. Maybe even a tool like [YourKit](https://www.yourkit.com) to help profile game performance. But everything else really is optional!
 
Most our automation and project setup happens through [Gradle](http://gradle.org) which the `gradlew` script downloads a version of if needed. The initial `gradlew` execution will download all project dependencies (Maven style - downloading half the internet). Just give it a while. Read more on [[Codebase Structure]] if interested. 


## Run game from source

As long as you have the code and Java 8 you can run the game from source simply with `gradlew game`. Note that, if when you try to create a world or run a game, you run into missing classes or assets, you may need to employ a workaround by adding the `jar` tasks to the build, e.g., `gradlew jar game`.

Any problem encountered at this point is usually from Java not being configured right, such as having an older version as your default Java. See [[Common Issues]] for more.

If the game itself behaves funny or crashes see if the [normal release download](https://github.com/MovingBlocks/Terasology/releases) works. If not check the [[Minimum Requirements]] and make sure your graphics card driver is up to date.

Ask in the [Support Forum](http://forum.terasology.org/forum/support.20) if issues remain, or come join us on `#terasology` on Freenode IRC. See [[Using IRC]] and please be patient! IRC isn't necessarily instant communication and it may take a while to get a reply.

You can also run a headless server from source using `gradlew server` - just run it in a second command prompt / terminal as it'll not accept further input (other than `CTRL-C` to break the process)


## IntelliJ or other IDEs

Running from command line is good and fine and some enjoy simply working in a plain text editor. For those preferring a full integrated development environment (IDE) we recommend [IntelliJ](https://www.jetbrains.com/idea/download)

We have a series of customizations that prepare run configurations, Git integration, and so on for the project, specifically for IntelliJ. Eclipse has fewer of these but is still entirely usable, as is NetBeans, but you'll need to figure out some details there yourself.

To prepare project files for IntelliJ simply run `gradlew idea` which as any `gradlew` also does the initial dependency fetch so you can go straight from source download to `gradlew idea` you don't need a separate plain `gradlew` step.

Open the resulting `Terasology.ipr` as an existing project in IntelliJ - do *not* create a new project or attempt to import the project via Gradle. It is possible to get that working but it may miss customizations and cause confusion.

The opened project should leave you with a series of run configurations to execute the game (and server) in various formats. It'll hook up our license header as a template, configure code analytics, and so on.

Git will be enabled as source control, however going deeper into the details of using Git is outside the scope of this wiki. Please [see the excellent resources on GitHub for more](https://help.github.com/articles/good-resources-for-learning-git-and-github) like their [bootcamp](https://help.github.com/categories/bootcamp) series.


## See also

* [[Developing Modules]] - if the engine is the heart of Terasology modules make up everything else. Learn about them here.
* [[Module Dependencies]] - modules have a dependency system much like Gradle / Maven. Read about that here. 
* [[Dealing with Forks]] - understand how to fork code repositories on GitHub and interact with several at once.