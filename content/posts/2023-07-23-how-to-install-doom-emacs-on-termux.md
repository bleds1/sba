---
title: "How to Install Doom Emacs on Termux"
date: 2023-07-23T15:00:18+01:00
tags: ['emacs','android']
---

![Image 1](/2023-07-23-how-to-install-doom-emacs-on-termux/2023-07-23-doom-emacs-termux-screenshot.png)

I used to think having Emacs on a phone was a bit much..but recently I've just started using Emacs and Org mode for nearly everything.. There's not a great selection of apps on Android for accessing Org files, the best solution to me was to just get Emacs with it's fully fledged Org on mobile. The newish GUI Android Emacs app is a bit strange and I swiftly uninstalled it. The Termux terminal version however, works much better. There's not a whole load of info out there about how to run Doom Emacs on Termux but I managed to figure it out and have been impressed with how well it works. I'm not a *massive* phone user and do the bulk of stuff on a laptop but It is pretty nice to be able to view my Org agenda or add something quick to my daily note from mobile. I'm also a big fan of just launching into a blank "*scratch*" buffer to do any writing, drafting or quick capture.

**1.  Install Emacs on Termux**

If you don't have Termux already, bookmark this post and get yourself set up with that from F-Droid. You may want to get to know it a little before getting into this stuff. When you're ready for Emacs then..

```sh
    pkg install emacs
```

**2.  Install dependencies**

It's possible you might be asked for some others depending on what you already have in your Termux installation.

```sh
    pkg install gh fd ripgrep
```

**3.  Install Doom**

You'll need to do things a bit differently from the usual install instructions on Github as Termux Emacs uses different directories..
```sh
    git clone --depth 1 https://github.com/doomemacs/doomemacs ~/.emacs.d
    
    ~/.emacs.d/bin/doom install
```

**4.  Setup your config files (config.el packages.el init.el)**

If you already have a config file on desktop I'd suggest rather than just dumping the whole thing into Termux, you take it chunk by chunk. The default included config is pretty much good to go if you haven't used Doom before. Start with your basic settings and introduce elements to it gradually and make sure it works at each step with a doom sync or doom/reload. If you have a really complicated set up you may run into things that don&rsquo;t work on mobile but I was surprised at how much works perfectly. Maybe you want to set up some slightly simpler keybinds in the mobile environment or live without certain packages. For example I haven&rsquo;t yet dared install the Org-Roam package on mobile as I'm worried about conflicting database issues. I can still access and edit all those .org notes however and that's totally enough for me.

**5.  Set up some convienient aliases**

Adding something like this to your shell config can save a few keypresses on that fiddly litte keyboard. I use zsh so in my .zshrc I have..
```sh
    alias doomsync="~/.emacs.d/bin/doom sync"
    alias emd="emacs --daemon"
    alias em="emacsclient -nw"
```

You'll want to doom sync on the command line after adding any new packages. With most changes to config.el you can just hot reload "SPC-h-r-r" or "M-x doom/reload" and you should see your configuration changes.

**6.  Bonus**

**Termux Extras**
If you install some Termux extras - API and widgets. You can just set up a script which acts as a home screen app launcher with a custom icon. Install both from F-Droid, also install termux-api in Termux.
```sh
    pkg install termux-api
```

**Vterm**
The Vterm pop up terminal is pretty useful in Termux because of the lack of screen space. I didn't expect it to work but it totally does. Uncomment it in packages.el, exit and doom sync. When you try to open it Doom will let you know it needs to compile the package so you'll need the following build dependencies.
```sh
    pkg install cmake libvterm
```

**Keeping files in sync**
I use Dropbox with Dropsync because the official Dropbox app on Android is weird and won&rsquo;t let you store the directory offline on your device.. Syncthing would be another option to use here but you will only be able sync your files on a local wifi.

That's about it for now. This should be enough to get you up and running. Enjoy your tiny little Emacs.


# Links

[Doom Emacs Github](https://github.com/doomemacs/doomemacs)

[Termux Github](https://github.com/termux/termux-app)

[Termux on F-Droid](https://f-droid.org/packages/com.termux/)

## Related Posts

[Getting Started with Doom Emacs](/posts/2023-01-27-getting-started-with-doom-emacs/)
