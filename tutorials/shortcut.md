---
layout: default
title: Using the GWSL Shortcut Creator
permalink: /tutorials/shortcut.html
---
## Using the Shortcut Creator

To access the Shortcut Creator, open the GWSL Dashboard and click "Shortcut Creator".

The Shortcut Creator UI:
<img src="https://opticos.github.io/gwsl/tutorials/shortcut.png" width="430">

### Key:

Basic Options
1. Current App Icon - This is the icon that will be used for the Windows shortcut. The icon is automatically chosen from the Shortcut Label. 
2. Shortcut Label - This is the label that will apper on your Windows shortcut. The label is used to find an icon for the shortcut.
3. Shortcut Command - This is the Bash command that will launch your app.
4. Run In - The WSL machine that will run the app. Be sure that the app you want to pin is installed on the machine you select. 
5. Reset Icon - Click this if the icon automatically selected by the Shortcut Creator does not match that of the desired app. 
6. Help - Opens this help page.
7. More/Less Options - Show and hide advanced shortcut options.

Advanced Options
8. Display Mode - Choose if you want to run the app in GWSL Single Window, Multi Window, or Fullscreen mode. If Default is selected, the current app mode is used.
9. GTK Scale Mode - Override the HI-DPI scale factor for GTK. If Default is selected, the current GTK scale factor for the current machine is used. 
10. QT Scale Mode - Override the HI-DPI scale factor for QT. If Default is selected, the current QT scale factor for the current machine is used.
11. Shared Clipboard - Enable or Disable the shared clipboard for this app. If set to Disabled, the Windows clipboard will not synchronize with the Linux app. If set to Default, the current default clipboard mode is used.
12. Color Mode - If set to Follow Windows, GTK will try to synchronize light and dark theme modes with Windows.
13. Run As Root - If set to true, the shortcut will ask for a password at launch and run the command with sudo.
14. Use DBus - This only works on Debian-based distros. Use it for Gnome apps if they do not start. Ex. Gnome Software.
15. Experimental Flags - These rarely work. If GTK and QT scaling does not work, try using these flags.
16. Add to Start Menu - Add a shortcut for the app to the Windows Start Menu with these current settings. It is reccomended to test your configuration with "Test Configuration" before creating the shortcut.
17.  Test Configuration - Test the current settings to make sure everything works before adding your shortcut.

### More

You can also use the [Linux App Launcher](https://opticos.github.io/gwsl/tutorials/launcher.html) to create shortcuts.
