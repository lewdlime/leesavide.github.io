---
layout: post
title: "Mac OS X Maintenance"
category: "blog"
---

#### Terminal Speedup
If the terminal or iTerm2 is starting slowly, use this command when the terminal does start to help speed it up:

	sudo rm -rf /private/var/log/asl/*.asl
This will also speed up MacVim / Vim, on occasion.

#### "OH GOD, WHERE DID MY DRIVE SPACE GO"
The El Capitan update brought some rather unwelcome changes, and along with them, restricting access to folders, even from root access, is one of them. Because of this, a very noticible side effect of this is that apps that originally cached data to folders they now cannot access will instead cache data to `/private/var/folders/`. Unfortunately, this can cause a massive slowdown to everything running, and also eats up 30 to 40 gigabytes of disk space. Whether this is a side effect from running certain apps, or some system task that needs patching, I'm not sure. But the quick fix for now is to run this command to regain the disk space:

	sudo rm -r -P /private/var/folders/tr/*
**Warning**: Running this command basically clears the cache of everything that's running on your Mac. It's not uncommon to see things like having to re enter passwords in Google Chrome / Firefox or reset apps with specific settings. I am not responsible for data loss, should you choose to run this. I ran this as a guinea pig for testing it, and that was the only noticeable mishap it would cause. But for the benefit of instantly speeding up performance, I am very willing to re apply lost settings.

#### Mac OS X Environment Variables [^1]

While there are many guides on how to set and edit Mac OS X environment variables, there are some programs that add variables to your
`$PATH` in Mac OS X that normally don't even notify that they've changed the variable, simply because they expect to be needed,
or because other programs won't function without them available. Regardless, while you *could* use `~/.MacOSX/environment.plist`, `~/.bashrc`, or `~/.profile`, you should also be aware of the `/etc/paths` & `/etc/paths.d/` entries. These are simply text files with listings of directories, one per line, to append to the  existing `$PATH` variable, like a "`pathrc`", in a way. It's common to forget that Mac OS X is still a port of UNIX to some degree. This is simply one of the many parts of UNIX that is present in Mac OS X.

I noticed that my `$PATH` was a bit cluttered and unnessessarily long when I ran `echo $PATH`, seeing locations that didn't exist and
programs that I've either removed or updated. From what I can tell, this happens in both Mac OS X and most ports of Linux, except Apple does't even mention it in their
[documentation][^2] when explaining how to set environment variables. If you notice anything strange in your `$PATH`, be sure to run

	sudo vi /etc/paths /etc/paths.d/*
 and make sure the entries are all for programs you do need in your path, and not just duplicates or [dead entries][^3].


[^1]: This serves both as a guide and as a self-reminder about this particular property of Mac OS X.

[^2]: <https://developer.apple.com/library/mac/documentation/MacOSX/Conceptual/BPRuntimeConfig/Articles/EnvironmentVars.html>

[^3]: Having a long `$PATH` with locations that don't exist can slow down the time it takes for the Terminal app to start. I removed the dead entries and noticed an immediate change when I ran the Terminal again.