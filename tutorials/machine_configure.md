---
layout: default
title: Preparing & Managing WSL Machines
permalink: /tutorials/machine_configure.html
---
## Using the GWSL Machine Manager

<!-- ### Contents:
[Accessing Machine Settings](#accessing-machine-settings)
[Using the Manager](#gwsl-machine-manager-overview) -->

### Getting Started

After a new WSL Distro is installed, several steps are required to get it up and running with GWSL: 
1.  The first step is to enable "Auto-Export Display" in the Distro configuration.
2.  After this, the user may tweak other settings explained on this page.


### Accessing Other Distro Settings ### 

To access per-distro-settings, open the GWSL Dashboard and click "GWSL Machine Tools".

Tip: You can open the GWSL Dashboard by clicking the "G" icon in the notification area or by clicking the icon in the Start Menu.

<img src="https://opticos.github.io/gwsl/tutorials/dashboardlink.png" width="500">


#### Choose the WSl Distro you want to configure:

<img src="https://opticos.github.io/gwsl/tutorials/chooser.png" width="300">

### GWSL Distro Manager Overview ###

<img src="https://opticos.github.io/gwsl/tutorials/configure.png" width="300">

### Key:

1) Display Auto Export - With other XServers for Windows 10, the user must type in several commands each time they launch a gui app. With GWSL, clicking this button makes these commands run automatically when the current WSL Distro starts. This must be enabled for every new WSL distro. NOTE: After converting a WSL machine between WSL 1 and 2, this button must be pressed again. 

<a href='#dbus' id='installation-guide' class='anchor' aria-hidden='true'></a>
2) Configure DBus - Some Gnome apps have trouble running on WSL. Clicking this button attempts to enable DBus to fix these issues. The root password of the current WSL Distro is required to do this. NOTE: This option is only available on Debian-based distributions.

3) GTK DPI Toggle - This button toggles the default DPI environment variable for GTK.

4) QT DPI Toggle - This button toggles the default DPI environment variable for QT. 

5) Theme Chooser - Unstable: This option allows users to set the default GTK theme of the Distro being configured. This attempts to scan ```/usr/share/themes/``` for GTK themes.

6) Help - Reboot the current WSL Distro.

