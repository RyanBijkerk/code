---
layout: post
title: 
date: 2014-11-17 13:37:00 +0100
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: Creating_a_manual_Netscaler_backup.png # Add image post (optional)
tags: [PowerShell, PoSh, Scripting, Windows] # add tag
---
While using the Netscaler 10.0 version there is appearantly no way to create a backup of the Netscaler files. Neither the web interface nor the Netscaler console doesn't provide a backup facility.

Based on the undermentioned commands, which you can include in one single .SH file, the Netscaler can be saved. Restoring however takes some more effort.

```
tar -cvf nsconfig_backup.tar /nsconfig/ssl/
tar -rvf nsconfig_backup.tar /nsconfig/license/
tar -rvf nsconfig_backup.tar /nsconfig/fips/
tar -rvf nsconfig_backup.tar /var/netscaler/ssl/
tar -rvf nsconfig_backup.tar /var/wi/java_home/jre/lib/security/cacerts/
tar -rvf nsconfig_backup.tar /var/wi/java_home/lib/security/cacerts/
tar -rvf nsconfig_backup.tar /nsconfig/ns.conf
tar -rvf nsconfig_backup.tar /nsconfig/ZebOS.conf
tar -rvf nsconfig_backup.tar /nsconfig/rc.netscaler
tar -rvf nsconfig_backup.tar /nsconfig/snmpd.conf
tar -rvf nsconfig_backup.tar /nsconfig/nsbefore.sh
tar -rvf nsconfig_backup.tar /nsconfig/nsafter.sh
tar -rvf nsconfig_backup.tar /nsconfig/monitors/
tar -rvf nsconfig_backup.tar /var/download/
tar -rvf nsconfig_backup.tar /var/log/wicmd.log
tar -rvf nsconfig_backup.tar /var/wi/tomcat/webapps/
tar -rvf nsconfig_backup.tar /var/wi/tomcat/logs/
tar -rvf nsconfig_backup.tar /var/wi/tomcat/conf/catalina/localhost/
tar -rvf nsconfig_backup.tar /var/nslw.bin/etc/krb.conf
tar -rvf nsconfig_backup.tar /var/nslw.bin/etc/krb.keytab
tar -rvf nsconfig_backup.tar /var/netscaler/locdb/
tar -rvf nsconfig_backup.tar /var/lib/likewise/db/
tar -rvf nsconfig_backup.tar /var/vpn/bookmark/
tar -rvf nsconfig_backup.tar /var/netscaler/crl
tar -rvf nsconfig_backup.tar /var/nstemplates/
tar -rvf nsconfig_backup.tar /var/learnt_data/
tar -rvf nsconfig_backup.tar /netscaler/custom.html
tar -rvf nsconfig_backup.tar /netscaler/vsr.htm
```

After this you can SCP the files over to another location.