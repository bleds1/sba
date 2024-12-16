---
title: "Trying out the Zed editor"
date: 2024-10-27T12:36:01Z
tags: ['writing','tech']
draft: true
---

## What is Zed editor?
 - [Zed]() is a fairly new code or text editor on the block. Cool name right?
 - It's written in [Rust]() and claims to be fast and light with an emphasis on using AI and collaborative features.
  - I'll be straight with you though - I have no interest in the AI features or collaboration tools. I'm not a programmer, I just tinker around with my computers configuration files and theming etc and work on some basic code for my website. I usually use Emacs or Neovim for that purpose.
- Why would you want to try it?
 - I kind of believe that you should have a terminal based and a GUI based solution for doing the same tasks on your system. I recently moved to the Gnome desktop environment and there's a kind of polish and unified look to that which has led to me investigating more GUI based solutions that fit nicely into my system. My first though on seeing Zed was - that looks pretty, let's give it a spin as my default text editor

## How to install Zed
 - The Linux version only came out a couple of months ago, you can get in MacOS but Windows users will have to wait.
 - On Arch Linux you can find Zed in the main repositories. See their [documentation]() for alternative installation methods.

 ```sh
 sudo pacman -S zed
 ```

## First launch
 - You can launch zed in the way you usually launch programs
  - On first launch you will see a little pop up that asks for a few default options. You can opt in or out of telemetry, set a theme and change your base keymap type here. You can also enable Vim mode here or set it later.
  - Enable cli
   - One of the first things you may want to do it is enable cli access so you can launch the editor in the terminal. You can do this in the graphical menu or through the control panel searching for cli::install
  - Accessing the Control pallette
   - The idea of a control or command pallette will be familiar to some from other programs and can be activated with Ctrl+Shift+p.
   - So now in the terminal you will be able to type

   ```sh
   zeditor ~/myproject
   ```
   to open a directory as a project
   or

   ```sh
   zeditor myfile.txt
   ```
   to open a single file
    -
  - Set an alias
   - The first thing I thought here was "no way am I typing zeditor everytime" and promptly headed to my bash alias and set

   ```sh
   alias z="zeditor"

   ```
   So I can instead just..

   ```sh
   z myfile
   ```

   ```sh
   z ~/myproject
   ```

## Basic settings
   - I was impressed with the amount and quality of the themes installed my default. You'll probably be able to find something you like in there but if not you can search extensions or [](https://zedthemes.com) to find more. I wanted mine to feel at home in my Gnome environment so installed on called 'Adwaita Pastel' that I think looks pretty smart.
  - Installing extensions
   - search for extensions in the command pallette. This eco system of plugins/extensions seems to mostly consist of themes right now but is an understandable as a fairly young editor. I would expect to see this grow quite rapidly.
  - Access the settings
   - Your going to want to tweak some settings to your liking. Access the settings file with Ctrl , or by using the command pallette and settings. This will open the .json file - you should see some things you already set through using the graphical ui already if you changed theme or disabled telemetry for example. You can add a comma to a line and continue to add more options here.
  - Access the keybinds
   - The other file you may want to edit regularly is the keymap.json. Search keymap in the command pallette or access directly with the keybind (for me this is Ctrl k Ctrl S)
- Hiding or disabling things
 - One of the first things I think about it getting the editor to look the way I want. As I said I'm not interested in the collaborative, co-pilot stuff and I wanted to hide the icons for those. The following code should help with hiding, showing or moving things into different parts of the UI.
- Some settings & keybinds
 - I need Vim mode and have a set of keybinds that are automatic for me in both Neovim and Doom Emacs. Basic stuff like saving a file. I'm particularly addicted to space f s. I'm really happy you can implement these kind of leader key, key chords. Find more happy defaults for me personally below. One area I haven't sorted out yet is my keybinds for splits and navigating splits. This is just because I've been using the regular tabbed mode primarily and not really seen the need for it yet.
- Some things I like
  - speed
  - Looks
   - I think it looks great, it's not clutters and helps you just focus on the text. Rounded corners in the Gnome, Adwaita environment feels almost native and fits nicely.
  - Markdown previews
   - The majority of my writing, note taking and blog work is in the markdown format. The Markdown mode feels nice to write in. Being able to generate a live preview in another tab or a split works really well.
  - Project search
   - This is essential to me for example I made need to find and replace a word across a whole bunch of folders in my website or search for a mention of something in my Zettelkasten notes. Sure you can grep and stuff but I find this kind of task nice to do in a GUI and search and search across projects is implemented well.

## Improvements I'd like to see
  - as a markdown editor [Obsidian]() and [Emacs]() still feel more featureful
   - I'd like to see a few more features for pure writing. A word count feature, spell checking in non code files. Some kind of zen mode that puts you into a pure clean writing state. It's those kind of features that could lead to me choosing to use something else..
   - You can go fullscreen and use the centered mode which works quite nicely for me. One things I'd like to be able to do is disable line numbers only in markdown mode. That's something I can achieve in other editors.
  - Understandably Zed's focus is coding but it's competitors do this well. I imagine these kind of things may appear in the form of extensions at some point.
  - Option to hide the co-pilot sign in
   - Being able to hide the icons for these features is a good start but that's not actually deactivating it's functionality. We can't get rid of that sign in button at the top and it seems the devs have no interest in making it a possibility.
  - More extensions
   - Zed is still a young editor and I expect as the extensions ecosystem grows we may see more features that we have grown accustomed to from other editors.

   ## Conclusion
 - Zed is a very good editor, I love it's simplicity, speed and it just feels good to work in.
 - If the emphasis on AI and collaboration is something holding you back don't worry you can work around those features and never login or connect to such things. If you want a code editor something akin to VSCode/or Codium without the bloat that comes with it. Zed feels more light and fast and more like Sublime Text really.
 I'm trialling it as my default editor but there are still some things I would prefer to use Emacs for as primarily a writer. It may be that I've still not discovered many features - it would only be fair to keep using it as my default for a while and see how it develops.
 - Let me know what you think? How are you finding Zed?


 ## Related

 [Doom Emacs Post]()

 ## Links

 [Zed website]()

 [zedthemes]()
