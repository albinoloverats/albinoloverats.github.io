---
layout: page
title: lmtpd
nav: true
permalink: /projects/lmtpd
---

<span style="color:red;text-align:center;">This project is no longer in active development</span>

lmtpd is a simple mail transfer daemon for local mail (i.e. from cron jobs, and between local users). This is especially useful if you have no need for a full-blown mail transfer agent and just want to allow local users to message each other without spamming the world at large.

<span style="color:red;text-decoration:line-through;">**Warning:** lmtpd is still very much in the development phase and may contain horrendous bugs!</span>

lmtpd is now (we think) quite stable :) with the help of [Valgrind][] we've eliminated memory leaks and having cleaned up the common code, config settings and command line arguments are handled as expected.

We have a simple [Arch Linux][] startup script---we'll add more if there's demand---so lmtpd will start at boot and then just keep going...

[Valgrind]: http://valgrind.org
[Arch Linux]: http://www.archlinux.org

*[lmtpd]: Local Mail Transfer Protocol Daemon
