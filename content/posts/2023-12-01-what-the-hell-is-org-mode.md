---
title: "What the Hell Is Org Mode?"
date: 2023-12-01T18:05:18Z
tags: ['emacs']
---


So what is it? Let me introduce you because of course, there's far too much to cover in one post. I would like to get into the more advanced stuff ideally. One of the things that annoys me is that there are a ton of _"Getting Started with the Basics"_ types posts and videos and not enough that go deeper into the features. It feels like I've absorbed a lot of the content that's out there, however..it only feels right to start with the basics and then build on top of that.

## Org is a language

[Org-mode](https://orgmode.org/) can do a lot of cool things. At it's core Org is a plain text, Markdown type language. It has a slightly different but familiiar syntax to [Markdown](https://www.markdownguide.org/getting-started/) that straps on a ton of very useful features for organization and productivity. I've seen it referred to as 'Org-down'. Many will be familiar with the idea of plain text, most of our text entry to the internet or through are phones is usually in plain text with  no special formatting . Most will also be aware of the Rich Text Format (.rft). You may have come across this is in your text editor of choice, writing an email, and certain other places where you have to write posts with more formatting. We might have options in a toolbar for Bold, Italics, Headings, Colours, Alignment etc. Markdown (.md) is a form of plain text with symbols that can be used to enhance the formatting when we publish text.

For example in Markdown..
```markdown
# This is a level 1 heading

## This is a second level heading

*Bold*
_Italics_
```

and in Org..
```org
* This is a level 1 heading

** This is a second level heading

*Bold*
/Italics/
```

## Org as an outliner

Org has the functionality of an Outliner. You may have seen something similar in apps such as [Logseq](https://logseq.com/) or [Roam Research](https://roamresearch.com/). Headings or bullet points are treated as seperate nodes or blocks that can be rearranged, indented, folded or given a hierarchy. If you've never written in this way, maybe try it out? Here's an example use case; you could keep one super long journal file with headings for each day. When you are working on today's entry every other heading can be folded and hidden away. Each note you make throughout the day could be a time stamped bullet-point that you give your entire focus to. Outliners are also particularly useful when writing long texts like a book or a literate configuration file with many sections.

(_Org headings in a journal file_)

![Org headings Screenshot](/2023-12-01-what-the-hell-is-org-mode/2023-12-01-1829-org-headings-screenshot.png)

(_Org headings folded with [TAB]_)

![Org headings Screenshot 2](/2023-12-01-what-the-hell-is-org-mode/2023-12-01-1829-org-headings-screenshot-2.png)

## Org in Emacs

Org-mode is not exclusive to use in [Emacs](https://www.gnu.org/software/emacs/) but it is one of the built in major-modes. Other text editors may be able to open and edit .org files but we wouldn't be even scratching the surface of it's powers. Emacs is modal, I could be in Markdown-mode, Lisp-mode or Org-mode and the text entered will display the properties, features and highlighting for the corresponding syntax.

With Org we are able to add key words to headings i.e TODO, DOING and mark things DONE or LATER. You can set scheduled or deadline date properties, start timers on headings. This means you can have a fully functioning task management/note taking system, a journal, calendar, make a personal wiki and much more. All of this functionality in a lightweight free to use open source text based editor that's been around for 40+ years. No sign up, cloud based account or subscriptions here - just a little bit of a learning curve.

```org
* TODO Post a blog
* NEXT Buy an Onion
* WAITING Establish world peace
* DONE Run 5km
```

## The benefits of plain text

The great thing about keeping your life in plain text is that it's reasonably future proof. With Org and Emacs you are in control of your files & information. Services like Evernote, Notion, maybe one of Microsoft or Google's offerings - they have hold of your data, online in proprietary file formats that cannot transcend their medium. Org files may be lesser known but it's just text and with a press of a few key-binds you can export to a variety of familiar file formats e.g (.pdf, .html, odt., .md, .txt).

There are some great apps out there that respect local first and I feel it's worth mentioning that I'm also a big fan of [Obsidian](https://obsidian.md/). The thing with Obsidian is that it only works with Markdown files. With Emacs I can navigate the entire file system of my computer and a variety of files and project types. Because everything is plain-text it's lightning fast even on an old potato computer.

(_Org Export Dispatch Menu [SPC-m-e]_)

![Org-export Screenshot](/2023-12-01-what-the-hell-is-org-mode/2023-12-01-1829-org-export-screenshot.png)

## Three nice features of Org-mode

This post is intended to be a primer for my Emacs/Org-mode series. I've previously discussed getting started with [Doom Emacs](/posts/2023-01-27-getting-started-with-doom-emacs/) and I'll dive a bit deeper in future posts. There are many great features but some of my favourites I'd like to cover are;

*Quick capture templates* - Add notes, tasks, bookmarks, links etc. with custom key-binds. I type SPC-n-n (in my mind that's new note) to activate quick capture and am presented with a series of options t = todo item j = new timestamped journal entry e = an event for my agenda r = add something to my reading list etc.

(_Org Capture Menu [SPC-n-n]_)

![Org-export Screenshot-2](/2023-12-01-what-the-hell-is-org-mode/2023-12-01-1829-org-export-screenshot-2.png)

*Task management* - I keep my tasks in an org file called todo.org. These entries have different properties e.g TODO, NEXT, SOMEDAY, WAITING. I can open org-agenda (a calendar view) and see deadlines and what is on the schedule for the day, week etc.

*Personal Knowledge Management* - A digital notetaking system.. How to keep something akin to a [Zettelkasten](https://zettelkasten.de/posts/overview/) to manage Fleeting, Literature and Permanent notes.

Did I mention I can write and code for this website, read emails, books, news feeds, browse the web and view images? Hopefully this serves as a nice intro to Org/and or Emacs and maybe you can start to see how with all this under one roof you might be able to construct quite a powerful way of working. 


### Related 

[Getting Started with Doom Emacs](/posts/2023-01-27-getting-started-with-doom-emacs/)

[How to install Doom Emacs on Termux](/posts/2023-07-23-how-to-install-doom-emacs-on-termux/)

### Resources

[The Org-mode Manual](https://orgmode.org/org.html)

[Org Mode - Your Life in Plain Text](https://orgmode.org/)
