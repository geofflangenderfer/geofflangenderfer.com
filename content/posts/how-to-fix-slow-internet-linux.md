---
title: "How to Fix Slow Internet Linux"
date: 2021-03-10T12:00:05-05:00
draft: false
---

# Summary
The default manjaro wireless drivers were incorrect, which made my internet painfully slow. 

Installing the correct drivers sped things up.

# How did you do it?

- find your specific wireless card info
```bash
$ lspci -vnn | grep Network 
02:00.0 Network controller [0280]: Broadcom Inc. and subsidiaries BCM43228 802.11a/b/g/n [14e4:4359]
```
- search google "\< your-driver-keywords \> driver install" (i.e. bcm driver install)
- grab first link and follow instructions (https://askubuntu.com/questions/55868/installing-broadcom-wireless-drivers)
    - find 4 alphanumerics separated by ":" and surrounded by "[]" (i.e. [14e4:4359])
    - lookup matching row in table to find drivers to install
    - install required drivers

```bash
git clone https://aur.archlinux.org/b43-firmware.git ~/.b43-firmware
cd .b43-firmware
makepkg -si
```
