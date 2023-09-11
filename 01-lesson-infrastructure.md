---
title: "Getting Started with the Carpentries Lesson Infrastructure"
teaching: 30
exercises: 20
---

:::::::::::::::::::::::::::::::::::::: questions 

- How are files/folders in the Carpentries Workbench organized?
- How do I find information on the Carpentries Workbench?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Navigate the Carpentries Workbench Structure
- Look up info in the Workbench docs

::::::::::::::::::::::::::::::::::::::::::::::::


In this lesson we will be using an example repository, created specifically for this lesson.
You will be able to play with it and not be concerned about breaking anything in a real lesson.
The instructor for today's session should share links to the rendered website and the backend repo in chat.

In the first hour we will:

- Explore how lesson pages look and the repositories that make them look that way
- See a demo of what to do when you find a problem with the lesson, both how to report the problem and how to fix it

In the second hour each person here will get the chance to practice fixing an issue in our practice lesson.

:::::::::: instructor

You will need to prepare the repo in advance.
This can be setup automatically using GitHub command line tools.
Be sure you turned on the gh-pages rendering and linked the rendered page in the about section.
Share the rendered webpage and the repo in chat.

Website: <INSERT YOUR LINK HERE>
Repo: <INSERT YOUR LINK HERE>

:::::::::::::::::::::

## Exploring the Website vs. the Repo

The rendered repository may look familiar as all the Carpentries official lessons have webpages use the same infrastructure, the Workbench.
All the lessons are hosted in GitHub, a popular service for sharing repositories, folders with a history using the unix shell software git.
This lesson will focus on working on lesson contributions in the GitHub interface, if you'd like to learn to use
git in the unix shell, please see the [Software Carpentry - Version Control with Git Lesson](https://swcarpentry.github.io/git-novice/).
The webpage we are looking at now is hosted via a repository on GitHub. Let's take a look at it.
You can find it either using the repo link in chat or by scrolling to the bottom of any page of the rendered website
and clicking the "Source Button".

This repository contains the files that tell it what to put on the rendered webpage.

Things the instructor should show here (also show the rendered pages):

- `episodes` folder
- `learners` folder and `setup.md` page
- `instructors` folder

## Workbench documentation

You will become more familiar with the repository part of lessons the more you work with them.
Until then you can use the [Workbench Documentation][workbench] and support from the Carpentries Community.
There is a lot of useful info in the documentation, so it is worth looking over more generally.
I most commonly use the [Episode Structure episode](https://carpentries.github.io/sandpaper-docs/episodes.html)
as it has a lot of info about how to format different elements that go in an episode.

::::::::::::::::::::::::::::::::::::: challenge 

## Workbench Docs - Callout Blocks

A callout block, is a special box type that can go in Carpentries lessons.
They often include info that is optional for the instructor to say to help cut down on the main text.
Use the [Workbench Documentation][workbench] to find how you can add a callout block to a lesson.
Paste in chate the example callout from the documentation.

:::::::::::::::::::::::: solution 


We can find how to add alt text in the [Callout blocks of the Episodes Structure episode](https://carpentries.github.io/sandpaper-docs/episodes.html#callout-blocks).

```markdown
::: callout
This is a callout block. It contains at least three colons
:::
```
:::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::::::::::


[workbench]: https://carpentries.github.io/sandpaper-docs
