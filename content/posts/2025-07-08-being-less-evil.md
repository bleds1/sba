---
title: "Being Less Evil"
date: 2025-07-08T14:18:09+01:00
tags: ['emacs', 'linux']
---

![Image 1](/2025-07-08-being-less-evil/202507091223-emacs-grim.jpg)

Something unexpected has happened. I'm not sure what possessed me to undertake this but I have disabled ['evil-mode'](https://github.com/emacs-evil/evil) in [Doom Emacs](https://github.com/doomemacs/doomemacs). Curiosity I suppose? maybe the chance to learn more about Emacs through understanding it's default behaviours? As a long time evil user I guess I just wanted a little change..

I've used evil-mode/vim keybindings in pretty much all my programs for several years. I got into Emacs because Doom made it accessible to me. This kind of navigation is quite deeply ingrained, so at first did feel like I was committing some kind of blasphemy. 

My first attempt at this admittedly felt uncomfortable. Although there were some behaviours I was enjoying.. jumping from Emacs to my browser, regularly used apps and basic navigation in my window manager felt jarring. Nearly everything on my system was set up to use the evil binds! The context switch was awkward and it was breaking my unified environment. I only lasted 24 hours before re-enabling evil mode.

After a little reflection I realised that I'd not really given it a fair crack of the whip. I made things feel smoother by changing some settings in [Qutebrowser](https://github.com/qutebrowser/qutebrowser) to make navigation feel more 'Emacsy'. Initially as simple as just switching my usual *'h,j,k,l'* navigation to *'C-n', 'C-p'*, *'M-v'*, *'M-p'* etc. I disabled vim navigation keys in my window manager too to bring it inline with this kind of movement. My usual *'Super Q'* to *'quit'* became *'Super K'* to *'Kill'* for example. With a little more consistency across programs I felt ready to make a real go of it.

Disabling evil mode in Doom Emacs is very simple.. just comment out the evil package in *'init.el'*.

``` lisp
;; (evil +everywhere)
```

After a *'doom sync'* on the command line and relaunching I was initially presented with a bunch of errors. My configuration had many references to *'evil'* and *'leader'* keys which I had to comment out for the file to be successfully evaluated. I decided to use this opportunity to remove those and explore the default key-binds. Later I could slowly adapt and reintroduce some of my most used actions. Many of those default Doom keys that where previously mapped to *'leader'* something you will find have changed to *'C-c'* something. Anything evil you set as a custom bind personally will probably need adaptation.

With a few days adjustment I've got to say I'm starting to really like and feel familiar with the default bindings and behaviour. One of my bug bears with evil was that in navigating org buffers, there was some odd behaviour. I mostly write in org-mode with headings and paragraphs. Moving to the next and previous line does not always work as expected. It's tricky to explain.. you can turn on visual line mode to truly treat *'j,k'* as going to the next visual line but that messes up the format and makes every line a bulleted header. I'm sure there are other hacks you could implement but default Emacs *'C-n'*, *'C-p'* behaves exactly as I'd expect. I've also found I like the way *'killing'*, *'marking'* and *'zapping'* works. There's also a few packages I use which don't fully accommodate evil that now feel much more native and natural.

So, I will be continuing with the default bindings. Are there more key presses? ..yes. Is my pinky finger getting a bit more of a workout? ..yep.. but I don't really mind. It makes a nice change to not be hammering the Escape key constantly..I was addicted to doing that.. I'd find myself hammering *'Esc'* for no reason in many other programs too. Is it as efficient as evil? I think it can be, with practice and familiarity, the binds are perhaps not quite as minimal and elegant but it does feels right and well thought out in the Emacs environment. Will I return to evil mode? I wouldn't rule that out either.. but I'm giving default a really good long go and liking it a lot currently.

It's a bit like picking up and learning a new game. You don't know the buttons at first. Slowly but surely, through playing around and experimentation you start to figure out how the game works. Before you know it you're fluid and automatic with the controls and don't even think about it any more.

There's a huge amount of learning materials about out there online but the majority of it is based around the default key-binds. I was feeling a bit like I'd absorbed all the Doom content out there. I'm currently looking at [Mickey Peterson's Mastering Emacs](https://www.masteringemacs.org/) book and watching video content from [Protesilaos](https://protesilaos.com/) and [System Crafters](https://systemcrafters.net/).. there's so many things to learn about Emacs that have just opened up to me.


## Related

[How I use Org-Mode Part One](/posts/2025-06-25-how-i-use-org-mode-part-one/)

[Getting Started with Doom Emacs](/posts/2023-01-27-getting-started-with-doom-emacs/)
