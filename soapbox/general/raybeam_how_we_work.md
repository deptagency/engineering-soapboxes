## Summary

Each client is different, but the approach to development shouldn’t be.  This is an effort to settle on a single way of doing work across clients so we have a common framework that can be improved over time.  

This is a living document, feel free to create a PR against it.

## Technical specification


### Goals: Why are you writing a spec?

1. Clarify your own thoughts on how build or design a part of the system (feature)
2. Have others review and understand the design before you spend a bunch of time writing code
3. Allow multiple developers to work on a single feature


### Requirements: What has to be in the spec?

Your doc should include: 

1. What you understand the requirements of what you’re building to be
2. How you plan on meeting those requirements.
3. A “definition of done” that identifies specific handoffs, quality checks or milestones that mean you can stop work on implementing that spec.   

If you don’t have any requirements, that’s a problem.  Sometimes, for smaller items or for projects where Raybeam is considered the technical expert, you may have to provide your own requirements.  You can do that a number of ways, but one good way is to ask someone you know has already done similar work.

How do you find someone who’s already done similar work, if you don’t know anyone?  Ask on your project’s Slack channel, the #ReferencePipeline or #General Slack channels, the Client or Project lead, or your mentor.  But a quick shake of the trees should tell you whether you can use someone else’s guidance, or you have to start fresh.


### Design

You’ll have to explain how you plan to meet each requirement.  Ideally your explanation includes some sort of visualization.  Get familiar with Google Draw or some other diagramming tool.  Visualizations are easier for people to understand.  You’ll need to get comfortable with them so you might as well start with tech specs.

Include a detailed explanation of how you want the system to work, like a workflow or state diagram.  Think of how data makes its way through your feature.  Also, think how the feature will be used and misused.  Account for problems.  Call out risks.  Identify monitoring points.

Also, and this is important, do NOT overdesign the system.  If you need to parse a CSV, just parse the CSV, don’t have it handle all formats.  Over-engineering just means more to support.  This doesn’t mean you shouldn’t think about people changing your code in the future.  Write easily understood, easy to maintain code.  

You should be able to write the spec in a matter of hours.  Keep it simple.  Meet the requirements.  Don’t over-engineer it.  You aren’t trying to solve the whole problem at once.


![first_do_it](first_do_it.png)


### Risks

We’re always building things that depend on work that hasn’t finished yet.  Call this out.  If your feature depends on a dataset that hasn’t finished yet, say that.  If we haven’t yet gotten access to launch this feature into production, call it out.  It’s up to you to understand the risks of the feature so that you can notify your team members.  That’s how we clear roadblocks before they become a problem.  This can be as simple as a list of known dependencies at the end of your doc.


### Notes


#### What’s it for?

Anything larger than a small fix or bug.  


#### Can I write code before finishing this?

YES!  I often need to write some prototyping code to figure out if what I’m trying to do is even workable.  Some of this code might even end up in the actual feature.  


#### Examples

These are not exhaustive.  They just happen to be examples that I think illustrate some of the points I’ve made above.  If you have a better idea or something that works better for you, do it.

## Specification review


### Goals: Why do the review? 



* Give team members a chance to review and speak about changes or improvements
* Notify team members about new work to start
* Give other team members a chance to volunteer additional work


### Requirements: How to run the review meeting 

The specification review should be scheduled by the person writing the spec.  The review session should be 60 minutes, unless there’s a good reason to be shorter or longer.  It’s OK to end early if everything is handled.  It is NOT OK to end before the review is finished.  

The spec writer should send out the spec beforehand with a note for everyone to read it over.  The meeting should not start with the developer just reading through the spec and the developer should assume everyone has at least read the spec doc.  The review should start with a quick summary and then quickly get into questions and comments.  Ideally there are already a fair number of comments in the doc when the review starts.

The spec writer should take notes (or ask someone to take notes) in the spec document.  The notes either change the document or are recorded but rejected.  Include the reason for rejection.  A note could also just be something to be aware of.


### Follow up: When is it necessary?

Unless the original spec is subject to a lot of revision, the spec should be considered finished after changes that come up during the review are addressed.


## Scheduling work

We prefer to use Jira to track effort and activity on our projects. 


### How to track your activity

Your work on the project is broken up into pieces.  You can’t work on everything at once, and you have to do some work before you can do other work.  It’s this sequence of your workflow that you need to track in Jira.  

The big components you’re working on building - an Airflow DAG to move data from point A to point B, a SQL script to move data from layer A to layer B, or something similar - are part of larger components as well.  

We try to structure our work so that it supports a specific customer deliverable: A dashboard, a capability, an ML model, whatever.  These deliverables are tracked as “Epics.”  To actually make those deliverables there’s a bunch of other work we need to do, and we track those smaller deliverables as “Stories.”  Finally, your actual workflow, the things you personally need to do, are tracked as “Tasks.”

You don’t have to follow someone else’s breakdown on their workflow, unless you think it seems to be more efficient.  But it should be possible for the Project Lead to look at your Stories and get a pretty good sense, based on the status of your Tasks, where you’re at.


