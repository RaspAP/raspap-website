---
date:
  created: 2025-09-27
title: Debian 13 "trixie" support is here
linkTitle: Debian 13 "trixie" support is here
authors:
    - billz
---

<img src="/blog/assets/images/debian-13-trixie.png" width="600px"><br/>

Debian 13 "trixie" was released on August 9th of this year, marking the latest stable release of the universal operating system that forms the foundation for countless Linux distributions. This release brings [many significant updates](https://www.debian.org/releases/trixie/release-notes/whats-new.en.html), including the Linux 6.12 LTS kernel.

<!-- more -->

For Raspberry Pi users, Debian 13's release is particularly relevant as Raspberry Pi OS is built on Debian. Early adopters have already begun testing the next version of Raspberry Pi OS trixie. With RaspAP now supporting Debian 13, users can take advantage of the latest system improvements and security enhancements for their wireless routers.

If you'd like to join these early adopters, this post has step-by-step instructions for upgrading your OS.

## Upgrading from bookworm

You can upgrade an existing bookworm (Lite) image to trixie by following the steps provided below, which were adapted from OS architect Simon Long's [post](https://forums.raspberrypi.com/viewtopic.php?t=389477). Debian's [official guidance](https://www.debian.org/releases/trixie/release-notes/upgrading.en.html) on upgrading from bookworm is also worth a read before diving in.

!!! warning "Important"
     The recommended and best approach will _always_ be to start with a clean trixie image and then install RaspAP, plus any other programs. You shouldn't attempt to upgrade any system that you rely on, and it's strongly advised to make a full backup before performing an upgrade. Bear in mind that, while this upgrade process has been tested repeatedly, it may still result in a broken image.

1. Start with a clean bookworm (Lite) image and update your system's package list, then upgrade the kernel, firmware and installed packages to their latest versions:
```
sudo apt update
sudo apt full-upgrade
```
2. Update the `apt` configuration for trixie by editing `/etc/apt/sources.list`. Change every reference to "bookworm" with "trixie". Do the same with `/etc/apt/sources.list.d/raspi.list`.
3. Run an `apt` update with the new package lists:
```
sudo apt update
```
4. Upgrade to trixie by executing the following:
```
sudo apt full-upgrade -y -o Dpkg::Options::="--force-confdef" -o Dpkg::Options::="--force-confnew" --purge --auto-remove
```
On a newer Pi model with a fast connection, the trixie upgrade takes about 10 minutes to complete. While it's running, you'll be asked to decide whether to restart services — answer "yes" to this prompt.
5. Finally, reboot your system:
```
sudo reboot
```

With the upgrade complete, reconnect to your device and confirm the new OS version by executing the following:
```
lsb_release -a
Distributor ID:	Debian
Description:	Debian GNU/Linux 13 (trixie)
Release:	13
Codename:	trixie
```

You can now proceed with installing the latest release of RaspAP.

## Installing RaspAP
For Debian 13 early adopters, RaspAP is available to install via the [Quick installer](https://docs.raspap.com/quick). Simply invoke the installer as you would normally:
```
curl -sL https://install.raspap.com | bash
```
The [version 3.4.3 release](http://github.com/RaspAP/raspap-webgui/releases/tag/3.4.3) includes updates to the installer and RaspAP's core with support for trixie. These updates are backwards compatible with bookworm and bullseye, so you can continue using these distributions with RaspAP.

Custom OS images, Docker containers and torrent files will be available after the official release of Raspberry Pi OS 64- and 32-bit (Lite) trixie.

## What's changed?
The biggest change in RaspAP under trixie is the move from `php-cgi` to `php-fpm` as the default PHP handler.

In Debian 13 with PHP 8.4, the `php-cgi` runtime, when used with web servers like lighttpd, applies stricter permission limits by default, which affects certain applications. Notably, this prevents RaspAP from interacting with system tools such as `iw`, `ip`, or `wpa_cli` — all of which are needed to fetch details about the Linux networking environment. This results in errors like the following:

```
The "no new privileges" flag is set, which prevents sudo from running as root.
Cannot open netlink socket: Address family not supported by protocol.
```

Even if sudo allows a given command for a specific user (usually, `www-data` under lighttpd), the `php-cgi` process doesn’t have the capabilities to execute it. 

For optimal compatibility and performance, RaspAP has moved to `php-fpm` (the FastCGI Process Manager) in place of `php-cgi`. Debian's own PHP packaging strongly emphasizes `php-fpm` as the preferred runtime for most use cases due to its superior performance, security, and configurability.

### Switching to php-fpm
RaspAP's installer handles this process for you automatically. 
If you previously ran `php-cgi` under lighttpd, you can switch to `php-fpm` by following these manual steps:

```
sudo apt udpate
sudo apt install php8.4-fpm
```

Next, enable its systemd service and update the web server configuration to use the FPM module:
```
sudo systemctl enable --now php8.4-fpm
sudo lighty-enable-mod fastcgi-php-fpm
```

The latter instructs lighttpd to pass requests to the FPM socket (typically located at  `/run/php/php8.4-fpm.sock`).

## Discussions
Questions or comments about Debian 13 and our move to PHP-FPM? Join the [discussion here](https://github.com/RaspAP/raspap-webgui/discussions/).