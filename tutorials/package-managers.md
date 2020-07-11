---
layout: default
title: Installing a Graphical Package Manager on WSL
permalink: /tutorials/package-managers.html
---
## Choosing a Package Manager

There are several to choose from depending on your Linux distribution. Here are some common ones.

##### Package Managers for Debian-Based Distributions Using APT

*  Synaptic - Easy to Install and Very Powerful.

   In the WSL terminal:
   
   ```bash
   sudo apt install synaptic
   ```
   To run Synaptic, use ```sudo synaptic```

*  Gnome Software - Streamlined But Quirky and Buggy at Times.

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

## Creating a Windows Shorcut for the Package Manager

Use the [Shortcut Creator](https://opticos.github.io/gwsl/tutorials/shortcut.html) with the command and name of the program. Be sure to set "Run as Root" to True.

