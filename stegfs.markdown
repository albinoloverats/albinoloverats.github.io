---
layout: page
title: stegfs
nav: true
permalink: /projects/stegfs
fork: true
---

stegfs is a steganographic file system in userspace which uses the [FUSE][] library. Steganographic file systems are one step ahead of (or beyond) traditional encrypted file systems as they aim to grant the user plausible deniability of the files within. The way that stegfs achieves this is by not remembering where each file is stored between mounts.

<span style="color:#dc143c;">**Warning!** stegfs has changed! Think of this as version 2&mdash;version 2015.08 cannot and (unless you force it) will not read or write to file systems created by previous versions.</span> You have been warned&hellip;

In contrast to previous versions, stegfs 2015.08 and newer use GNU's [libgcrypt] to provide the cryptography, and no longer forces a single cipher/hash combo; you are free to choose the algorithms used when the file system is created _(see man (1) mkstegfs for details)_.

As stegfs has reached a stable state and is mostly feature complete. It allows reading and writing files (obviously), and various mechanisms for limiting the damage done to files as new files are added, yet it still retains its aura of deniability. Pre-built binary packages are usually available for Arch, Debian, Fedora, and Slackware shortly after the latest source code is released. As always, the Git repository has the latest (but not always greatest) code we've committed.

<span style="color:#dc143c;">Remember:</span> if you intend to build from source yourself you will obviously need the development libraries for libgcrypt and its dependencies. Consult your package management system for further details.

Now for a few technical details: each file system block is 2KB, with 1,976 being used for actual data, and the rest being used to verify the integrity of the data, and point to the location of the next block.  (Thus, not only is stegfs lossy, it's also very inefficient! Oh - and _really_ slow.) A typical stegfs partition of 1GB will support files up to approximately 123MB&mdash;this is roughly twice the capacity of previous versions.

stegfs uses a file hierarchy similar to that of conventional file systems, although one important point worth noting is that it doesn't actually store directories. If you store a file in some obscure tree and then unmount the file system, you will need to recreate that original path to access the file. For each subdirectory a check is made to ensure that the current block isn't already being used by another file down the same. Files at a deeper level 'know' about the files above them, but files in the root directory know only of those other files also in the root. This basically means that files at a deeper level are less likely to overwrite another file, but in turn, are more susceptible to being overwritten themselves.

<span style="color:#dc143c;">NB:</span> Unlike the previous version, the 2015.08\* releases are not yet multi-threaded; this is (hopefully) enforced by the FUSE driver. **This makes stegfs slow!**

Binary packages, and GPG signatures, for release 2015.08.1 are available below for x86_64 architectures; if you're looking to use stegfs on other operating systems and/or architectures, the source code is your best bet (it seems to work okay on FreeBSD):


|OS|Package|GPG Signature|
|-|-|-|
|[Arch Linux]|[pkg][ap]|[Signature][ag]|
|[Debian]|[deb][dp]|[Signature][dg]|
|[Fedora]|[rpm][fp]|[Signature][fg]|
|[Slackware]|[tgz][sp]|[Signature][sg]|
|Source|[.tar.xz][zp]|[Signature][zg]|

[FUSE]: http://fuse.sourceforge.net
[libgcrypt]: http://www.gnu.org/software/libgcrypt/

[Arch Linux]: http://www.archlinux.org
[ap]: /downloads/stegfs/2015.08.1/stegfs-2015.08.1-1-x86_64.pkg.tar.xz
[ag]: /downloads/stegfs/2015.08.1/stegfs-2015.08.1-1-x86_64.pkg.tar.xz.asc

[Debian]: http://www.debian.org
[dp]: /downloads/stegfs/2015.08.1/stegfs_2015.08.1-1_amd64.deb
[dg]: /downloads/stegfs/2015.08.1/stegfs_2015.08.1-1_amd64.deb.asc

[Fedora]: http://fedoraproject.org
[fp]: /downloads/stegfs/2015.08.1/stegfs-2015.08.1-1.x86_64.rpm
[fg]: /downloads/stegfs/2015.08.1/stegfs-2015.08.1-1.x86_64.rpm.asc

[Slackware]: http://www.slackware.com
[sp]: /downloads/stegfs/2015.08.1/stegfs-2015.08.1-x86_64-1aa.tgz
[sg]: /downloads/stegfs/2015.08.1/stegfs-2015.08.1-x86_64-1aa.tgz.asc

[zp]: /downloads/stegfs/2015.08.1/stegfs-2015.08.1.tar.xz
[zg]: /downloads/stegfs/2015.08.1/stegfs-2015.08.1.tar.xz.asc

*[FUSE]: Filesystem in Userspace
*[RPM]: RPM Package Manager
*[GNU]: GNU's not Unix
