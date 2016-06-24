---
layout: post
title: Google Domains Dynamc DNS Check
date: '2016-06-16 13:54:17 -0400'
categories: dev
tags: [dev, python, dns]
author: Matthew Aguirre
---

[check-ip-change](https://github.com/ZenHarbinger/google-domains-dydns-ip-change) is a script for checking the local public IP address and a [Google Domains](https://domains.google.com/) Dynamic DNS registered address.

Add Configured Dynamic DNS Record.

```
$ check-ip-change --add
Domain: sub.domain.com
User: [Google Provided]
Password: [Google Provided]
E-Mail: [Google E-Mail address]
```

List Configured Dynamic DNS Records. This will list out an index value and name. This index or name value can be used when removing a configured record.

```
$ check-ip-change --list
[ 1 ] sub.domain.com
--------------------------
username: [Google Provided]
password: [Google Provided]
email: [Google E-Mail address]
```

Remove Configured Dynamic DNS Record.

```
$ check-ip-change --remove
Domain to Remove (Index or Name): 1
or
Domain to Remove (Index or Name): sub.domain.com
```

Configurations are stored in `~/.config/check-ip-change.json`, nothing is saved remotely.
