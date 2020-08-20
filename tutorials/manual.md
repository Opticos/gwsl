---
layout: default
title: GWSL Manual
permalink: /tutorials/manual.html
---
# THIS MANUAL IS UNDER CONSTRUCTION. CONTACT ME ON THE DISCORD SERVER OR BY EMAIL IF YOU NEED HELP.
## Table of Contents
1.  [Prerequisites](#prerequisites)
2.  [Installing GWSL](#installing-gwsl)
3.  [The GWSL User Interface](#the-gwsl-user-interface)
4.  [Configuring a WSL Distro for use with GWSL](#configuring-a-wsl-distro-for-use-with-gwsl)
5.  [Using the GWSL Shortcut Creator](#using-the-gwsl-shortcut-creator)
6.  [Using the Integrated Linux App Launcher](#using-the-integrated-linux-app-launcher)
7.  [Using GWSL with the Linux Terminal](#using-gwsl-with-the-linux-terminal)
8.  [Installing a Graphical Package Manager](#installing-a-graphical-package-manager)
9.  [Using GWSL with SSH](#using-gwsl-with-ssh)
10.  [Using GWSL with other Shells](#using-gwsl-with-other-shells)
11.  [Using GWSL Configuration Files](#using-gwsl-configuration-files)
12.  [Finding Logs](#finding-logs)


***

## GWSL Manual

### Prerequisites ###

GWSL requires [Windows 10 version 2004](https://support.microsoft.com/en-us/help/4028685/windows-10-get-the-update). If you do not have it, please update Windows to continue.

Once Windows is up to date, be sure you have the WSL feature installed and configured properly. Here are some helpful links:
*  [Familiarizing Yourself With WSL](https://docs.microsoft.com/en-us/windows/wsl/about)
*  [Enabling WSL and Installing Distros](https://docs.microsoft.com/en-us/windows/wsl/install-win10)

To make sure WSL is installed correctly, type ```wsl.exe``` in the command line and verify that there are no errors.

### Installing GWSL ###

GWSL can be easily installed from the Microsoft Store. If it is not already installed, get it [here](ms-windows-store://pdp/?productid=9NL6KD1H33V3) or [here](	https://www.microsoft.com/store/apps/9NL6KD1H33V3).

Note: Some Antiviruses might detect GWSL and block its installations. This is a known bug in Pyinstaller, the program we use to package GWSL. If this occurs, you might want to disable the Antivirus during installation.

### The GWSL User Interface ###
#### The Dashboard 

You can open the GWSL Dashboard by clicking the GWSL icon in the Start Menu. Once GWSL is running, you can quickly pull up the Dashboard with ```CTRL+ALT+G``` or by clicking the "G" icon in the notification area.

Overview: The GWSL Dashboard is where you can configure WSL machines, create shortcuts, and quickly launch apps.
<img src="https://opticos.github.io/gwsl/tutorials/dash annotated.png" width="400">
##### Key
1.  **GWSL Distro Tools:** Access various management and configuration options for WSL Distros.
2.  **Shortcut Creator:** Create Windows Shortcuts that launch graphical Linux apps running in WSL. Usage is explained [here](#using-the-gwsl-shortcut-creator).
3.  **Linux Apps:** You can access and launch most graphical Linux apps installed on WSL here. You can also instantly create shortcuts for these apps. *Note: The App Launcher does not always find all graphical programs. Also, some links might not be functional. To access these programs, please use the [Shortcut Creator](#using-the-gwsl-shortcut-creator) or WSL Shell.*
4.  **Linux Shell:** Access the shells of installed WSL Distros.
5.  **Graphical SSH Connection:** This feature allows you to log in to remote Linux machines and access their graphical apps on Windows. More is explained [here](#using-gwsl-with-ssh).
6.  **Donate:** I spent a long time developing this app and am now offering it for free. *Donations are appreciated.* [Donate here (-:](https://sites.google.com/bartimee.com/opticos-studios/donate).
7.  **Help:** Umm... This opens the [GWSL help page](https://opticos.github.io/gwsl/help.html).
8.  **About:** Shows GWSL credits, version, and license information.

### Configuring a WSL Distro for use with GWSL ###


### Using the GWSL Shortcut Creator ###


### Using the Integrated Linux App Launcher ### 

### Using GWSL with the Linux Terminal ###

### Installing a Graphical Package Manager ###

#### Choosing a Package Manager

There are several to choose from depending on your Linux distribution. Here are some common ones.

##### Package Managers for Debian-Based Distributions Using APT

*  Synaptic - Easy to Install and Very Powerful.

   In the WSL terminal:
   
   ```bash
   sudo apt install synaptic
   ```
   To run Synaptic, use ```sudo synaptic```

*  Gnome Software - Streamlined But Quirky and Buggy at Times. We do not reccomend using this one.

   In the WSL terminal:
   
   ```bash
   sudo apt install gnome-software
   sudo apt install network-manager-pptp-gnome #This is required due to a WSL quirk
   ```
   To run Gnome Software, use ```sudo gnome-software``` after starting [DBus](https://opticos.github.io/gwsl/tutorials/dbus.html).
   NOTE: To create a shortcut with the shortut creator, be sure to set "Enable DBus" under "More Options" to True:
   
##### Package Managers for OpenSuse

*  YaST - The Recommended Default.
   In the WSL terminal:
   
   ```bash
   sudo zypper install xterm
   ```
   To run YaST, use ```sudo xterm yast2```

##### Package Managers for Other Distributions

There are hundreds of other Linux Distributions. Try checking [this page](https://www.tecmint.com/linux-package-managers/) out.

#### Creating a Windows Shorcut for the Package Manager

Use the [Shortcut Creator](https://opticos.github.io/gwsl/tutorials/shortcut.html) with the command and name of the package manager. Be sure to set "Run as Root" to True.


### Using GWSL with SSH ###

### Using GWSL with other Shells ###
#### Using X with Fish
Auto-exporting does not work if Fish is the default shell but you can use this script.
```fish
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
Add this to the end of `config.fish` and you should be good to go!

### Using GWSL Configuration Files ###

#### The GWSL configuration file allows users to block certain applications and distros from showing up in the app launcher and machine chooser.
1.  Open Windows Explorer.

2.  In the path entry box, paste ```%AppData%/GWSL/```and hit enter.

3.  The configuration file is called ```settings.json```.

4.  Stop the GWSL Service and open this file in your favorite text editor to make changes.

#### Blocking Distros


### Finding Logs ###

#### Reporting a bug? Here is how to find bug reports and logs
1.  Open Windows Explorer.

2.  In the path entry box, paste ```%AppData%/GWSL/```and hit enter.

3.  The logs are stored in ```dashboard.log``` and ```service.log```.

4.  Include these logs in support emails or share them in the Discord help server.

