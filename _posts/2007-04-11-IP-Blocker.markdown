---
layout: post
title: "IP Blocker"
date: 2007-04-11 19:37:37
categories: ip-blocker
---
[s]I've now uploaded the script I use (in conjunction with FireHOL) which helps to stop script kiddies from continually attempting to login to my machine as root, and what have you.

Nothing too fancy, every 15 minutes it scans [b]/var/log/auth[/b] and acts on it: if some one tries to logging as root or some other invalid user they get blocked. It allows a few failed attempts for real users just in case - this only applies to passwords, not usernames!

Let me know how it works for you :)[/s]

[color=red][b][update][/b]Project under reorganisation[b][/update][/b][/color]
