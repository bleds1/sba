---
title: "2025 07 01 How I Take Notes With Org Roam"
date: 2025-07-01T12:47:09+01:00
draft: true
---
# Intro
In the [last post]() I gave a bit of of an overview of my [GTD]() system in [Doom Emacs](). This time I'd like to cover the part of my system that relates to note-taking and [Zettelkasten](). 

# log.org as a home base
I treat it *almost* as a separate system although things are intertwined. Just as with the GTD part most things start with my daily log.org. This place acts as an inbox for almost everything. I can make a note of a task or note an idea for writing. The log is generated and captured to with org-roam-dailies although in one long datetree file rather than the one file per day method org-roam uses by default. My log.org also lives in the same directory as my gtd files; per.org, events.org etc. This means that it get's picked up by org-agenda views if I do put schedule or deadline dates onto a heading. Sometimes I have some todo's living there that I haven't refiled to an other home. 

I probably got into this one long daily journal or log way of working from using outliners like [Logseq]() and [Tana]() One thing I particularly liked about those is that the daily page is the home base for the whole experience. [Obsidian]() also has a way of implementing daily notes as your default startup page. 

This idea fits well with the Zettelkasten system where by you take fleeting notes throughout the day to an inbox of sorts. Perhaps some of these notes will become something useful and many will just hang around or get deleted as temporary and unimportant. 

# My roam directory/file types
~/org/roam/
/articles
/fleeting
/reference
/zk

## Fleeting notes (fleeting)
So this is how my roam directory looks. It takes inspiration from the Zettelkasten system of having Fleeting notes, Reference notes, and a Zettelkasten slipbox (zk). Why do I have a folder for fleeting if the log is the base of all things? well sometimes you are not working in your log. Maybe I capture from somewhere other than Emacs, maybe I scan in a hand written note that has an idea on it? What I tend to do is scan through my log.org for things with the :fleeting: tag and if it something that feels like it could be developed I may refactor it into it's own file here in fleeting.

## Reference notes (reference)
These could be thought of as resource notes in my system. I will clip bits of information and keep things as a reference note. This directory could be thought of as a wiki and often not in my own words. Maybe a link to an article. A quick "How to do so and so" or notes taken from a book or video. Most notes go here.

## Zettelkasten (zk)
These are original thoughts or atomic statements or ideas. Short, snappy and interlinked. 

## Articles (articles)
This folder is for creating output. The idea of having a Zettelkasten system is mostly to create pieces of writing.. to put that thinking or gathered knowledge to some kind of good use. I start writing blog posts in this category.

# Org-Roam UI
One thing I miss from Obsidian is the graph view. People are divided about the graph view, some see no use in it. As a visual person I find it incredibly useful for seeing how notes link and cluster together. Thankfully Emacs users don't need to miss out on that due to the Org-Roam UI package.

Installing ORUI in Doom Emacs

I've found Org-roam-ui to behave much better in Qutebrowser than I have others. Not sure what the reason for that is but I had some strange visual performance issues with Firefox based browsers and Brave - it works great for me in Qutebrowser.
