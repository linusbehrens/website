---
title: Linux and what it means
author: "Linus Behrens"
date: 2024-09-05T15:37:19+02:00
tags: ['tech', 'os']
header: "/header/linux.jpg"
---

# Why GNU/Linux


> This is the Unix philosophy: Write programs that do one thing and do it well. Write programs to work together. Write programs to handle text streams, because that is a univeRsal interface
> 
> *- Doug McIlroy, the inventor of Unix pipes and one of the founders of the Unix tradition*


Linux at its core is the idea of intercompatability born in the body of a kernel. What I love in Linux is not how fast and free it is. Not how amazingly many people contribute to one goal. It is the way I use it and how it allowed me to fit the most bare bones software to my needs.

## Examples for the perfect fit

My senior high note taking setup is pretty complex. However it does fit my workflow perfectly.

- [neovim](/posts/neovim) note taking
- [\tex](posts/tex) for long-term sheets
- [markdown](posts/markdown) for short-term notes in lessons
- pandoc turns markdown into `\tex`
- telescope and todo-comments for todo lists
- [anki](posts/anki) for everyday learning
- github for backing up and syncing my data (homelab in the future)


With that setup I am albe to quickly make notes in my lessons as well as clearly structure my long-term sheets. With having anki on any of my devices I am able to learn everywhere.

If I want I could even run all of that over ssh from a homelab of server at school.

## Intercompatability 

My shell runs in [alacritty](https://github.com/alacritty/alacritty) (macOS) and [st](https://st.suckless.org/) (arch and void). My most used and centered tool is [neovim](/posts/neovim). With my configuration it is beautiful and works seemlesly. With telescope I quickly open my `<subject>.refile.md` note and later the week I convert it to `<subject.refile.tex` with pandoc. The important information gets refiled into `<subject>.tex` and tagged as `ANKI: <subject>`. 
So if I open telescope to see my todos the anki sign reminds me of entering the information to my `anki deck`.
Every evening I push my files to github to be safe for a data loss.

## Options (example distributions)

The following are distros I have used.

- Manjaro (Why does it exists exactly)
- Mint (If you would want to cheat)
- [Arch](/content/arch.md) (Amazing documentation, pacman, AUR)
- Arco (No systemd arch)
- Gentoo (If you want it you know it)
- Void (small, but no systemd!)

On my **x61s ThinkPad** I run Arch Linux. It is light weight and has amazing documentary. The arch wiki is one of the best documents and I even refer to it to non specific arch users.

The **2013 Mac mini** runs void linux. Not because I don't like arch as much, but because after inserting a bootable usb and entering grubs "install arch for x86_64" I got a black screen for days. I choose void because I liked the neofetch batch and because it has no `systemd` elevating the performence and reducing drama. I mainly use that mashine as a ssh server.

Both mashines run [suckless software](https://www.suckless.org). Namely `dwm`, `dmenu`, and `st`. I am really happy with how good it works, but I do not feel well using `X`.

My **MacBook** runs macOS because Asahi sucks at the moment. However I use the tiling window manager `yabaii` and [alacritty](https://github.com/alacritty/alacritty) to come closer to a linux experience.

