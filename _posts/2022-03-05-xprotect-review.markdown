---
layout: post
title: "Milestone XProtect Essential+ review from a homelabber "
date: 2022-03-05
categories: Review
description: A review of Milestone's XProtect Essential+ software
author: Hoi Kay
---
![XProtect Smart Client]({{site.github.url}}/assets/img/xprotect/smart.png)
Milestone XProtect is a Video Management Software (VMS) for network IP cameras. The Essential+ edition of its software is intended for small businesses and can be used with up to 8 network cameras. This is my review of the software as a home user with a Microsoft Active Directory home lab network after using the software for over a year. <br>
<br>
{% include toc.md %}

# Setup is time-consuming
The XProtect installer takes a long time to install the software onto your machine with many, many dependencies on Microsoft SQL Server and .NET Core. The installer feels very fragile with it breaking on my first attempt of installing 2020 R1 and then after that I couldn’t attempt to install it again until I reinstalled Windows on the system as the installer would fail with seemingly no self-correcting functions to it, so it has to be a perfect install to get it through. <br>
<br>
The XProtect Management Client feels like a relic of the Windows XP era, while it is perfectly functional, I can hardly call it user friendly like its makers claim as the interface does take a lot to get used to. <br>
Once XProtect is installed however, it does get better as I will detail below. <br>
<br>

# Clients are pretty good
The Smart Client on Windows is pretty easy to use and are quite customisable with what views you want. These views are synced across all the clients which means that they are set and forget. <br>
<br>
The mobile client on Android is also pretty good when it works though, with my slow upload, the playback was slower than real-time with the slow resolution and frame options not low enough for my slow VDSL line. An issue I have with the mobile client is when trying to access my server locally, it would use the local server address rather than the internet address which is a problem as the internet address has a proper TLS certificate while the local server address doesn’t and with no option to allow for self-sign certificates or options to disable automatic server mapping, it makes it next to impossible to use the client locally though I seem to have found mitigation for this by putting the server behind a Nginx Reverse Proxy. <br>
<br>
The web client is OK, though I find that forever reason after using it, my user account would get locked out due to multiple failed login attempts. The web client allows for quick viewing but it’s nowhere as good as the Smart or Mobile clients, use this as a last resort. <br>
<br>
It’s also important to note that while the Mobile and Web clients can start investigations that preserves footage indefinity for later investigations, the smart client can’t view or create these which in my opinion is an oversight and forces the use of them if you were to use this feature. <br>
<br>

# Quirks 
Here are some quirks that I’ve found with the software in no particular order. <br>
* AXIS Network Cameras with additional text in the overlay would sometimes get overwritten with a clock which makes them redundant as these have to be manually corrected every so often with no way of adding the text in the VMS itself. <br>
* AXIS Network cameras running the legacy 4.x firmware seem to have their events overwritten when the server connects to them and then never again until the server or camera has been rebooted. <br>
* Wireless network cameras would disconnect from the software more often than any other VMS software I’ve used. <br>
* The XProtect Mobile server seems to randomly crash after a while of someone viewing a feed on their phones. (This looks to be resolved) <br>
<br>

# In conclusion
Milestone XProtect Essential+ is a pretty good VMS software for environments with a low camera count. There are a lot of missing features like searching a spot in a video and push notifications to XProtect Mobile that can be found in the paid SKUs of the software but for a basic video surveillance system, it works well barring its quirks and faults. I just wished there was a way to expand XProtect Essential+ without upgrading to Express+ with for example having camera licenses for Essential+ if you wanted to expand to a system that supported up to 16 cameras.
