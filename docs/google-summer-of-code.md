# Google Summer of Code

We have participated in [GSOC](https://summerofcode.withgoogle.com) before, and hope to do so again. This page serves the related information and some suggested ideas for proposals! 

The items listed here are drawn from our [issue tracker's GSOC category](https://github.com/MovingBlocks/Terasology/labels/GSOC), suggesting tasks suitable to be worked by a student over a summer.

More conceptual work is likely needed for most items and there may be existing contributors familiar with and able to help guide a student, beyond any mentors made available for GSOC normally. Other proposals are of course also welcome *but* they need extra justification to be considered :-)

Difficulties and contacts are best estimates - please see the "How to get involved" section below. 

This page is likely to get updates and new entries repeatedly during the warmup period before GSOC formally starts, then go somewhat dormant during the off-season.

For more GSOC specific details see its site at https://summerofcode.withgoogle.com

# Contents

* [What is Terasology](GSOC#what-is-terasology)
* [Overall Requirements](GSOC#overall-requirements)
* [How to get involved](GSOC#how-to-get-involved)
* [Project Ideas](GSOC#project-ideas)
    * [New or expanded gameplay template](GSOC#new-or-expanded-gameplay-template)
    * [Renderer Visual Debugging System](GSOC#renderer-visual-debugging-system)
    * [API for Integration Tests](GSOC#api-for-integration-tests-headless-client)
    * [Crash/Issue reporting improvements](GSOC#crashissue-reporting-improvements)
    * [Deep into Shaderland](GSOC#deep-into-shaderland)
    * [Light & Shadow](GSOC#light--shadow)
    * [Player avatar selection](GSOC#player-avatar-selection)
    * [Customizable characters](GSOC#customizable-characters)
    * [Renovation for MasterOfOreon](GSOC#renovation-for-masteroforeon)
    * [GPU-based Occlusion Queries](GSOC#gpu-based-occlusion-queries-to-load-medium-distance-chunks-only-if-they-are-visible)
    * [Image based selection preview](GSOC#game--saved-world--module-preview-image-content)
    * [Noise-based generation](GSOC#noise-based-generation-of-distinguishable-terrain-features)
    * [Leap Motion implementation](GSOC#leap-motion-implementation)
    * [Mobile server management utility](GSOC#mobile-server-management-utility)
    * [Rendering for far distances](GSOC#new-rendering-approach-for-very-far-distances)
    * [Port organic growth simulator ](GSOC#port-advanced-organic-growth-simulator-from-python)
    * [Dynamic plate geology](GSOC#advanced-and-dynamic-geology-based-on-plate-tectonics)
    * [Destination Sol to ECS](GSOC#porting-destination-sol-over-to-ecs)
    * [Module Showcase Site](GSOC#module-showcase-site)
    * [Genome Integrations](GSOC#genome-integrations)

# What is Terasology

In short [Terasology's](http://terasology.org) goal is to make a heavily extensible voxel world game where actual gameplay can be defined in batches of modules. The engine is minimal, primarily serving to support modules of different kinds. Even systems that seem central to games in general, like a first person player, inventory, combat, and so on is here provided in modules instead and everything can be replaced with a customized version or disabled if not needed.

We plan to make a few typical game types available, like a content creation sand box mode, a twisted Alice in Wonderland style base warfare mode, a more difficult "start from scratch" world with a realistic tech tree to claw your way up while surviving, and so on.

Inspiration is obviously sourced from [Minecraft](https://minecraft.net), as well as other classics like [Dwarf Fortress](http://www.bay12games.com/dwarves) and [Dungeon Keeper](https://en.wikipedia.org/wiki/Dungeon_Keeper). One heavy focus is making sure the world contains more realistic creatures that'll interact with the player in a number of different ways as well as develop their own societies.

# Overall Requirements

As an incoming student you should meet these general requirements:

* Intermediate level Java skills (for most projects. Exceptions do exist)
* Knowledge of version control, preferably Git (the project is hosted on GitHub)
* Experience with an IDE such as IntelliJ or Eclipse would be helpful
* A good attitude and willingness to learn!

More specific requirements (if any) can be found listed with corresponding proposals.

To earn some bonus points familiarize yourself with the [[Codebase Structure]] and the [concepts of our entity system](Entity-System-Concepts). Get an [overview of the project](Project-Overview) and [get set up](https://github.com/MovingBlocks/Terasology/wiki/Dev-Setup)!

# How to get involved

The sooner you contact us the better! As mentioned above, [set up your environment](Dev-Setup), browse through our primary [Issue Tracker](https://github.com/MovingBlocks/Terasology/issues) and get your hands on some minor fixes or a simple module.

For a bunch of sample small tasks you could also see [our tasks completed entry for Google Code-In 2016](https://codein.withgoogle.com/tasks/?sp-organization=5452182442737664) - several of them are still repeatable and all of them were doable since they got done! :-)

If you have any questions don't hesitate to enter #terasology on [Freenode IRC](https://webchat.freenode.net), join us on [Discord](https://discord.gg/4uKbB8J) or post a thread in our [dev portal forum](http://forum.terasology.org/forum/developer-portal.5).

Here is a more step-by-step guide:

* Check our [main site](http://forum.terasology.org), look at the source code and read the available guidelines
* Pick an idea that you think is interesting from the ideas list below or come up with your own idea
* Get familiar with what exactly GSOC is! We can provide you with some information to get started, and most of the time give you some feedback, but its still *you* working out an idea
* Post an introduction of yourself in our [intro forum](http://forum.terasology.org/forum/contributor-introductions.7) and of what your interests are, including what you might like to do for GSOC
* After we get to know each other a bit and you've picked an item then write a draft proposal, posting updates for instance in your intro thread
* The contact people listed below aren't necessarily going to mentor - although some will - but they have been involved with each idea or its general area. After acceptance and discussion we will identify the best available mentor for chosen tasks. By keeping the discussion open we might even find that the best mentor isn't even listed yet :-)

# Project Ideas


## New or expanded gameplay template

* Difficulty: Varies
* Contacts: [jellysnake](http://forum.terasology.org/members/jellysnake.1938/), [vampcat](http://forum.terasology.org/members/vampcat.2080), [msteiger](http://forum.terasology.org/members/msteiger.1197), [Nihal](https://forum.terasology.org/members/nihal-singh.1869/). [Josharias](http://forum.terasology.org/members/josharias.1201), [skaldarnar](http://forum.terasology.org/members/skaldarnar.270), [iojw](http://forum.terasology.org/members/isaac.1943), [mandarj](https://forum.terasology.org/members/mandarj.1964/)
* Helpful skills: Knowledge of game design and a vivid imagination.

One of the great advantages of Terasology is that it provides a very basic and empty engine when no modules are included. Whilst most people associate voxel games with sandbox games and similar, we want to produce a wide variety of gameplay templates and sub games that use Terasology.

A proposal written for this idea should emphasize reuse of existing modules and content and _de-emphasize_ adding large amounts of your own artwork or lore as those don't count for GSOC (summer of **code** after all). You could aim to use existing content as placeholders or make basic new assets while contacting existing community members and artists to help provide those pieces as optional extras.

While you very likely might end up creating one or more new modules as part of this project it is fine to aim to improve existing ones. The main focus is on content rather than on new reusable frameworks, and the goal is to have a playable end product even if parts remain of placeholder nature. This is very similar to the Exploration World idea which was a project during GSOC 2017, which can be seen as a Sandbox specific case of this idea.

### Example ideas

While you could propose a completely new and previously not thought of concept if you have the imagination to think it up and the design skills to convince us you can scope it to fit into a summer it is fine to use existing or expanding on past efforts. Here are some specific ideas:

* Expand on Lost (the Exploration World from GSOC 2017)
* Expand on the GooeysQuests dungeon crawler system (make dungeons more varied, deeper, better, more meaningful rewards)
* A Slime Rancher type game based on our Gooey, see [design write-up](https://forum.terasology.org/threads/gookeeper-game-concept.2099) - this could mix in some elements from the Genome suggestion
* A tower defense type game (could mix in Light & Shadow or similar)
* A better biome based world with greater variety than our current basics, with more meaningful differences, like survival factors to consider, unique flora and fauna, and/or a progression based equipment/supply tree to climb as you explore the world ("need x from biome y to survive in biome z")
* An initial implementation of Metal Renegades, with a [design write-up in the forum](https://forum.terasology.org/threads/metal-renegades-wild-west-meets-robots.1079/)

**Note:** This is a fairly approachable item, yet it may be more difficult to stand out with a proposal if multiple other students also approach this topic. It is also likely to be tricky to scope correctly to fit within a summer of effort. Please do read on and see if you find a more unique item a better fit for you personally! :-)

## Renderer Visual Debugging System

* https://github.com/MovingBlocks/Terasology/issues/2795
* Difficulty: Moderate to High
* Contacts: [manu3d](http://forum.terasology.org/members/manu3d.1256)
* Helpful skills: OpenGL, LWJGL

Terasology uses a deferred renderer: every frame it renders a number of separate layers (stored in FBO attachments) which are combined to produce the image seen on the display. Existing bugs or newly introduced bugs affecting the rendered will tend to negatively affect its visual output. 

An important aspect of debugging these issues is to isolate and identify the rendering node that introduces the problem. Currently, we have a visual debugging system in place, displaying the content of a user-specified FBO when enabled. The current system has a number of shortcomings however. 

First of all, it is hardcoded and does not take advantage of the new, node-based, extensible architecture of the renderer. Second, a number of nodes may write to the same FBO but the current system visualizes the content of the FBO only at the end of the frame: ideally we'd want to be able to inspect the contribution of each node to that FBO separately. Third, the current system visualizes the color attachments of the various FBOs but does not allow inspection of other important attachments, for example depth and stencil buffers. Finally the current system displays the content of an attachment and only that: there is no label allowing the user to uniquely identify the visualized attachment nor additional metadata such as attachment type, size in pixels, size in memory and other useful information.

If you are interested in this particular problem, please engage in a discussion in the space provided by [issue 2795](https://github.com/MovingBlocks/Terasology/issues/2795).

## API for Integration Tests (Headless Client?)

* Difficulty: Moderate to High
* https://github.com/MovingBlocks/Terasology/issues/2780
* Contacts: [oniatus](http://forum.terasology.org/members/oniatus.1641), [Cervator](http://forum.terasology.org/members/cervator.2)
* Helpful skills: Unit testing, test driven development, automated acceptance testing, QA, any other testing topic. Automated (game) environment setup. 

As of the start of 2017 Terasology has several hundred unit tests and a barely implemented code coverage (25% woo!) setup in our build scripting / Jenkins. We can do better!

But to move beyond very basic unit testing we need to improve our testing toolchain, both including more external tools (automated acceptance testing!) and better engine support for partial game environment launching for faster integration tests.

There is a forum thread linked from the issue that covers a wealth of possibilities, but one good initial goal would be for a more complete way to launch the game client, but in a headless fashion, to simply exercise a set script of actions, asserting that all went as expected.

This could relate to a few other items like a RESTful API server (which could communicate with the game server via a headless client)

## Crash/Issue reporting improvements

* Difficulty: Moderate
* https://github.com/MovingBlocks/Terasology/issues/2765
* Contacts: [msteiger](http://forum.terasology.org/members/msteiger.1197), [skaldarnar](http://forum.terasology.org/members/skaldarnar.270), [Cervator](http://forum.terasology.org/members/cervator.2), [rzats](http://forum.terasology.org/members/rostyslav-zatserkovnyi.1659)
* Helpful skills: User interface design, user experience (UX), library design, issue reporting, troubleshooting, data analysis

We have a [CrashReporter](https://github.com/MovingBlocks/CrashReporter) project that allows users that crash an easy way to retrieve log files and submit an error report - but manually, merely aided by the CR.

This item would take it a step further to do automatic return of analytics to some back-end system we control, so we can easily see related error reports and spot patterns like all crashes of one type coming from a particular OS or video card.

There are existing frameworks that support such efforts, part of this idea would be researching what's available and writing a proposal for how to achieve this for Terasology

## Deep into Shaderland

* Difficulty: Moderate to High
* https://github.com/MovingBlocks/Terasology/issues/3251
* Contacts: [manu3d](http://forum.terasology.org/members/manu3d.1256)
* Helpful skills: opengl, glsl, 3D graphics, mathematics 

Once upon time there was a Renderer. It was good and did great cool things a many. But nobody dared entering the dark caves in which it worked, so full of arcane glRunes, monstrous code machines and the inextricable tangles of twisted couplings between them.

Eventually, three explorers descended into the caves, defying their own fear of forever becoming lost in the code labyrinth. Instead, after carefully mapping the area, they patiently moved every piece of machinery and every floating wisp of wizardry to the surface, where they built a number of well lit, neatly organized and welcoming workshops, where people of all sorts can work on the Renderer free of the terrors the explorers had to face.

HOWEVER...  deep underneath the workshops, a terrible secret still lies in wait, enraged and envious of the fortune that befell the higher level code... 

Shaderland. A basement full of codewebs as thick as carpets and gnarling, vicious tendrils of wizardry float gingerly mid-air, ready to grab and oblate the minds of those poor souls who venture within this land's borders. This is the land where Shaders live, doing their magic in the deep darkness where only a few can appreciate their strenuous efforts. But they are prisoners and cry in silence as they await for a destiny that never seem to arrive...

The Terasology crew heard their cry however! And is calling for action!

The Shaders need... a HERO! A selfless individual ready to plunge into the darkness, a valiant knight with enough fortitude to overcome the many obstacles, a liberator, who will lead the Shaders out of the darkness and into the light, where they can be appreciated and nurtured like the rest of the codebase. 

The Shaders... NEED YOU!

## Light & Shadow

* Difficulty: Easy to Moderate
* https://github.com/MovingBlocks/Terasology/issues/2576
* Contacts: [SuperSnark](http://forum.terasology.org/members/supersnark.14), [glasz](http://forum.terasology.org/members/glasz.66), [skaldarnar](http://forum.terasology.org/members/skaldarnar.270), [oniatus](http://forum.terasology.org/members/oniatus.1641),  [Josharias](http://forum.terasology.org/members/josharias.1201)
* Helpful skills: Game design, Blender, 3D modelling, world generation, AI

Our Light & Shadow concept is the oldest design we have with the most available game assets, however the game world itself isn't really prepared yet.

While we still lack key features in combat and meaningful PvP to achieve full replayable content with L&S at a scope suitable for GSOC the world setup should be doable, including many of the central gameplay features like base setup and maintenance. 

## Renovation for MasterOfOreon

* https://github.com/MovingBlocks/Terasology/issues/2078
* Difficulty: Moderate
* Contacts: [mkienenb](http://forum.terasology.org/members/mike-kienenberger.1215), [Cervator](http://forum.terasology.org/members/cervator.2)
* Helpful skills: AI, UI

The MOO module contains a basic command menu akin to how you manage your dwarves in Dwarf Fortress. While a few very basic functions work most of the menu options remain unimplemented (and somewhat awkward to use).

We need somebody to help modernize it (replacing a dependency on the old Miniion module) and flesh it out further to arrive at some DF-inspired gameplay within Terasology, managing creatures in a sensible fashion.

The DynamicCities module may integrate well with this item as it already has population-based cities - they just need to be populated by something!

## GPU-based Occlusion Queries to load medium-distance chunks only if they are visible

* https://github.com/MovingBlocks/Terasology/issues/1710
* Difficulty: Moderate to High
* Contacts: [manu3d](http://forum.terasology.org/members/manu3d.1256)
* Helpful skills: OpenGL, LWJGL

Terasology currently loads and unloads chunks (boxes containing 32x64x32 blocks) purely depending on their distance from the player. A ViewDistance set in the Video Setting to "Moderate" for example, will trigger the loading of 13x7x13=1183 chunks centered on the player. Depending on the circumstances many of these will be invisible, either because they are underground or because they are behind large obstacles such as hills and mountains.  

While the chunks representing the immediate surroundings of the player will probably need to be always loaded (so that the player can interact or perceive entities in her proximity even if they are behind obstacles), Terasology would benefit from loading medium-distance chunks only if they are visible from the point of view of the player or other significant point of views (i.e. the shadow map camera). 

By using GPU-based occlusion queries it could be possible to limit the number of chunks loaded by verifying that the bounding box of a chunk (a 32x64x32 box) is effectively visible given the geometry rendered so far. If it is the chunk gets loaded and rendered, if it isn't, the chunk remains in a "loadable" state until it is no longer occluded or until the player gets close enough to it.

By using this technique on average we could be able to reduce the number of loaded chunks for a given view distance or extend the view distance maintaining the number of loaded chunks.

This item on its own may be too small to fit GSOC scope well. It could be combined with improved chunk sorting (side-item for the world storage idea) or maybe the new approach for far rendering.

If you are interested on working on this particular challenge please engage in the discussion space provided by [issue 1710](https://github.com/MovingBlocks/Terasology/issues/1710).

## Game / saved world / module preview image content

* https://github.com/MovingBlocks/Terasology/issues/1487
* Difficulty: Easy
* Contacts: [msteiger](http://forum.terasology.org/members/msteiger.1197), [Josharias](http://forum.terasology.org/members/josharias.1201), [skaldarnar](http://forum.terasology.org/members/skaldarnar.270),
* Helpful skills: resource loading/locating, web design, presentation

This is a fairly straight forward addition to the create world / load game screens, and similar locations in the main menu. Currently we only use text to describe modules and worlds. But a picture is worth a thousand words!

When a player looks at an existing world we could present any screenshots the player has taken in that game, or if none have been taken use a logo or other placeholder graphic from the primary module.

For viewing modules you could again have logos or preview screenshots associated with each module. These could also be used on a module browsing site on GitHub or elsewhere.

For bonus points this could be extended into easy screenshot uploading (to imgur maybe?) or even in-game video recording made available along with the world as saved assets.

*Update:* As of February 2016 there is a [pending PR](https://github.com/MovingBlocks/Terasology/pull/2074) with a first step to a newer create game approach. It is pending a solution to a game context issue (to what degree is what loaded during setup/preview).

## Noise-based generation of distinguishable terrain features

* https://github.com/MovingBlocks/Terasology/issues/943
* Difficulty: Moderate (most concept work already done, sample code available)
* Contacts: [msteiger](http://forum.terasology.org/members/msteiger.1197), [MarcinSc](http://forum.terasology.org/members/marcin-sciesinski.1103)
* Helpful skills: knowledge of procedural generation, advanced mathematics, terrain generation

Infinite terrain worlds are typically generated by noise generators such as Perlin or simplex. While the generated patterns are aperiodic, no distinguishable terrain features are created.
Regions such as desert areas have only very little high-frequency noise while mountainous regions will have a lot. 

A first step could be to create abstract, large, high-level regions which are then refined depending on the type. Smooth transitions between such regions must be created.

Some regions such as lakes have additional requirements (flatness). Some effort on that particular issues has already been invested:

http://procworld.blogspot.com/2014/01/leveling-lakes.html

Sorted by difficulty, desired regions are: grassland, ocean, dessert, forest, mountain, lake.

## Leap Motion implementation

* https://github.com/MovingBlocks/Terasology/issues/934
* Difficulty: Moderate (and need to have a Leap Motion Controller)
* Contacts: [Cervator](http://forum.terasology.org/members/cervator.2), [nh_99](http://forum.terasology.org/members/nh_99.1095), [begla](http://forum.terasology.org/members/begla.1)
* Helpful skills: user interface design, user experience (UX), library design

We did a proof-of-concept implementation for using the Leap Motion Controller in-game quite a while ago and actually made a video on it: http://www.youtube.com/watch?v=H8-afb0yUoc

While Terasology isn't really super apt for motion control there are some interesting niche areas like spell casting or flying that could lend some novelty if a user happens to have a Leap unit laying around. This is a fairly open-ended item on how it should work, although an external library named [Jitter](https://github.com/openleap/jitter) was started to help out the effort and fleshing it out further would be ideal.

A few existing contributors have Leap units (we've had some good contact with the company - they actually reached out to us first!) and some additionally have Oculus Rifts, which we can also support, so there could be some interesting combination potential there like Leap VR... :-)

This item might go well with our VR item.

## Mobile server management utility

* https://github.com/MovingBlocks/Terasology/issues/929
* Difficulty: Moderate
* Contacts: [Immortius](http://forum.terasology.org/members/immortius.35), [mkienenb](http://forum.terasology.org/members/mike-kienenberger.1215)
* Helpful skills: mobile development (Android, _maybe_ iOS), web services, server software administration, user interface design

You can launch a Terasology server easily enough, but configuration is still pretty manual. We need to start expanding administrative options available and it would be very convenient (and a novel experiment to break into mobile land with) to also offer a small utility for smart phones and tablets to interact with a server, from managing users to viewing logs and maybe even observing from a map view (the AWT facade could hold some premise here)

There are likely existing similar utilities for administering MC servers that could be used for inspiration.

This item is more accessible after a GSoC project last year that exposed the game server via an API.

## New rendering approach for very far distances

* https://github.com/MovingBlocks/Terasology/issues/319
* Difficulty: Unknown (moderate or even straight forward for a fellow 3D wizard?)
* Contacts: [begla](http://forum.terasology.org/members/begla.1), [KaiKratz](http://forum.terasology.org/members/kai-kratz.53), [Immortius](http://forum.terasology.org/members/immortius.35), [manu3d](http://forum.terasology.org/members/manu3d.1256)
* Helpful skills: 3D graphics, LWJGL, OpenGL, rendering

This calls for a new rendering technique to support showing the world beyond normally visible chunks (where every block is rendered). The more distant detail would have to be reduced in some fashion to display the world in a more simplistic fashion at range. While there is a little more detail in the issue begla or KaiKratz would probably need to be consulted for more details, or any other 3D wizard we have with the know-how :-)

*Note:* This is a very old item and may be blocked waiting for more progress on https://github.com/MovingBlocks/Terasology/issues/2547 - it may be possible to start working on it. Contact Manu3d!

## Port advanced organic growth simulator from Python

* https://github.com/MovingBlocks/Terasology/issues/218
* Difficulty: Moderate (most concept work already done, sample Python code available)
* Contacts: [Woodspeople](http://forum.terasology.org/members/woodspeople.34), [MarcinSc](http://forum.terasology.org/members/marcin-sciesinski.1103), [jellysnake](http://forum.terasology.org/members/jellysnake.1938/), [glasz](http://forum.terasology.org/members/glasz.66), [ddr2](http://forum.terasology.org/members/ddr2.178), [ahoehma](http://forum.terasology.org/members/ahoehma.801), [mandarj](https://forum.terasology.org/members/mandarj.1964/)
* Helpful skills: Python, procedural generation, biology

Long ago cfkurtz / Woodspeople reviewed some old work she had done and prepared a growth simulator in Python that bases its growth on available water and mineral values in the soil, among other things (sunlight!). While we've since gotten an initial "growing trees" implementation working that is sufficient for showcasing growth in-game (doesn't consider its location much) it could be amazing to take it one (to many) steps further!

At a minimum this would port the Python version to Java based on simulated values where no exact data currently exists

* Sunlight is available
* Soil nutrients could be approximated by soil type, possibly the block could even change as it is depleted (and fertilizer bring it back)
* Moisture could be based on distance to water or again on block type (while aquifers could later yield a more exact per-block moisture level)
* Custom block shapes could be added to get higher detail level for branches and other smaller tree components

Any additional detail in the original plant simulator could be considered for extras.

*Update:* Since this topic was originally posted we improved engine support to where a large amount of extra information can be included via per-block biome data. There are also several more advanced flora-related content modules.

## Advanced and dynamic geology based on plate tectonics

* https://github.com/MovingBlocks/Terasology/issues/141
* Difficulty: High (more supporting systems needed, possible interaction with native C code)
* Contacts: [Laurimann](http://forum.terasology.org/members/laurimann.586), [Nym Traveel](http://forum.terasology.org/members/nym-traveel.213), [Immortius](http://forum.terasology.org/members/immortius.35), [MarcinSc](http://forum.terasology.org/members/marcin-sciesinski.1103), [msteiger](http://forum.terasology.org/members/msteiger.1197), [skaldarnar](http://forum.terasology.org/members/skaldarnar.270)
* Helpful skills: geology, procedural generation, advanced mathematics, advanced Java (dealing with native code)

This item is for generating a world based on plate tectonics such as provided by PlaTec or some sort of simulated version. At a minimum it should be able to read maps generated separately from PlaTec (or some comparable source) and in turn prepare one or several layered maps usable in-game to guide placement of actual blocks such as minerals in appropriate layers. A series of bonus features are possible:

* Connecting to PlaTec natively from Java to C to request a map (and maybe to take advantage of extra per-step data)
* Visually showing the plates moving during world generation in a simple map view mode in-game
* Placement in the world of volcanic and other interesting biomes related to tectonics

An actual study of the involved sciences is best left to surfing Wikipedia although a certain level of artistic creativity to enhance gameplay value would be welcome :-)

## Porting Destination Sol over to ECS

* Difficulty: High
* Contacts: [vampcat](http://forum.terasology.org/members/vampcat.2080), [Cervator](http://forum.terasology.org/members/cervator.2)
* Helpful skills: Experience with Terasology's ECS

[Destination Sol] (https://github.com/MovingBlocks/DestinationSol), another game developed by MovingBlocks, still utilizes OOP. This item focuses on porting the game over to ECS architecture. This will laying the groundwork for [gestalt-entity-system](https://github.com/MovingBlocks/gestalt), porting over at least some systems to use the new architecture (since porting the entire game over is not realistic in 3 months), and adding support for modules to be able to register their own systems via annotations. This is a open idea, and with the correct subset of systems and features, it should be feasible.

Note that work is on-going on this idea, and the student should contact the relevant mentors for the latest updates.

## Module Showcase Site

* Difficulty: Moderate
* Contacts: [jellysnake](http://forum.terasology.org/members/jellysnake.1938/), [Smsunarto](http://forum.terasology.org/members/smsunarto.1956/)
* Helpful skills: Experience with Web Development and Visual Design

Terasology aims to eventually provide a huge number of modules enabling a large number of different features. We currently have over 150 modules but the vast majority are never seen, used or otherwise even known about. This idea is to develop a module showcase site that will help to solve this issue for both Developers and Users.  

The end goal of this is to produce a site that provides a section for each module containing a basic information page, and one or two wiki subsections for Developers and/or Users. The main page of the module should allow for searching of modules by category, keyword, name etc etc, as well as providing other methods of discovering modules.  
Secondly, there should be additional integration with the game. This would most likely involve a UI overhaul of the Create Game and/or Module Select screen that would also include a method to integrate modules selected/found on the site to be installed in the game.

As we are obviously an open source project, we don't want to nor are able to provide the resources to manually fill out, upload and otherwise populate this site with the information about modules. To this end, as much of the content on the site should be scraped from other sources and operations should be as automated as possible. This means things like creating the main info page from the `module.txt` and Readme files; populating the wiki pages from the github wiki and the readme; automatically creating a new entry into the site from our jenkins/artifactory instance; and other similar tasks. These methods should not be the only way to create/edit the info in each module's section as to allow users to upload modules that they have created that is out of the supported lineup for instance.

As extras this could also rehaul the current method of storing modules and delivering modules, with current ideas proposing solutions such as central storage on Archive.org (like [CKAN](https://github.com/KSP-CKAN/CKAN)) and/or using a torrent like peer-to-peer method.

*This idea doesn't require the level of java that other items do, and thus is idea for a student that doesn't have high java proficiency. Instead high proficiency with Web Development is needed.*

## Genome Integrations

* Difficulty: Moderate
* Contacts: [mandarj](https://forum.terasology.org/members/mandarj.1964/), [jellysnake](http://forum.terasology.org/members/jellysnake.1938/)
* Helpful skills: Experience with Terasology's component system

Terasology has a rudimentary [Genome](https://github.com/Terasology/genome) module which allows you to assign simple genetic codes to entities and cross two similar genomes to get a new daughter genome (breeding). However, this is still a general purpose abstract system, and needs to be implemented in a way such that it contributes to the game in a meaningful way.

Last GSoC, arpan98 took on this task (and another one), and was able to improve the base Genome module and it's breeding algorithms, and implement a simple breeding and growth system for animals (more specifically, deer). A more detailed account of his progress last year can be found in [his wrap-up post](http://arpan98.github.io/2017/08/23/gsoc-wrap-up-post.html) and in other posts on his blog.

However, there is still a long way to go until Genome can become a big part of the game. For example, it should be integrated into SimpleFarming to produce variation in different plant features through genetics, as is described in [this issue](https://github.com/Terasology/SimpleFarming/issues/46). There is an open [Pull Request](https://github.com/Terasology/SimpleFarming/pull/57) which aims at getting started with this, but most of it needs to be rewritten as it isn't compatible with the recent refactor of the SimpleFarming module. Integration with WildAnimals also needs a lot of work.

Check out [this issue](https://github.com/Terasology/SimpleFarming/issues/82) for a tentative roadmap for integrating Genome with SimpleFarming.
