---
layout: page
title: remove
nav: true
permalink: /projects/remove
fork: true
---

<span style="color:red;text-align:center;">This project is no longer in active development</span>

remove has been designed along the same path as encrypt. To have a small file size, to be easy and simple to use.

<span style="color:red;">Important:</span> remove (and various other related tools) have, by-and-large, been deprecated by file systems which support file buffering techniques such as [delayed allocation][da], and various methods of [journaling][]. [stegfs][] was born out of a desire to overcome this security risk; if you find stegfs is too extreme for your tastes, perhaps take a look at [LUKS][] for your encrypted partitioning needs.

It has been written in C as to allow the source to be ported to many different operating systems. The standard source download has a simple terminal interface which obviously helps with porting and keeping everything simple and small. A version with a simple GUI is also offered through the help of the GTK. As the GTK has been ported to Windows, Mac OS, and other systems this makes it ideal for keeping remove easily ported to other platforms.

NB: The GUI is still in the early stages of development and is unstable.

remove is ideal to ensure that once you've encrypted your data [[using encrypt ;)]][encrypt], the original plain text is removed completely from your disk. And just as encrypt is portable, so is remove.

To ensure that the data is actually removed and overwritten, remove opens the file at the lowest level and writes out random data. You can tell it how many time to overwrite the original, and once it's finished, the file is then 'deleted' from the filesystem in the normal way.


[da]: http://en.wikipedia.org/wiki/Allocate-on-flush
[journaling]: http://en.wikipedia.org/wiki/Journaling_file_system
[stegfs]: /projects/stegfs
[LUKS]: http://code.google.com/p/cryptsetup/
[encrypt]: /projects/encrypt

*[LUKS]: Linux Unified Key Setup
*[GTK]: Gimp Tool Kit
*[GUI]: Graphical User Interface
