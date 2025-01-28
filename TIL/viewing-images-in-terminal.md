---
title: "Viewing images in the terminal"
author: "Deven Mistry"
date: "2024-10-24"
categories: [c,cpp,rust,terminal]
---

The ability to view images in a terminal is a very handy skill. I recently ran into this issue when I was working on a project which had over a million images on a network drive.

The problem became a complex one to solve as even running a mere `ls` command was not an option on the network drive.

Firing up a jupyter notebook server everytime to view an image was not a feasible option. And there had to be a better way.

Upon some searching I found some popular options

1. [feh](https://github.com/derf/feh)
2. [TerminalImageViewer](https://github.com/stefanhaustein/TerminalImageViewer) (tiv)
3. [Viu](https://github.com/atanunq/viu)

In my use case, the best one which worked the best in my use case was `viu` because of its support for jpgs.