### Epics 

An Epic is a customer deliverable and the work required to deliver it.  It will often last many months and require coordinating several teams.  The end-goal is something the customer uses, so there should be some consideration in planning an Epic as to who’s going to take over the operation of the thing we’re building.  

A good example of an Epic would be “An Email Dashboard that consolidates data across all of the client’s ESPs.”  Another might be “Develop a Data Catalog product for use by Raybeam clients.”  In both cases we’ve got a specific deliverable with a reasonably clear “definition of done” for the Epic.  Each one requires multiple teams, and will take a long time to deliver.


### Stories

“Stories” describe chunks of work that need to be completed to conclude an Epic, to some level of abstraction.  Each Story should have an attached spec that explains the requirements and a plan for the completion of the Story.  

A good Story might be “Ingress SFMC data into BQ using the Reference Pipeline.”  (We might abbreviate that story as just “SFMC Ingress.”)  An “SFMC Ingress” story identifies a discrete bit of work that needs to be done to support its Epic.   

Another good Story might be “SFMC Transform,” which describes the work that needs to be done to move data from RAW into the BO layer.  

A third good story example is “Create an operator to create a schema json for each source provided a list of tables.”

Not all Stories are simple or discrete.  You have some discretion, and it’s best to get some agreement with your team on how to construct stories.  

The Project Lead should be able to figure out what you’re working on by looking at your current Stories.  Ideally a Story should take no more than two weeks to complete, and better if it’s a week or less.  


### Tasks

Tasks are bits of work that are needed to complete the Story.  Tasks should usually take a day or less.  If a task takes longer than a day, consider breaking it up.


### Bugs

Bugs are issues found in the code.  They may take longer than a day to fix but hopefully that’s not the norm.  Bugs are about the only task that won’t be part of a Story.


### **Pre-sprint work** 

When a sprint starts, the Stories for that sprint should already be in the backlog.  Ideally, we’d have more than one sprint’s worth of Stories in the Backlog.  For that to happen, each person should:



* Review the schedule to see what’s up for next week
* Have a spec written and reviewed for the next week’s work, if it needs a spec
* Have each reviewed spec broken into epics, stories and tasks in the backlog
* Be ready to estimate and assign work at the upcoming sprint meeting


## Sprints

Sprints are units of work.  They should be 1 week long as a default.  A team could move to 2 week sprints after a couple of weeks or months if they feel comfortable and have a history of accurately estimating work.


### Goals: What do we need sprints for?



* Accurately predicting the velocity of a team
* Splitting work periods into something concrete
* Adapt to changes in priorities quickly


### Sprint meeting 

This is a single meeting where one sprint ends and another begins.  It’s probably best to set aside 60 minutes.  Ideally, this meeting could also act as a weekly status meeting.  This meeting should include everyone who plans to work in that sprint.


### Process: How to run the Sprint meeting


#### Review last sprint 

What was completed and what wasn’t?  What lessons are there to learn that can apply to the new sprint?  For example, were items missed because of blockers that could also push back items in the new sprint?  Under or over estimation of work should be called out by **those that under or overestimated.**  This is not a chance to blame, but to improve.  If you thought something was going to be easy and it wasn’t, we all want to know because we may have to pick up where you left off.


#### Pull work from Backlog into new sprint

Each person should pull a sprint’s worth of work.  That work might also include items from the last sprint.  The goal should be to accurately estimate one sprint’s worth of work.  You can move Tasks inside a Story into the Sprint too, instead of the entire Story.  


#### Estimate work in the backlog 

Part of the meeting should be used to identify about the next two sprint’s worth of work in the Backlog.  These estimates may change by the next sprint meeting, but ideally the next sprint meeting is just pulling that work in.  


#### Announcements 

If the Sprint meeting is being used as a weekly status meeting, use the end for announcements, including whether any is on upcoming PTO.


#### Start the sprint 

Kick it off and get to work


### Notes 



* Leave time in your estimates for writing and reviewing specs.  If a spec needs to be written, it should be a Task
* Bugs take up time, so estimate them
* If the sprint changes a lot, we’re not planning well.  Fix the planning problem, don’t try to jam stuff into the sprint.


## Branching and releasing

With multiple people working on a single project, it’s important to manage your code.  A single mainline with feature branches is both effective and not too complicated.  The overall idea is that 



* You have a consistent main branch of code that has all reviewed changes.  
* For any new code (bugs, features, etc), you branch from the main branch.   
* Releases are tagged off of main.  Hotfixes are fixed on main and then cherry-picked to a release.


### Details

[https://www.bitsnbites.eu/a-stable-mainline-branching-model-for-git/](https://www.bitsnbites.eu/a-stable-mainline-branching-model-for-git/)


### Tools

I’ve had success with git-reflow for capturing the principals outlined here in a tool: [https://github.com/reenhanced/gitreflow](https://github.com/reenhanced/gitreflow)


## TODO



* Data QA / UAT
* Dashboard development
* Deploying code and DDL changes
* Post mortems / Retrospectives
* Demos