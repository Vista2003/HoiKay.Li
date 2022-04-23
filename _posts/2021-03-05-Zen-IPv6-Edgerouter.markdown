---
layout: post
title: "Configuring IPv6 on the EdgeRouter X on Zen"
date: 2021-03-05
categories: Networking
description: Configuring IPv6 on the EdgeRouter X Zen UK
author: Hoi Kay
---
Configuring IPv6 on the Edgerouter X on Zen can be a bit of a pain since there's not much documentation on the matter. These instructions are for the EdgeRouter X running the latest firmware but should be applied to the rest of the current Edgerouter line as long as the firmware is up to date though I haven't tested it.

An easy way of doing it is to go through basic setup again (note, this will reset all the Edgerouter's previous configurations) and enable DHCPv6 Prefix Delegation along with selecting your prefix length which in the case of Zen is /48.

After going through the setup and configuring the rest correctly, reboot and attach your modem and the rest of your network to the applicable ports. 

Once it has rebooted, open an SSH session with the Edgerouter and enter the following commands:

```
configure 
set interfaces ethernet eth0 pppoe 0 ipv6 enable 
set protocols static interface-route6 ::/0 next-hop-interface pppoe0 
commit 
save
exit 
```
After that IPv6 should work without the need to reboot.

Have fun browsing with IPv6. You can check if IPv6 is working by clicking [here](https://ipv6-test.com/).
![ipv6test]({{site.github.url}}/assets/img/ipv6/ipv6test.png)