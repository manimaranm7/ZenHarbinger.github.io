---
layout: post
title: Torgo
date: '2016-07-13 15:29:17 -0400'
categories: dev
tags: [dev, java, snapcraft, gradle]
author: Matthew Aguirre
---

I have added a new plugin into snapcraft for building snaps from Java projects utilizing gradle.  The plugin utilizes the [jar task](https://docs.gradle.org/current/userguide/java_plugin.html#N15BFE).  Mirrored from the maven plugin where `mvn package` is called, the gradle plugin calls `./gradlew [OPTOINS] jar` with any additional parameters that are passed in via the `gradle-options` property in the plugin.

Output files located in the build/libs directory are copied to the snaps `jar` directory.

Also, happy birthday Mackenzie!

snapcraft.yaml:
```yaml
name: java-hello-gradle
version: 1.0.0
summary: A java example using gradle
description: this is not much more than an example using gradle
confinement: strict

apps:
    hello:
        command: bin/wrapper

parts:
    local:
        plugin: gradle
        source: .
        gradle-options: [--debug]
    wrapper:
        plugin: make
        source: .
```
