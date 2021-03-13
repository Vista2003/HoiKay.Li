---
layout: post
title: "Changing the IPv6 DNS on Edgerouter X"
date: 2021-03-13
categories: Networking
description: Tutorial on changing the IPv6 DNS on Edgerouter X
---
If you have an EdgeRouter and you want to change the DNS for IPv6, it can be a bit of a pain as it appears as no one seems to know properly how to change it for IPv6. Some suggest adding it to your name server list but if SLAAC got an IPv6 DNS from your ISP then that isn’t going to do anything and the no-dns flag in my experience ends up disabling IPv6. The instructions here are intended for the EdgeRouter X though it can work with other EdgeRouters without a switch when you replace the term switch with the appropriate ethernet port. <br>

You’ll need to SSH into your EdgeRouter to perform these commands as it’s easier to do it using the command line rather than trying to edit the config tree.
```
configure
edit interfaces switch switch0 ipv6 router-advert
set radvd-options “RDNSS <YOUR IPv6 DNS IP ADDRESS HERE> { };”
commit
save 
exit
```
If you have received no errors when inputting the commands, check your devices. On modern versions of stock Android (at least Android 10), you can see the DNS settings in the Wi-Fi connection. 
If you see no external IPv6 addresses and/or the IPv6 DNS is fe80::%wlan0 then you have a syntax error, check what you have inputted into the command line and delete the changes and redo them. <br>


If the DNS has been set correctly, go to an IPv6 test site or an IPv6 only site and if they load correctly then congratulations, you have set your IPv6 settings correctly!
