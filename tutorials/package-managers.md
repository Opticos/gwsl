---
layout: default
title: Installing a Graphical Package Manager on WSL
permalink: /package-managers.html
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



