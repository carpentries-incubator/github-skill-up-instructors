---
title: "Using Markdown"
teaching: 10
exercises: 2
---

:::::::::::::::::::::::::::::::::::::: questions 

- How do I edit a file in a Carpentries lesson?
- How do I suggest those changes back to the Carpentries?
- How do I edit the suggested changes after I've submitted them?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Edit a file in GitHub and commit
- Create a Pull Request
- Edit a Pull Request
- Navigate the PR review structure

::::::::::::::::::::::::::::::::::::::::::::::::


This episode will dig further into suggesting changes using the lesson infrasturucture. 


Imagine we are looking at rendered "instructor view" to prepare to teach, we notice we can review all images that are part of the lesson to see how we want to reuse them.
We then notice that the the 2nd image cinnamon rolls doesn't have any alternative text.
Alternative text or alt text, is often used by individuals with vision disabilities to relate the contents of an image.

Let's suggest an update to the lesson so this image has alt text.
First, we will file an issue to alter maintainers to the problem.

<!--- TODO: Add call out describing the maintainer role -->

## Filing an Issue

We will first go to the source repository again and open the "Issues" tab.
We can make a new issue by clicking the "New Issue" button in the upper right side of the window.
However, best practice is that we search through existing issues to see if anyone has already reported this one.
I'll search for "alt text" in open issues (the default search options on this page).
I can see that issue #4 is about alt text, I'll open it to see if it is the same as what I was planning to describe.
It is, in fact, the same issue!

Instead of reporting it, I could then add more info to the existing issue if I think it is needed.
This would be enough to help the maintainers get started.
However, if I want to suggest the change directly, I can do what is called a "Pull Request".
A "Pull Request" is where someone makes a copy of the lesson, make changes, and then suggests the official repo "pull"
the updated version if they are happy with those changes.
Making a "pull request", often called a "PR", is a great way to support lesson maintenance and to help get changes integrated faster.

## Creating a Pull Request

First, before I start to make the changes, I'll let others know I'm going to work on this issue.
If you are affiliated with the repository, you might be able to click the "assign yourself" button under the 
Assignee's section on the right side. However, most of us will not have access to the Carpentries Lessons directly.
Instead, we will type a note in as a comment, "I'll go ahead and make a PR with this change".

Next, we need to find the file we want to make changes to.
This change needs to be made in the recipe instructions page, we can get a hint at the file name
by looking at the URL of the rendered webpage.  It says it is `recipe_instructions.html`, which is a 
hint that the file name will include `recipe_instructions`.
This is an "episode", a section of a lesson, so we can find it in the `episodes` folder.
The file is in Markdown format, a simpler text language, and then the Workbench infrastructure renders it as an html, 
so the file itself is called `recipe_instructions.md`

Before we can make the change in our lesson, we need to know the proper syntax in the Workbench markdown to 
add alt text to the image.


::::::::::::::::::::::::::::::::::::: challenge 

## Workbench Docs - Alt text

Use the [Workbench Documentation][workbench] to find how to add alternative text to an image.
Type what we need to add to the image in chat when you've found it.

:::::::::::::::::::::::: solution 


