---
layout: post
title: Network connectivity lost after upgrading to an Insider Preview build
tags: network upgrade 
---


## When you install the Windows 8.1 on a Windows 7 based computer, the boot option is appearing as below:
 
![](/images/blog/2017-04-04/wifi-property.png)

Network connectivity lost after upgrading to an Insider Preview build

### Scenario:

You may lost network connectivity if you upgrade to an Insider Preview build and if you have Hyper-V with an External V-Switch or Visual Studio Phone Emulator installed before the upgrade.
To confirm if you’re having this specific issue, check these things:

1.	From the Start menu or screen, search for cmd and right click to run Command Prompt as Administrator.
2.	Type IPConfig and hit Enter. It will return an empty result if you have this issue. 
3.	From the Start menu or screen, search for View Network Connections and select it from the results. 
4.	Right-click on your network connection and select Properties. All of the check boxes for the protocols will be empty as below screenshot:

![](/images/blog/2017-04-04/device-manager.png)

### Cause:

This happens because during upgrade, the Virtual Switch migration encountered a race condition, and left the Network Interface in an Unbound state.

### Solution:

To resolve the issue, do the following:

1.	Use Search from the Start menu or screen to search for Device Manager.
2.	Open Device Manager, and expand Network Adapters.
3.	Locate the network adapter that is faulting [1], and right-click it (see screen below).
Note: Here make Microsoft Hyper-v Network adapter as an example.
 
4.	Select Uninstall [2].
5.	Select Scan for hardware changes [3]. 
After these operation, Windows should locate the corresponding network adapter and reinstall it.



