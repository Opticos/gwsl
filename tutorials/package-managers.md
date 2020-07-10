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

*  Gnome Software - Streamlined But Quirky and Buggy at Times.

   In the WSL terminal:
   
   ```bash
   sudo apt install gnome-software
   sudo apt install network-manager #This is required due to a WSL quirk
   ```

##### Package Managers for OpenSuse

*  YaST - The Recommended Default.

##### Package Managers for Other Distributions

There are hundreds of other Linux Distributions. Try checking [this page](https://www.tecmint.com/linux-package-managers/) out.

## Creating a Windows Shorcut for the Package Manager

1.  Open the GWSL Dashboard.

2.  Click Shortcut Creator.

3.  Write the title of the shortcut in the first section and the command to run the manager in the second.

4.  Under "More Options", set "Run as Root" to True. NOTE: If you are using Gnome-Software, set "Use DBus" to true as well.

5.  Test your shortcut configuration using the "Test Shortcut" Button. If it works, click "save and add". The package manager of your choice will be added to the Windows 10 Start menu.