We can find how to add alt text in the [Figures section of the Episodes Structure episode](https://carpentries.github.io/sandpaper-docs/episodes.html#figures).
It says we need to include it with curly brackets and `alt=` after the image link.
E.g. `![caption](image){alt='alt text'}`

:::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::::::::::

Now that we know how to add the alt text, I can go make the change in a copy of the lesson.
I'll go ahead and copy the text the issue recommends.
Then I'll go back to the "Code" tab where all the files for the repo are and navigate to `episodes/recipe_instructions.md`

Here is where we want to make the change.
We need to tell GitHub we want to make edits by clicking the pencil icon in the upper right.
If you don't have permissions, it will ask if you want to make a fork. <!--- I think but I can't test it as I have write permissions -->
A fork is your copy of a repository that you have access to and can edit.

In my fork I'll make the change adding `{alt='A bunch of cinnamon rolls in a baking tray in an oven.'}`
after the image link.
I then want to save my changes, to do so in GitHub I have to create a "commit", which is a save with a short message about what changed.
I can click the "Commit Changes" button on the upper right side or type Ctrl/Cmd+s, 
the save keyboard shortcut in most programs.
This will pop up a box to save, the "Commit message" box auto-populates with a message "Update recipe_instructions.Rmd".
That message isn't very descriptive so it won't make for a good message in the history.
I'll instead change it to "Added alt text to image of rolls in oven".
If you need to leave some additional info or a longer message, you can add it to the "Extended description" box.

If you have write access, the most important thing we want to check is that the radio buttons at the bottom is switched
to the option to "Create a **new branch** for this commit and start a pull request".
If we leave the default box to "Commit directly to the `main` branch" it won't start us on the process of suggesting this change back to the official Carpentries repository.
When we click the **new branch** button, it asks us what we want to call the "branch", this is a copy of the repository within our fork.
We can only have one fork but we can have as many branches as we want.
The ability to create many different branches allows us to suggest lots of different changes separately to a lesson.
I'm going to name my branch with the issue it fixes, #4.
Then I'll click the "Propose changes" button in the bottom right.
When you practice this, it probably won't give you the radio buttons but will automatically make a new branch called `patch-1` for you in your fork.

We've now *saved* our suggested changes in our fork and the next page it pulls up for us is to file the "Pull Request"
suggesting that the official repo "pull" in our changes.
We can see the comparison between forks and branches at the top of the page and a display of the differences
between our version and the official version.
Since we are finished with our suggested changes we will click the "Create pull request" button in the 
upper right.

It autofills the title with our commit message but we can edit it or add more info in the "Leave a comment box".
The title is probably okay but one thing we might want to do is *link* our PR with the issue it solves.
We can type "#4" and it will link it to the #4 issue, and it nicely shows us the title of that issues so we can confirm.
Since we know this PR should solve this issue we can add a keyword that will automatically close
the linked issue when our changes are accepted by adding "Fixes" in front of the #4.
Then we will click the "Create pull request" button.

Let's take a look at the PR we just submitted.
It has...

- A tab for discussion
- A tab listing all the commits/saves in our PR
- A tab for checks, which is more for the automated workflows so we will ignore
- A tab that shows the changes, called a "diff" between the official repo and our forked branch

Next, we wait for someone to review our Pull Request.

## Reviewing a PR

::::::::: instructor

Here you should swap to a collaborator screensharing, if possible, so they can review your PR.
Otherwise, you can probably just pretend you are someone different.

::::::::::::::::::::


Now, a reviewer comes in and takes a look at my PR.  They will most likely look at the 
files changed closely.

The reviewer notices that we should mention that these are the uncooked cinnamon rolls in the image.
They could comment in the discussion tab with that suggestion for me to fix.

- Reviewer types "I suggest you update the alt text to mention the rolls are uncooked in this image."

Alternatively, they could "suggest" the change directly.
In the "Files changed" tab, they can click on the "+" sign to the right of the line numbers on the line or lines where they want to make a suggestion.
This pops up the option to make a comment associated specifically with that line.
The reviewer could also have put their comment from the suggestion in this comment box,
then if lots of lines were changed it would be easier for me to find.
To make the change even more directly they can click the icon that has box and a + and a - sign.
This button adds in a suggestion block into the comment.
They can then go and make the change in this block directly.

- Reviewer updates the line to say 'A bunch of **uncooked** cinnamon rolls in a baking tray in an oven.'

The review could put together a bunch of a comments into a review by clicking "Start a review" but since our PR is relatively simple, they will instead click "Add single comment" to submit this issue.

<!--- TODO: callout to mention that they might have to do a review if that is required for merging because the main branch is protected -->

::::::::: instructor

Here you should swap back to the original presenter screensharing.

::::::::::::::::::::

Now I can see the single comment that the review added and even better I can click the "commit suggestion" button
to directly accept their change into my PR.  I'll also update the commit message to say "Adds more detail to alt text"
and then click "commit changes".

Now that suggestion by the reviewer is accepted and the comment is closed as it is outdated,
though someone could expand it if they wanted to see what had been done.
You may now note that the Commits tab has 2 commits.
If we were to check the "Files changed" it would also be updated.

You too can put in suggestions and then accept them if you need to make small changes to your PR based on a reviewer's advice.
This works best for small changes and there is a different way I would suggest using for bigger changes but we won't cover it today.

## Maintainer Accepts Pull Request

Once the review has been completed, the maintainer (or anyone with more access to the repository) can accept our changes and merge the pull request in.  They do this by clicking the "Merge pull request button".  You won't see this button if you don't have access to the repo but I do so I will go ahead and merge it so we can see what happens.

We can see the status of the Pull request changed to "Merged", it is also no longer listed in the Pull Requests tab
at the top of the page.

*What happened with the linked issue?* If we click on the #4 link in the PR it will take us to the issue and 
we can see that the issue is now "Closed".  This automatically happened when we merged the PR since we wrote
that the PR "fixes #4".



::::::::::::::::::::::::::::::::::::: challenge 

## Make a PR yourself

Now you can practice making a Pull Request yourself.

- Go to the etherpad to find which issue you were assigned.
- Comment in the issue that you will be working on submitting a PR
- Use the instructions and try to file a PR with that change
- Ask the instructor questions as you encounter any issues or unexpected behavior.

:::::::::::::::::::::::::::::::::::::::::::::::





[workbench]: https://carpentries.github.io/sandpaper-docs
