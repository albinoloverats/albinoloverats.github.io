---
layout: page
title: messaging
nav: true
permalink: /projects/messaging
fork: true
---

This is (intended to be) a fast and simple event messaging framework,
with support for:

* Events
* Queries (events that expect/generate a response)
* Running multiple instances of the server as well as client services
* SSL/TLS by default
* Very little configuration

## Getting Started

To get started with  just and the following to your `build.gradle` for
your [Spring Boot](https://spring.io/projects/spring-boot) service:

    implementation "net.albinoloverats.messaging:messaging-client:0.0.1"

And then annotate you event objects with `@Event` and your even handler
methods with `@EventHandler`. Likewise for any queries. Everything else
should then be handled for you.

## Configuration

Configuration options are identical for both server and client; an
optional list of server hosts, which defaults to auto and will direct
servers to issue a UDP broadcast message that can be picked up by other
server and clients alike (provided they are on the same network). A
value of none will disable this entirely and essentially force a single
server instance. The SSL/TLS capabilities can also be configured, from
the protocol version, to choosing between PEM certificates or JKS, with
a fall-back default of an ephemeral/in-memory certificate (only really
recommended for testing and development).

    messaging:
      hosts:
        - auto
      ssl:
        protocol: TLS
        pem:
          keyPath: /path/to/server-key.pem
          keyPassword: key-password
          certificatePath: /path/to/server-cert.pem
          trustPath: /path/to/ca-cert.pem
        jks:
          keyStorePath: /path/to/server-key-store.jks
          keyStorePassword: key-store-password
          trustStorePath: /path/to/client-trust-store.jks
          trustStorePassword: trust-store-password

Remember, if you intend to run multiple server instances, they will need
a trust certificate/store.

## Running

There is a Docker image for the server, which is available from
[Dockerhub](https://hub.docker.com/repository/docker/albinoloverats/messaging-server/general).
