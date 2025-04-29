# Linux kernel OJT exercises

## About this challenge

This challenge consists of several tasks, complete each task before proceeding to the next one.

Each task comes with detailed instructions possibly accompanied by relevant reading material, hints and a ~~proposed solution~~.

When writing code priorities are as follows in **decreasing** order:

1. Working code
2. Readability
3. Efficiency (Speed, Space)

## Requirements

These tasks were designed for the following environment:

- x64 Windows PC with WSL support (obviously Linux is also fine)
- Raspberry Pi 3 B+ (RPI from now on) )Running Raspberry Pi OS version 9.6 (stretch) (Or **32** bit Debian Stretch VM).  Tested on kernel version `4.14.79-v7+`.
- [Linux Kernel Development](https://www.amazon.com/Linux-Kernel-Development-Robert-Love/dp/0672329468) 3rd Edition by Robert Love

## Notes

* Follow the [official steps](https://www.raspberrypi.com/documentation/computers/getting-started.html) to set up your RPI.
* You'll probably want to connect to your RPI via SSH, you can do so using it's IP address, but it might change due to how DHCP works. We recommend [giving your RPI a hostname ](https://raspberrytips.com/set-new-hostname-raspberry-pi/)which you can type instead of it's IP address to connect to it. If that doesn't work, make sure [NetBIOS](https://www.thewindowsclub.com/enable-or-disable-netbios-over-tcp-ip-on-windows-10) is enabled.
* If you want to browse the linux kernel source code, you may prefer Bootlin's [Elixir Cross Referencer](https://elixir.bootlin.com/linux/latest/source) or Woboq's [code browser](https://codebrowser.dev/linux/linux/) to just opening the folder with VS Code.
