---
layout: post
title: 
date: 2020-02-04 13:37:00 +0100
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: HP-iLO2-extremely-slow-on-HTTPS.png # Add image post (optional)
tags: [PowerShell, PoSh, Scripting, Windows] # add tag
---
When you have the v2.33 (latest and greatest) iLO2 firmware installed, you might surprised that the HTTPS requests are taking forever. This is due to the new Diffie-Hellman key exchange.

When you are not worried by security threats as you have your firewall fence high up or using a VPN to reach your systems remotely you the best thing you can do is downgrade to ILO2 firmware v2.32.

When the downgrade has done the ILO 2 Log will happily tell you that you have **upgraded** your system, again!

```
Severity      | Class | Last Update      | Initial Update   | Count | Description
Informational | iLO 2 | 08/15/2018 22:59 | 08/15/2018 22:59 |   1   | Firmware upgraded to version 2.32. 
```

[Download the ILO2 firmware v2.32 here.](/assets/bin/hp-firmware-ilo2-2.32-1.1.zip)
