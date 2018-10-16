Github has a nifty feature to add labels to both Pull Requests and Issues. This is a feature we use to help keep track of both of these and to help sort them. This page will list all of the labels we use at the moment and provide information about each one.

If you have the permissions to add labels, please pop them onto any issues or pull requests that you notice are missing them. Even if you are not fully sure, better to have a slightly wrong label than no label at all.

*All the labels are able to be added to both Pull Requests or Issues.*

### Size Related

Some of out issues are small, bite size and good for beginners. Others are large behemoths that would require a seasoned contributor a few months of work. These labels are mainly used for the writeup issues, although they can also be placed onto large pull requests.

|Label|Description|Colour|
|:-|:-|:-|
|**Good First Issue**|*Doesn't require much work or knowledge.* Good for beginners. Used to mark issues for beginners to start from. Also used to display an issue on up-for-grabs.net. We should always have a few issues marked with this label|![](http://via.placeholder.com/50/0e8a16/0e8a16)|
|**Mentor Size**|*Requires an average amount of wok and knowledge.* The step above Good First Issue. Marks issue as suitable for a contributor that has an understanding of the codebase.|![](http://via.placeholder.com/50/3cbd45/3cbd45)|
|**Epic**|*The item will require a large amount of work and knowledge.* The item is rather large and will require substantial work. Some overlap with the GSoC label, but not all *Epic*s are suitable for GSoC.|![](http://via.placeholder.com/50/6ae672/6ae672)|

### Program or Third Party Specific

Firstly, these are the labels that flag an item as being a part of a program or otherwise related to another service. Currently these are [GSoC](https://summerofcode.withgoogle.com), [GCI](https://codein.withgoogle.com/), [Hacktober](https://hacktoberfest.digitalocean.com/) and [Bounty Source](https://www.bountysource.com/), although we are always open for more.

|Label|Description|Colour|
|:-|:-|:-|
|**GCI**|*This item is part of a Google Code-In task.* Should be used on issues that are related to a particular Google Code-In task. Often used on PR's that complete a task and on issues that have been turned into tasks.|![](http://via.placeholder.com/50/bfb2e2/bfb2e2)|
|**GSOC**|*This item is part of a Google Summer of Code proposal.* Often used on PR's to mark that they are part of an ongoing proposal. Also can be used on issue writeups of proposals & proposal ideas.|![](http://via.placeholder.com/50/8c6be2/8c6be2)|
|**Hacktoberfest**|*This item is a part of Hacktoberfest.* Either indicates that a PR is intended to be part of Hacktoberfest. Alternatively that the issue would be a good fit for the program.|![](http://via.placeholder.com/50/7965ad/7965ad)|
|**Bounty**|*This item has a BountySource attached to it.* Placed on all issues that have an associated bounty on BountySource.|![](http://via.placeholder.com/50/6441be/6441be)|

### Bugs and Support

It is inevitable that software breaks or doesn't work properly. These labels relate to this, indicating bugs, and user issues.

|Label|Description|Colour|
|:-|:-|:-|
|**Bug**|*Details or Fixes a bug.* If used on an issue indicates an outstanding bug. If used on a PR indicates the PR fixes a bug. A link to the issue (if any) should be included in the PR.|![](http://via.placeholder.com/50/e10c02/e10c02)|
|**Support**|*Helping a user or dev with a particular problem.* Indicates where a user or developer needs assistance with something. For instance, having trouble setting up the workspace. Distinct from a Bug. Should highlight common problems.|![](http://via.placeholder.com/50/d55252/d55252)|
|**Needs Info**|*The issue needs futher information to be solved.* Often partnered with Bug or Support. Highlights an issue as needing further information or discussion to be solved. For non Bug/Issues see Research|![](http://via.placeholder.com/50/ff7a79/ff7a79)|

### Specific Code Sections

These are labels for items that directly interact with specific sections of the codebase. For instance with the NUI framework, the Rendering subsystems and so on.

|Label|Description|Colour|
|:-|:-|:-|
|**Rendering**|*The item directly involves the rendering systems.* Used on items that utilise or change the rendering system directly.|![](http://via.placeholder.com/50/fbca04/fbca04)|
|**Physics**|*Involves the Physics engine.* Used where the focus of the item is on the Physics Engine.|![](http://via.placeholder.com/50/bafca4/bafca4)|
|**UI**|*Involves visual or functional changes to the UI.* Use where the item involves changes to an element of the UI systems.|![](http://via.placeholder.com/50/bfb2e2/bfb2e2)|
|**Multiplayer**|*The item directly involves multiplayer functionality.* When the item has a direct interaction with multiplayer. Either through using it or through effecting it.|![](http://via.placeholder.com/50/fef2c0/fef2c0)|
|**Content**|*The item adds new gameplay based content.* Should only be used on things that will interact with Core|![](http://via.placeholder.com/50/207de5/207de5)|
|**Artwork**|*The item Involves changes to some artwork.* Used on items that involve changes to some art assets to Terasology. For UI changes, use UI|![](http://via.placeholder.com/50/FFFF07/FFFF07)|

### Implications and Aspects

Some items have important impacts on certain aspects of a project. For instance, it may improve performance, or raise security concerns

|Label|Description|Colour|
|:-|:-|:-|
|**Documentation**| *The item involves Javadoc or Developer Documentation.* When used on an issue, often indicates it involves general Terasology documentation. When used on a PR indicates the PR has a focus on Javadoc. Can often be combined with Logistics. |![](http://via.placeholder.com/50/02d7e1/02d7e1)|
|**Security**|*The item has security implications.* Should be used where the item is either a security breach or aims to alter the existing security code. Also can be used where security implications need to be considered|![](http://via.placeholder.com/50/d4c5f9/d4c5f9)|
|**Performance**|*Item is likely to change performance.* Used when the item is probably going to noticeably impact performance, either positively or negatively. |![](http://via.placeholder.com/50/7B8075/7B8075)|
|**Logistics**|*Item involves changes to the technical or contributor logistics.* Used where the item requests or makes changes to an element of our logistics or infrastructure. Examples include gradle/groovy, proposals for changing workflow elements.|![](http://via.placeholder.com/50/B322B3/B322B3)|
|**Api**|*This PR will involve a change to the Api.* Used on PR's that will involve a notable change to the API, or having an API risk. Can also be used on issues to mark them as being about the Api.|![](http://via.placeholder.com/50/eb6420/eb6420)|

### Miscellaneous 

These are labels that don't fit into any category, or are a category unto themselves.

|Label|Description|Colour|
|:-|:-|:-|
|**WORK IN PROGRESS**|*Contributor is still working on this PR.* Indicates that a PR is still under development and should not be merged until this label has been removed.|![](http://via.placeholder.com/50/e56eb1/e56eb1)|
|**Architecture** |*Changes or additions to the underlying architecture.* Involves a rework to the underlying architecture of some feature or element. Doesn't always result in API changes.|![](http://via.placeholder.com/50/A13027/A13027)|
|**Research**|*The item requires further discussion and community feedback.* Used to mark proposals, often where more community feedback is needed. When used on a PR often marks a proof of concept.|![](http://via.placeholder.com/50/bfe5bf/bfe5bf)|
|**Blocker**|*This item is needs to be fixed before the next release.* High priority. Highlights a problem that needs to be fixed before the next release can go through. Mostly used on major bugs near release date. |![](http://via.placeholder.com/50/000000/000000)|