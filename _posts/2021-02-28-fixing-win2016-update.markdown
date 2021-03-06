---
layout: post
title: "Fixing Windows Server 2016 update after a clean install"
date: 2021-02-28 19:00
categories: Windows Server
---
After a clean install of Windows Server 2016 these days you may notice that Windows Update would hang and fail, this post just shows my fix for this issue.
You'll need to manually download and install the following updates in this order:
1. The latest Servicing Stack update
2. The latest Cumulative update


After installing these two updates, Windows Update should now work correctly though it will still be [slower than Windows 10 or Server 2019's update](https://borncity.com/win/2019/02/20/windows-server-2016-empirical-proof-of-slow-update-installs/).




You can download the Servicing Stack update [here](https://www.catalog.update.microsoft.com/Search.aspx?q=Servicing%20Stack) and the latest Cumulative update [here](https://support.microsoft.com/en-us/topic/windows-10-and-windows-server-2016-update-history-4acfbc84-a290-1b54-536a-1c0430e9f3fd).
