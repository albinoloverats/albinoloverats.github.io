---
layout: post
title: "New Project: lmtpd"
date: 2010-09-22 09:41:53
categories: lmtpd
---
We've a new project!  It's a little way from the security related software we've developed in the past but hey-ho.

[def=Local Mail Transfer Protocol Daemon]lmtpd[/def] was conceived out of a necessity to deliver mail locally between user accounts without resorting to a full sendmail install, particularly as we already use [url=http://www.mutt.org]mutt[/url] with [url=http://msmtp.sourceforge.net/]msmtp[/url] for global mail delivery.  As msmtp didn't seem to handle local delivery on its own, we set about solving this by having msmtp's default profile send mail via the LMTP to our daemon, which then places messages in the users local mail box.  Each user is then free to use their own private profile to send outbound mail as normal.

Although not a security application, lmtpd has been designed with security in mind, as it only allows localhost connections by default, and while the code is available, it's not yet fully tested or completely functional as a typical system daemon.

We hope that in the coming weeks we're able to finish off the start/stop scripts and add sufficient documentation, and that [i](fingers crossed)[/i] lmtpd is useful to more than just us :)

Cheers
