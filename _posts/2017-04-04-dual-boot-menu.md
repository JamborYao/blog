---
layout: post
title: 闲谈
tags: windows7 boot menu
---

## How to change Windows 7 & Windows 8.1dual boot menu 

### Situation one: 

When you install the Windows 8.1 on a Windows 7 based computer, the boot option is appearing as below:
 
![](/images/blog/2017-04-04/choose-system.png)

Figure-1

If you want to use the old Windows 7 boot menu, follow these steps:

1.	Start the computer and go into above Windows 8.1 style boot menu.  (Figure-1).
2.	Click Change defaults or choose other options link on that menu. (Figure-1).
3.	It pops up Figure-2 window.
4.	Click Choose a default operation system option. (Figure-2)
5.	It pops click Figure-3 window, click Windows 7 Enterprise option to set Windows 7 as the default operating system. 
6.	Complete these steps, it will be changed to Windows 7 style boot menu.(Figure-4)

![](/images/blog/2017-04-04/choose-options.png)
 
Figure-2
 
![](/images/blog/2017-04-04/choose-default.png)

Figure-3

### Situation two:

When you install the Windows 7 on a Windows 8.1 based computer, the boot menu is appearing as below:

![](/images/blog/2017-04-04/boot-menu.png)
 
Figure-4

If you want to get the GUI as Windows 8.1 style, follow these steps:

1.	Boot into Windows 8.1 computer, open the command Prompt (Admin). 
2.	Type the following command line and press Enter (Figure-5).
bcdboot  c:\Windows
3.	Complete these steps, next time reboot you'll see the Windows 8.1 style menu.(Figure-1)

![](/images/blog/2017-04-04/command.png)

 Figure-5

### Situation three:

When you have dual boot system, one of the system disappear from the boot menu. We could follow these steps to get it back:

1.	Boot the computer from the installation media (Here my example is Windows 7) that works fine system.
2.	Go into System Recovery Options menu. (Figure-6)
3.	Click Command Prompt link to open the command prompt window
4.	Use the diskpart and list volume commands to confirm the OS boot drive.
5.	Backup the bcd file, rename it. (Figure-7)
6.	Rebuild a new bcd file. It will scan all disk to confirm all Windows installation on your computer and ask if you want to add them to boot list. (Figure-7)
7.	Type Y to agree with adding to boot list. And then in next boot, you will get all boot options back in the boot menu.

![](/images/blog/2017-04-04/system-recover.png)

Figure-6
 
![](/images/blog/2017-04-04/boot.png)

Figure-7
