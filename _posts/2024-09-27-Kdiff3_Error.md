---
layout: post
title: "Windows KDiff3 Error: "Opening of these files failed... Unknown error."
date: 2024-09-27 00:00:00 +1200
categories: windows tools
---
# Windows KDiff3 Error: "Opening of these files failed... Unknown error.

KDiff3 is my tool of choice for 3 way merge. It is unobtrusive, easy to learn and has good shortcuts.

I use it on Windows as well, and I have never had any issues until I was forced to use Windows 11 on my work machine and then attempted to do a 3 way merge. 

I received this error:

'Opening of these files failed: [filename] Opening [filename] failed. Unknown error'. 

(Which is also documented here: https://bbs.archlinux.org/viewtopic.php?id=295528)

You can work around this error by closing the dialogs that appear (you won't see any files diffed), and then instead of closing KDE, choose "Open" and the open dialog will be prepopulated with the folder paths.

- 
I checked the version, it was very much up to date.

I am not sure why, but I had a suspicion this was related to how KDiff3 was installed. In an effort to spend less time looking at setup wizards, I had downloaded most of my tools via winget.

## How to resolve KDiff3 opening files error
I simply uninstalled KDiff3 using Winget, I then [downloaded KDiff3 for Windows from the official KDE mirror.](https://download.kde.org/stable/kdiff3/)

When installing, I made sure to select "install for all users" instead of single user. 

After changing my difftool and mergetool path in git from AppData to Program Files, KDiff3 started working immediately.