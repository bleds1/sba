---
title: "Image previews in lf with sixel and chafa"
date: 2025-03-26T11:55:25Z
tags: ['linux','lf']
---

![Image 1](/2025-03-26-image-previews-in-lf-file-manager/screenshot1.png)

Despite swearing by [ranger](https://github.com/ranger/ranger) for quite a few years I am a recent convert to the very similar [lf file manager](https://github.com/gokcehan/lf). It just feels a little lighter, faster and simpler and lets me fly around my system super fast. Today I finally got image previews working and very nicely too. I can do away with Ranger and the no longer maintained [ueberzug](https://github.com/seebye/ueberzug) for terminal image previews.

The answer for me was that I needed to install [chafa](https://github.com/hpjansson/chafa). You may also need to install libsixel - I already had this installed so maybe go look into that. We need to make a previewer script that uses chafa for pictures and bat when it's text/not an image file. [bat](https://github.com/sharkdp/bat) gives you nicely coloured previews of text files with syntax highlighting. I'm using the [foot terminal](https://codeberg.org/dnkl/foot) on Wayland in [hyprland](https://hyprland.org/) and on Arch Linux. If you want to implement it this way you will need to use a terminal with [sixel support](https://www.arewesixelyet.com/)

![Image 2](/2025-03-26-image-previews-in-lf-file-manager/screenshot2.png)

Feel free to use this code below or check out my dotfiles repo on [GitHub](https://github.com/bleds1/dotfiles)

First up install chafa via your package manager. On Arch Linux you should find this in the regular repos. Installation may vary on different distros.

```sh
    sudo pacman -S chafa
```

Next up create a bash script. I've called it pv.sh but name it as you like. It can be placed in any directory so long as you include it's full path in your lf config. I keep my scripts in a *~/.scripts* folder or sometimes in *~/.local/bin*

```sh
    #!/bin/sh
    # use chafa/sixel to preview images in lf. If it's not an image use bat with colour
    # chmod +x on the command line to make the script executable.

    case "$(file -Lb --mime-type -- "$1")" in
        image/*)
            chafa -f sixel -s "$2x$3" --animate off --polite on "$1"
            exit 1
            ;;
        *)
            bat --color=always --style="numbers,snip" "$1"
            ;;
    esac
```

Now in your lf config *(~/.config/lfrc)* you will need the following options set. Save and launch a new instance of lf and you should be in business.

```sh
    set preview true
    set previewer ~/.config/lf/pv.sh #full path the above script
    set sixel true
```

## Related Posts

[Significantly reduce video file size with ffmpeg](/posts/2025-03-23-significantly-reduce-video-size-with-ffmpeg/)


[Getting Started with Doom Emacs](/posts/2023-01-27-getting-started-with-doom-emacs/)
