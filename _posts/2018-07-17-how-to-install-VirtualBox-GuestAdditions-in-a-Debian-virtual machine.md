---
layout: post
title:  How to install VirtualBox Guest Additions in a Debian virtual machine
mathjax: false
comments: false
share: false
mathjax: false
tags:
- system
---

<!--more-->
1. Open terminal and become root `su`
2. Update APT cache: `apt-get update`
3. Install the latest security updates: `apt upgrade`
4. Install these required packages: `apt install build-essential module-assistant`
5. Configure your system for building kernel modules: `m-a prepare`
6. Insert Guest Additions ISO: Expand menu Devices and click on Insert Guest Additions CD image...
7. It should mount automatically, but if for any reason it doesn't: `mount /media/cdrom`
8. Run the following script: `sh /media/cdrom/VBoxLinuxAdditions.run`
9. Restart the system: `reboot`

[How to install VirtualBox Guest Additions in a Debian virtual machine](https://unix.stackexchange.com/questions/286934/how-to-install-virtualbox-guest-additions-in-a-debian-virtual-machine)