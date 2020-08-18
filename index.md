---
layout: homepage
title: GWSL
---


<img src="https://opticos.github.io/gwsl/tutorials/banner.png">

## GWSL

### What on Earth does this do? What is it for? How can it help me?

GWSL automates the process of running X on top of WSL and over SSH:
*  It lets you easily run graphical Linux apps on Windows 10.
*  It lets you run graphical apps located on remote Linux machines.
*  It provides a simple UI for launching Linux apps, managing them graphicaly, and creating customized Windows shortcuts for them.
*  All this at the click of a button! No memorization of commands necessary. *Easy!*

Bascially, it does alot of stuff so *you* don't have to! Maybe you'd better watch the video ↓

TODO: Insert promo video here

### Wait... Why is it called GWSL? From your title it looks like it should be called TFPHIWXS. Why didn't you call it that?

Meh... That doesn't sound too great. GWSL stands for Graphical WSL. WSL in turn stands for Windows Subsystem for Linux. :-)

### Great. But there are other XServers for Windows. Why should I use GWSL?

There are several alternative XServers for Windows 10. Some are proprietary (and costly). Some have not been updated for years. 

GWSL is Free.

GWSL is easy to install.

GWSL Builds on the VCXSRV XServer, one of the best open source Windows Xservers. It uses VCXSRV as a backend but adds many useful features. 

### Minimum System Requirements

Windows 10 Version 2004



### Using GWSL

[GWSL Manual](./tutorials/manual.html)

Quick Links:

[Familiarizing Yourself With WSL](https://docs.microsoft.com/en-us/windows/wsl/about).

[Enabling WSL and Installing Distros](https://docs.microsoft.com/en-us/windows/wsl/install-win10).

[Using GWSL](./tutorials/machine_configure.html).

<!--
TODO: [Prepare a Distro for X (Graphics Compatibility)](https://guides.github.com/features/mastering-markdown/).
TODO: [Enable Dbus (To Run Gnome Apps)](https://guides.github.com/features/mastering-markdown/).


#### More

Digging Deeper

TODO: [Frequently Asked Questions](./tutorials/shortcut.html).

[Creating a Linux App Shortcut on Windows](./tutorials/shortcut.html).

[Changing DPI Options](./tutorials/dpi.html).

TODO: [Changing the GTK Theme](https://guides.github.com/features/mastering-markdown/).

TODO: [Using the Integrated Linux App Launcher](https://guides.github.com/features/mastering-markdown/).

TODO: [Using Remote Linux Apps With X](https://guides.github.com/features/mastering-markdown/).

TODO: [Creating Windows Shortcuts for Remote Linux *Apps* With X](https://guides.github.com/features/mastering-markdown/).

TODO: [Creating Windows Shortcuts *ENTIRE* Remote Linux *Machines* With X](https://guides.github.com/features/mastering-markdown/).

Miscellaneous

[Installing a Graphical Linux Package Manager](./tutorials/package-managers.html).

-->

### Frequently Asked Questions
*  Why doesn't GWSL seem to work with Linux shells other than Bash? *This is by design. Only Bash is supported for auto export. However, you can still make x work with fish.*
```
# WSL2 display export
set --export WSL2 1
set ipconfig_exec (wslpath "C:\\Windows\\System32\\ipconfig.exe")
if which ipconfig.exe >/dev/null
    set ipconfig_exec (which ipconfig.exe)
end

set wsl2_d_tmp (eval $ipconfig_exec | grep -n -m 1 "Default Gateway.*: [0-9a-z]" | cut -d : -f 1)
if test -n "$wsl2_d_tmp"
    set first_line (expr $wsl2_d_tmp - 4)
    set wsl2_d_tmp (eval $ipconfig_exec | sed $first_line,$wsl2_d_tmp!d | grep IPv4 | cut -d : -f 2 | sed -e "s|\s||g" -e "s|\r||g")
    set --export DISPLAY "$wsl2_d_tmp:0"
    set -e first_line
else
    set --export DISPLAY (cat /etc/resolv.conf | grep nameserver | awk '{print $2}'):0
end

set -e wsl2_d_tmp
set -e ipconfig_exec
```
  ^Add this to the end of ```config.fish``` and you should be good to go!
*  What will happen when WSL2 gets official Wayland support? *We are just as excited about this as you are. Till it is available, GWSL will only function as an XServer. When Wayland is available, there will be an option to swicth between Wayland and X as a GWSL backend. The shortcut creator and app launcher will continue to work in the new Wayland mode.*
*  Why aren't there more questions? *We are woking on this... Not many questions have been asked frequently enough to put here. Start asking!*

### Help and Support

Need help? Visit our [help page](https://opticos.github.io/gwsl/help.html).

