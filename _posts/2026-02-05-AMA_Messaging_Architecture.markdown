---
layout: post
title: "AMA Messaging Architecture"
date: 2026-02-05 14:37:10
categories: messaging
tags: messaging
author: The messaging Development Team
---
This is the first usable release of our new messaging framework: AMA
Messaging Architecture. It may not be big and professional like Kafka,
but it sure is a hell of a lot easier to get up and running; certainly
based on my own experience in my day job!

There is a server that can easily be pulled via Docker Compose; a single
dependency for client services (and a sneaky second dependency for testing)
that is available from the [Maven Central Repository](https://central.sonatype.com/artifact/net.albinoloverats.messaging/messaging-client/overview).
There is also a demo project that showcases how to make use of it all.

More information can be found on the [project page](/projects/messaging).

Java, love it or hate it, it pays the bills.

Peace
