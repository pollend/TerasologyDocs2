# Setup
###<b>Step 1: Download or clone the repo</b>
<a href="https://github.com/MovingBlocks/Terasology">Click here to go to the repo</a>
###<b>Step 2: Import existing modules you want to build off of, or create your own.</b>
Before we continue, make sure you open command prompt, so you can enter some commands in.<br/>
<b>_(tip: you can hold shift and right click where the repo is saved, and left click open command prompt here, it will automatically open command prompt on that directory)_</b><br/>
if you didn't navigate to the directory already, then just type<br/>
`cd "THE REPO DIRECTORY"`<br/>
example:<br/>
`cd "C:\Repositories\TerasologyRepo"`

<b>To import a module, use</b><br/>
`gradlew fetchModule[MODULENAME]`

Here are some examples:<br/>
`gradlew fetchModuleSample`<br/>
`gradlew fetchModuleNguiExample`<br/>
`gradlew fetchModuleQuest`<br/>

<b>To create your own module:</b><br/>
type the command<br/>
`gradlew createModule[MODULENAME]`

example:<br/>
`gradlew createModuleMyFirstModule`<br/>
this will create the module, and name it "MyFirstModule"

###<b>Step 3: Build your workspace for your preferred IDE
<b>Eclipse:</b><br/>
`gradlew eclipse`<br/>
<b>Intellij</b><br/>
`gradlew idea`<br/>

If you import any modules in the future, make sure to call this command again, to re-build the project files to be able to import it into your workspace

###<b>Step 4: Import your project to your workspace</b>
<b>Eclipse</b><br/>
First, rightclick your package explorer, and leftclick on "Import Package"<br/>
![](http://image.prntscr.com/image/0977ec9b76ec40a2a18a6c711e1e5c22.png)

Second, expand "General" and leftclick "Existing projects into workspace"<br/>
![](http://image.prntscr.com/image/2d83d7481c1b405a91cf8e88ff12a974.png)

Finally, import the repository path. Just copy the repository directory, and paste it into the "Select root directory" text area<br/>
![](http://image.prntscr.com/image/2fa0e833d7ed466494261d44aa8717a0.png)


And done! now you can start making your mod!
