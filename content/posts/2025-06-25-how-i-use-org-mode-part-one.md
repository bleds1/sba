---
title: "How I Use Org Mode Part One"
date: 2025-06-25T11:40:08+01:00
tags: ['emacs','org']
---

Since the last time I wrote about [Org mode](https://orgmode.org/) and my [Doom Emacs](https://github.com/doomemacs/doomemacs) set up I feel like some things will have changed. In fact, who am I kidding.. it's always changing. The basic principles of my [GTD](https://gettingthingsdone.com/) and note taking would be the same anywhere but little things get tweaked and optimized all the time. I think I'm at a good place to record my current process and way of working here. 

## File structure
Currently my org files for GTD and directory look like this;

**~/org**

**archive.org**     - completed todos get refiled to here

**events.org**      - calendar events and appointments

**goals.org**        - long term, midterm, short term goals

**log.org**           - one long file with datetree for daily notes/planning/fleeting thoughts

**na.org**           - tasks relating to a group I am a part of

**per.org**           - personal tasks end up here to be reviewed and executed

**read.org**          - for keeping track of books read or to read.

**someday.org**     - low priority todos I may do one day

**watch.org**        - for keeping track of movies/shows to watch or watched.

**work.org**         - tasks relating to the world of work

## Todo states

![Image 1](/2025-06-25-how-i-use-org-mode-part-one/org-part-one-1.png)

All created tasks have a state, the default being TODO. States can be as follows;

**TODO (t)**          - a task that needs doing
    
**STRT (s)**          - a task that I have started or am working on

**WAIT (w)**          - on hold for now. Put to sleep until I'm ready to do it or delegated, waiting on something
    
**PROJ (p)**          - a project to me is anything that has multiple todos nested beneath to achieve completion

**DONE (d)**          - it's been completed

**CANC (c)**          - these just aren't happening or don't need to be done anymore for whatever reason

I have some slightly modified todo statuses in my *watch.org* and *read.org* files as you can set status on a file by file basis. I don't think we need to go into that here but I use things like WATC or READ instead of the usual TODO. 
```lisp
(setq! org-todo-keywords
      '((sequence
         "TODO(t)"
         "STRT(s!)"
         "WAIT(w!)"
         "PROJ(p)"
         "|"
         "DONE(d!)"
         "CANC(c!)" )))
(setq! org-todo-keyword-faces
      '(("TODO" :foreground "#cc4d3e" :weight bold)
       ("STRT" :foreground "#85C7A1" :weight bold)
       ("WAIT" :foreground "#83898d" :weight bold)
       ("PROJ" :foreground "#896ccc" :weight bold)
       ("DONE" :foreground "#2b8c63" :weight bold)
       ("CANC" :foreground "#5d6265" :weight bold))))
```

## Tags and Priorities

![Image 2](/2025-06-25-how-i-use-org-mode-part-one/org-part-one-2.png)

I try to keep my tags for these todo's quite limited but the first area I think about it priority. Priorities are a little odd in org. By default it's a system where you can mark things as A,B,C priority. When searching for tasks every un-prioritised todo defaults to B which I'm not keen on. One approach we can take to deal with that is to give every single task an A,B or C priority. Another way is a shift in thinking -  sometimes I just think of it as the next 3 things I'm going to do.. Do A, then B, then C. These priorities are set very easily with shift up and down.

![Image 3](/2025-06-25-how-i-use-org-mode-part-one/org-part-one-3.png)

```lisp
(after! org
  (setq org-tag-alist
        '(
             ("@call")
             ("@email")
             ("@errand")
             ("@games")
             ("@home")
             ("@listen")
             ("@post")
             ("@read")
             ("@research")
             ("@sys")
             ("@watch")
             ("@web")
             ("per")
             ("na")
             ("work")
             ("fleeting")
             ("posted")
             ("refile")
             ("recur")
               ))
```

These are my current tags I use for todos and fleeting thoughts. The ones beginning with *@* symbol are contexts. So, say I am working on domestic tasks around the house I can filter things down by searching for the *@home* tag. If I'm working at my computer (system) I can pull up the *@sys* tagged tasks.

## Org capture templates

![Image 4](/2025-06-25-how-i-use-org-mode-part-one/org-part-one-4.png)

Capturing new tasks is fast and easy using org-capture-templates. A dialogue for more specific org-capture will pop up with *'C-c-c' or F6*

The options I'm presented with there are;

**Todo (t)**

**-(p) Personal**      - add a new todo to *per.org* under the heading *"INBOX:"*

**-(n) NA**               - add a new todo to *work.org* under the heading *"INBOX:"*

**-(w) Work**          - add a new todo to *work.org* under the heading *"INBOX:"*

**-(d) Done**            - add some task immediately with DONE status to *archive.org*. This is for things that come up and get completed that are not already in the system. By logging these they show the time they got completed on agenda views.

**Event (e)**              - add an entry to *event.org*. This file is synced with org-cal-dav so appointments show up everywhere I access my calendar.

**Watch (w)**

**-(t) To Watch**      - films or shows I want to watch added to *watch.org*

**-(d) Watched**       - when I watch something it gets logged as done with timestamp that shows on agenda views

**Planning (p)**

**-(p) Day Plan**       - add a quick checklist to my *log.org* (Primary Objectives for the day)

**-(r) End of day review** - A few questions for EOD, What did I get done? what will I do next? etc. I don't use as often as I should. I tend to use the following more consistently.

**-(w) End of week review** - Same as above but with regards to the whole week

```lisp
(after! org
  (setq! org-capture-templates

        '(
          ("t" " Todo")
          ("tp" "󰭕 Personal" entry (file+headline "~/org/per.org" "INBOX:")
            (file "~/org/tpl/tpl-todo.txt"))

           ("tn" " NA" entry (file+headline "~/org/na.org" "INBOX:")
            (file "~/org/tpl/tpl-todo.txt"))

           ("tw" " Work" entry (file+headline "~/org/work.org" "INBOX:")
            (file "~/org/tpl/tpl-todo.txt"))

           ("td" " Done" entry (file "~/org/archive.org")
             (file "~/org/tpl/tpl-done.txt"))

           ("e" " Event" entry (file "~/org/events.org")
             "* %? \n %^t")

          ("w" " Watch")
           ("wt" "󰿎 To Watch" entry (file+headline "~/org/watch.org" "TO WATCH:")
            (file "~/org/tpl/tpl-towatch.txt"))

           ("wd" "󰎁 Watched" entry (file+headline "~/org/watch.org" "WATCHED:")
            (file "~/org/tpl/tpl-watched.txt") :prepend t)

           ("p" " Plan")
           ("pd" "󰃶 Daily Plan" plain (file "~/org/log.org")
            (file "~/org/tpl/tpl-bod.txt"))

           ("pr" "󰱄 Daily Review" plain (file "~/org/log.org")
            (file "~/org/tpl/tpl-eod.txt"))

           ("pw" "󱛡 Weekly Review" plain (file "~/org/log.org")
            (file "~/org/tpl/tpl-weekly.txt"))
            )
           ))
```

Most thoughts throughout the day will be captured to my journal *log.org*. Tasks will be captured to the relevant todo file for refiling, tagging, scheduling and organisation. Each todo file (*personal/na/work*) has the following headings *INBOX:* and *NEXT:*. *INBOX* is where things sit until they have been prioritised, scheduled or tagged, by default they have one tag *:refile:* inherited from the heading making them easy to locate from agenda views. They get queued up under the *NEXT:* heading suggesting the order I want to complete things in. An agenda view search for the *:refile:* tag is then a unified inbox where I can sort tasks across the different areas.

## Agenda views

![Image 5](/2025-06-25-how-i-use-org-mode-part-one/org-part-one-5.png)

I don't go to crazy with these. *C-c-TAB* brings up my default agenda view. A timeline of the current day that shows both events and scheduled tasks or deadlines. I leave the agenda view open and sticky in the background and have set up a key to toggle back and forth from whatever file I'm in with *C-c 9*
```lisp
;; Note this keybind requires that the agenda is already open in the background or it will just go to an empty buffer
(global-set-key (kbd "C-c 9") (lambda ()
                              (interactive)
                              (if (string= (buffer-name) "*Org Agenda*") (previous-buffer) (switch-to-buffer "*Org Agenda*"))))
```

## The daily log.org

![Image 6](/2025-06-25-how-i-use-org-mode-part-one/org-part-one-6.png)

My main go to file during the day is my *log.org*. It's one long file that uses org-roam-dailies to create a date-tree journal with timestamped entries.
```lisp
;; Capture template for my daily log entries
(setq org-roam-dailies-capture-templates
      '(("d" "default" entry
         "* %<%H:%M> %?"
         :target (file+datetree "log.org" week)))
      )
```

I have a keyboard shortcut that can quick capture an entry to the log from anywhere throughout the day. The default *'org-roam-dailies'* create a separate file for each day and I started to find that counter productive. I would rarely ever look back on the individual files. With one long log I can quickly scan back over the past few days or weeks and information stays fresh unless I decide to fold a heading away or narrow the buffer to just today's date. Sometimes I create a little check list here at the beginning of the day for my main objectives, often I just ramble and capture fleeting thoughts throughout the day.

```lisp
;; Keyboard shortcut to get to my daily log on today's date
(global-set-key (kbd "C-c d") 'org-roam-dailies-goto-today)
;; Alternative that uses leader key. Space d.
(map! :leader
      :desc "org-roam-dailies-goto-today"
      "d" #'org-roam-dailies-goto-today)
```

That covers the basic foundation of my system in org mode. I hope this starts to show why no other app or text editor comes close for me. Being able to have my notes, journal, tasks and calendar all under the one roof whilst also being able to navigate my entire file system with Vim keybindings in Emacs is very efficient and endlessly customizable. We're barely even scratching the surface of all the things Emacs is capable of here.

I keep my org-files in sync with my mobile with [Syncthing](https://syncthing.net/) and access them there for some basic editing with [Orgro](https://orgro.org/). Of course we don't have all the features of Emacs there but I can quickly take a few notes to one of my files if needs be. My calendar events in *events.org* sync with [org-cal-dav](https://github.com/dengste/org-caldav/blob/master/doc/org-caldav.org) to the [Fossify Calendar](https://www.fossify.org/) app with [Davx5](https://www.davx5.com/). 

A big part of my system not mentioned here is that I folders related to note-taking with [Org-Roam](https://www.orgroam.com/). I feel my [Zettelkasten](https://zettelkasten.de/introduction/) system is a separate one to my GTD related things although there can be some cross-over.

If you want to dive into my full messy [Doom Emacs config](https://github.com/bleds1/dotfiles/tree/main/.doom.d) then you can find my dotfiles [here on Github](https://github.com/bleds1).. I push changes quite often and I will discussing my Org-Roam note taking system in a future post.

## Related

[Getting Started with Doom Emacs](/posts/2023-01-27-getting-started-with-doom-emacs/)

[How to install Doom Emacs on Termux](/posts/2023-07-23-how-to-install-doom-emacs-on-termux/)
