This page contains a suggested outline with explanations for how to handle an accepted GSOC project from the time of acceptance to the final evaluation and beyond. We've tried using [Trello](trello.com) for keeping track of things and for 2018 are taking in a step deeper with a [GSOC column on a Trello roadmap with a step-by-step checklist](https://trello.com/b/E6PfiSX8/roadmap-and-volunteers). We naturally also use GitHub heavily along with our forum.

## GitHub

GitHub serves two purposes. One is simply storing the produced code in a suitable location, another is keeping a GitHub project board to manage tasks for the given GSOC project.

There are two main GitHub organizations involved, which may grow in the future

* [Terasology](https://github.com/Terasology) - this organization holds all Terasology modules, and content-focused projects will tend to affect one or more module repos. The GitHub project board for these projects should be defined under this org.
* [MovingBlocks](https://github.com/MovingBlocks) - this holds anything not a module, like the [engine](http://github.com/MovingBlocks/Terasology) itself and a variety of libraries and infrastructure related repos. Any project that mostly affects the engine, our infrastructure, and so on should go under this org.
  * [DestinationSol](http://destinationsol.org)'s "[engine](https://github.com/MovingBlocks/DestinationSol)" and similar also lives under this org, with its modules likewise in a [separate dedicated org](https://github.com/DestinationSol/). DS GSOC projects thus may go here or in the future under its module org.

### The Project Board

[Kanban](https://en.wikipedia.org/wiki/Kanban_(development)) has become a typical way to organize software development and GitHub offers a basic board you can use with the process, including some nice automated extras like closed PRs going to a "Done" column.

We're trying to use that process to track GSOC projects. This is not necessarily a mandatory requirement if the student + mentor team are more comfortable with a different tool instead, such as Trello. Talk it out if needed. But ideally most/all projects will follow the standard making it easier to keep track.

During the bonding period when projects have been announced the board should be created, populated, and finalized in its initial form toward the end of the bonding period / very early work period. During the work period it should be reviewed regularly, mostly during the weekly meetings, to make sure goals remain realistic. Expect plans to change and cards to move around between months, get moved out to the backlog or even go out of the project entirely if reaching those tasks becomes unrealistic.

Extras such as stretch goals from the proposal should start in the backlog and only be moved to a month when there is available space. As the project approaches the end create an "Outbox" column for features that have been cut from the main project but may be desirable in the future.

GitHub project boards have a progress bar that counts cards in the columns flagged as todo, in progress, and done. This progress bar should be filling up nicely toward the end, especially as the backlog is being emptied out (worked or moved to the Outbox). Be sure the Outbox column is *not* marked for any kind of automation, as it isn't meant to be counted toward the project status.

Some steps to be sure to get done to the project board

* Start with the automated kanban template board. This results in three automated columns (as per May 2018)
* Configure the board to be publicly viewable with org members having write access (Menu -> ... -> Settings)
* Rename the default "ToDo" column to "Backlog" (since there will be multiple todo columns)
* Add three month columns for the three major segments of the work period. These should be marked as todo but not involve automatically moving issues into them
* Delete the month columns over time as they are spent and have been emptied out
* Create an "Outbox" column at some point toward the end of the project to hold cards that will not be completed on time

The final ordering of the columns should be (from left being furthest out to right being closest to or beyond completion): [Outbox,] Backlog, Month 3, Month 2, Month 1, In Progress, Done

## Trello Project Card

Trello is primarily used to organize GSOC itself, not so much the work being done by students. The main product here is a single project summary and progress card that lives on our [Roadmap Trello](https://trello.com/b/E6PfiSX8/roadmap-and-volunteers) and should be tended over the project's duration by the team, checking off items as they are completed. The card is described in deeper detail in the following sections

### Summary Info

Every GSOC project ends up with some metadata, which goes into a summary section. Some parts from there can also be posted in the forum thread. Template and description follows:

* **Description**: Brief description of what the project aims to achieve
* **Student**: Name of student plus any alternative nicknames on various services
* **Mentors**: List of mentors
* **Github**: Link to the project board on GitHub
* **Slack**: _#some-channel_ on Slack that's the primary home for live chat 
* **Forum**: Link to the student's GSOC forum thread (for regular updates)
* **Weekly meeting**: Scheduled time for the student + mentor team to meet and discuss progress / status
* **Blog**: We encourage students to do blog entries for their work, rather than just forum threads (which may just be links to the blog and some real brief notes in that case)
* **Availability**: Reminder for anything unusual such as a student being unavailable during period x, which might mean they aim to start a week or two early to make up time. Could also cover unavailable time during the bonding period so we can better coordinate planning sessions
* **Proposal**: Link to the original proposal (the timeline built on the project board may vary)
* **API impact**: Whether or not the project is likely to cause a violation of the [[Modding API]] at some point and if so then roughly how so we can plan ahead (long term topic branch for the engine for instance)

### Pre-GSOC (Bonding Period)

This time is ideal for filling out the summary info, making sure everything is ready for the project to start. It is also good for any remaining (re)planning needed if the proposal doesn't translate 100% exactly to a set of story cards for the project board. It should be possible to copy the following list into a Trello checklist to create one item per line (although we should have a template card / an initial student to just copy off - plagiarizing is great for building checklists!)

* **GitHub board created** - an initial empty board has been set up on GitHub as detailed in its section above
* **GitHub board populated** - the proposal is roughly represented on the board via cards in months 1-3
* **GitHub board planning finalized** - feedback from planning sessions have been applied to the board (add, remove, modify)
* **Slack channel ready** - there is a dedicated channel on Slack with the student + mentor team present
* **Forum thread posted** - student has posted a project thread in our [student forum](https://forum.terasology.org/forum/student-programs-gsoc-gci.64/)
* **Weekly meeting scheduled** - the team has agreed on an ideal weekly time to meet (can use a [Doodle Poll](https://doodle.com) to figure out ideal times) and a calendar invite has been sent out (include terasology@gmail.com to add it to the overall project calendar)
* **Blog** - student has had a chance to set up a blog if desired, if not then can just use forum
* **Availability** - has been filled in for the summary
* **API impact considered** - has been filled in for the summary
* **Slack channel reminder set** - use `/remind #channel-name about weekly GSOC @channel meeting at 4 pm EDT every Sunday` to set the reminder in the given channel, causing a full channel ping weekly when it triggers

### GSOC work period

After the work period formally starts we expect the student plus mentor team to meet once a week, and at a minimum post an update to the Slack channel and the forum/blog (for better visibility) weekly. As a slight additional bit of structure to that we can keep a checklist of the same in the Trello card. Feel free to add dates to mark the weeks better.

In addition to the regular weekly events there are a few other spots with extras, like the evaluations.

* Week 1 - meeting & status update
* Week 2 - meeting & status update
* Week 3 - meeting & status update
* Week 4 - meeting & status update
* First evaluation completed - student
* First evaluation completed - mentor
* Week 5 - meeting & status update
* Week 6 - meeting & status update
* Week 7 - meeting & status update
* Week 8 - meeting & status update
* Second evaluation completed - student
* Second evaluation completed - mentor
* Re-evaluate backlog, create column "Outbox", start moving items there that won't be completed
* Week 9 - meeting & status update
* Week 10 - meeting & status update
* Week 11 - meeting & status update
* Week 12 - meeting & status update
* Student submits work + eval
* Final eval - mentor

### Post-GSOC

After the project work has been turned in and evaluated there are usually a few loose threads to tie up or extras that could be done.

* Delivery of work (if not done as part of project - for instance feature branch for next major release)
* Retrospective with student + mentors
* Presentation of new features available (may be part of project / final blog)
* Future potential in the area / where to go next / new person start hints (could also be a blog entry)
* Close out project board (especially the "Outbox") / make follow-up issues

## Forum

Our [Student Forum](https://forum.terasology.org/threads/gsoc-2018-overview.2163) is the default place for update reports and a single project thread should be posted and maintained per student.

The initial post should include some of the details from the Trello card's summary info. Students should aim to post a weekly update which could be entirely in the thread or consist of a few brief words and a link to their blog.

### Suggested template for weekly report

* What have you achieved in the last xxx?
* What are you currently working on?
* What problems are you currently facing?
* Is anything blocking you from making progress?
* List of PRs and opened/closed Issues
* Something else (pictures of new content, code snippets, new wiki content, …)