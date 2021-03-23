---
layout: post
title: "The 1p Ethernet adapter review"
categories: Networking Review
description: A review of the unbelievably cheap ethernet adapter
author: Hoi Kay
---
![The adapter]({{site.github.url}}/assets/img/1p ethernet adapter review/item.jpg)
Well, it came early, and it just arrived like this with no driver CDs or invoice papers. <br>
First impressions are that it feels light though that’s expected for something so cheap. 

Now, let's plug it into a computer!

# Windows 10 64 Bit troubles
Plugging the adapter into my trusty ThinkPad X230 Tablet revealed that Windows 10 didn’t have the drivers for it to be plug and play. Device Manager returned an error 28 (no driver) when it was plugged in and it was identifying it as a “USB 2.0 10/100M Ethernet Adaptor”.
![device manager]({{site.github.url}}/assets/img/1p ethernet adapter review/deviceman.png)

After trying to get device manager to find the drivers and failing. I decided to give Snappy Driver Installer a go and to its credit, it correctly identified the device.
![SDI]({{site.github.url}}/assets/img/1p ethernet adapter review/driverinstaller.png)
But this "success" was shortlived as the driver just kept failing to be installed with error 0 which I can't find any information on from a brief search. 

Clearly Windows 10 isn't going to want to work with this adapter without a driver CD if at all so let's go back a bit to an older operating system.

# Using the adapter with Windows 8.1 32 Bit
OK, I know this isn't the world's most favourite version of Windows though it’s the oldest supported consumer OS from Microsoft. So let’s plug it in and see how it reacts.
![success]({{site.github.url}}/assets/img/1p ethernet adapter review/devicemanproperties.png)
And it works! <br>
Windows 8.1 correctly identified it and installed the correct drivers for it. As we can see, this adapter is using a Corechip Semiconductor chip. So let's benchmark it!

# Benchmarks
So under Windows, it's showing up as an 100mbps connection but according to the switch, we've only got a half duplex 10mbps connection.

![connectionstats]({{site.github.url}}/assets/img/1p ethernet adapter review/status.png) <br>
And when we compare it to what my Netgear switch is seeing:
![switchspeed]({{site.github.url}}/assets/img/1p ethernet adapter review/switchport.png)

When copying a file using SMB 3.02 over my network from my server, we only see a transfer rate that maxes out at 6.8 Mbps.
![benchmark]({{site.github.url}}/assets/img/1p ethernet adapter review/transfer speed.png)

Trying to improve the performance of the adapter, I went back into device manager and looked at the advanced settings for this adapter and found that I could change the connection speeds by changing it to 100 Mbps and 100 Mbps Full Duplex but these seemed to do nothing for the connection.
![settings]({{site.github.url}}/assets/img/1p ethernet adapter review/changingsettings.png)

# Verdict
If you see one for very cheap and want something to bottleneck your connection to effectively 7 Mbps then go-ahead. But if you want something to use for more than just telnetting into computers I would look elsewhere. <br>
Also, the indicator light in it just served to show how hollow the adapter is.
![light]({{site.github.url}}/assets/img/1p ethernet adapter review/light.jpg)

I honestly don’t know what to expect when I ordered it. To be honest, I half expected to receive nothing but it did came and performed around what I would have expected for a 10 Mbps ethernet adapter.