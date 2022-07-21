# Inflection Points - development guidelines

This document will outline general procedures & guidelines for issue tracking, commit/code formatting, deployments, etc...

## Issue tracking (to-do's)
To ensure maximum transparency to all team members, any new feature, bug, enhancement, optimization, etc should be documented in a GitHub issue.  Issues should be limited in scope, and focus on very specific areas of work.

* Back-end, DevOps, and any other **non-user facing** issues should be added to the [Crypto Institute API](https://github.com/Inflection-Points/inflectionpoints-api) repo.
* Front-end, UI/UX and any other **user facing** issues should be added to the [Crypto Institute Web-Client](https://github.com/Inflection-Points/inflectionpoints-web-client) repo.

Just because a particular issue falls outside of your typical work scope (e.g. Steve discovers client-side error with a form input) don't hesitate to create an issue for a teammate to resolve!  Even though this could feel rude to point out problems with someone else's work, being completely transparent will be hugely beneficial to the whole team in the long-run.

### Titles
Issues titles should be adequately descriptive without being overly verbose.  A good issue title might something like "Track/lesson search functionality" and a bad one would be "Add track/lesson search bar by implementing ElasticSearch on related data models".  The second title gives far more info than is needed at a quick glance and it would make more sense to add the minutia to the issue description.

### Descriptions
At a minimum, descriptions should contain a checklist of action items that must be completed in order to resolve the issue.  How you decide to organize this is at the issue creators discretion, but in general if there are new files that need to be created or specific tasks that need to be completed, each of those should be outlined in a checkbox list.

Sometimes an issue is more complicated than a few bullet points.  In those cases it can be help to break the description into "Overview" & "Tasks" sections.  The overview can contain a general description of the bug or feature.  Consider including a block-quote with a message if you're creating an issue based on a message or email you received.  The "Tasks" section should then contain your checklist of action items.

*See the ["Study Guide resource"](https://github.com/Inflection-Points/inflectionpoints-api/issues/133) issue for a good example of this*.

#### *Nested issues*
Frequently when it comes time to actually work on an issue, you realize the scope of the work too complex to complete in a single siting.  When this is the case, issues should be broken up into smaller, tightly scopes segments.

A good example of this is the ["Email template improvements" issue](https://github.com/Inflection-Points/inflectionpoints-api/issues/689).  At first the tasks seemed straight forward...

1. Verify email address email template
2. Forgot password email template
3. Batch user registration complete email template
4. Email verification reminders
5. Video upload & processing complete notifications

In reality, each of these tasks require several steps to complete them (e.g. create custom notification, custom mailable object, add tests to ensure notification was sent).  Instead of adding more tasks, a new issue was created for each of the checklist tasks that is automatically linked to the original issue.

*note: this section will be improved to provide more clarity*

### Comments
When you come across useful resources (StackOverflow, API docs, dev blogs, etc) related to your issue, make sure to link them in an issue comment, even if it's for yourself.


#### Assignees
Most of the time assignees aren't need since issues are typically created by the person responsible for them, but in the cases you're creating an issue related to someone else's work make sure to assign it to them so they know you need their help!


#### Labeling
Whenever a new issue is created, it should be labeled appropriately so that at a quick glance anybody (even if they're unfamiliar with the issue) can determine its nature.  Labels should answer questions like "Is this a new feature or an enhancement to an existing one?", "Is this a bug?", "Is this a refactor or optimization of existing code?".

* [Back-end repo labels](https://github.com/Inflection-Points/inflectionpoints-api/labels)
* [Front-end repo labels](https://github.com/Inflection-Points/inflectionpoints-web-client/labels)

The majority of issues should include either the "bug", "enhancement" or "new feature" labels.  An "enhancement" being an entirely new feature, that doesn't currently exist.  And "new feature" being a feature that doesn't exist.


#### Milestones
Milestones represent groups of features like "Registration workflow" or "Student dashboard UI".  This allows us to easily associate issues that are related to the same body of work.  In general, Colton will set the milestones and it will be the engineering teams responsibility to appropriately assign their issues to the correct milestones.

#### Projects
As of now we have a single ["Crypto Institute" project](https://github.com/orgs/Inflection-Points/projects/1) with all of the back-end and front-end issues.  In the future we may want to segment this further by adding other project boards like "Crypto Institute - nice to haves" but for now all new issues will be automated through GitHub actions to be added to our ["Crypto Institute" project](https://github.com/orgs/Inflection-Points/projects/1).

After an issue has been created and added the project, it ends up in the "Backlog" column by default.  If you're about to start working on this (that day), make sure to move it to the "In Progress" column.  If you plan on working on it in the coming days, move it to the "To-Do" column to indicate its not currently being worked on but is one of the next issues up in the queue.


## Branch creation & pull requests
Once you've created an issue for your bug or feature, the next step is creating a new Git branch to commit your code changes to.  This should be done by clicking "Create a branch" in the "Development" section of the right hand column on the GitHub issue details page.

By creating a branch linked to an issue, you ensure that merging a pull request from that branch into the main branch will automatically close your issue.

### Pull requests
* should be use the same labels as their related issue
* if you're created a pull request on someone else's repo, request them to review it
* once you've committed all of your code & the automated test have passed, "Squash & Merge" your changes into the main branch
* "Squash & Merge" should be used instead of a standard "Merge Branches" to keep the commit history as clean as possible ("squashes" all your commits on that PR to a single commit)
