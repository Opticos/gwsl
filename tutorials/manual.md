---
layout: default
title: GWSL Manual
permalink: /tutorials/manual.html
---
## Table of Contents
1.  [Prerequisites](#prerequisites)
2.  [Installing GWSL](#installing-gwsl)
3.  [The GWSL User Interface](#the-gwsl-user-interface)
4.  [Configuring a WSL Distro for use with GWSL](#configuring-a-wsl-distro-for-use-with-gwsl)
5.  [Using the GWSL Shortcut Creator](#using-the-gwsl-shortcut-creator)
6.  [Using the Integrated Linux App Launcher](#using-the-integrated-linux-app-launcher)
7.  [Using GWSL with the Linux Terminal](#using-gwsl-with-the-linux-terminal)
8.  [Using GWSL with SSH](#using-gwsl-with-ssh)
9.  [Using GWSL with other Shells](#using-gwsl-with-other-shells)
10.  [Using GWSL Configuration Files](#using-gwsl-configuration-files)

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


### Configuring a WSL Distro for use with GWSL ###


### Using the GWSL Shortcut Creator ###


### Using the Integrated Linux App Launcher ### 

### Using GWSL with the Linux Terminal ###

### Using GWSL with SSH ###

### Using GWSL with other Shells ###
#### Using X with Fish
Auto-exporting does not work if Fish is the default shell but you can use this script.
``
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
``
Add this to the end of `config.fish` and you should be good to go!

### Using GWSL Configuration Files ###
