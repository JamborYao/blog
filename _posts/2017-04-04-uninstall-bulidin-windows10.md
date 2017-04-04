---
layout: post
title: How to uninstall the Built-in app in Windows 10 
tags: windows10 build-in-app
---

## How to uninstall the Built-in app in Windows 10 

### Issue:

In Windows 10 Insider Preview build 10074 and 10122, someone may encounter this issue:
Mail App cannot launch, crash or not working correctly.

### Solution:

In this Scenario, we need to re-register this app or reinstall it from Windows store.
Re-register this App:

1.	Run the PowerShell as Administrator.
2.	Type Get-AppxPackage, press Enter.
3.	From the output list, find the Mail App and remember the InstallLocation as blew:
 	![](/images/blog/2017-04-04/install-location.png)
4.	And then type this command:
    `Get-AppXPackage | Foreach {Add-AppxPackage -DisableDevelopmentMode -Register "C:\Program Files\WindowsApps\microsoft.windowscommunicationsapps_17.4119.42011.0_x64__8wekyb3d8bbwe\AppxManifest.xml"}`
5.	It would run as below:
	![](/images/blog/2017-04-04/get-apppackage.png)



If re-register App cannot resolve your issue, do the next.

### Re-install the App:

**First step**: Uninstall it completely

1.	Run the PowerShell as Administrator.
2.	Type Get-AppxPackage, press Enter.
3.	From the output list, find Mail App package and remember its PackageFullName as below:
	![](/images/blog/2017-04-04/package-fullname.png)
4.	And then type the following command:
    `Remove-Appxpackage –Package microsoft.windowscommunicationsapps_17.4119.42011.0_x64__8wekyb3d8bbwe`
5.	It would run as below:
	![](/images/blog/2017-04-04/remove-apppackage.png)

>Note: After running this command in Windows Insider Preview 10074 build, the Mail icon still appear in the App list and start menu. However, you cannot click to launch it. Just ignore and continue next step.

**Second step**: Reinstall it from Windows Store 
