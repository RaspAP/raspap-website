---
date:
  created: 2025-11-30
title: Say "hello" to Kali Linux 2025.3 
linkTitle: Say "hello" to Kali Linux 2025.3
authors:
    - billz
---

<img src="/blog/assets/images/kali-linux-2025.jpg" width="600px"><br/>

Kali Linux 2025.3, [released](https://www.kali.org/blog/kali-linux-2025-3-release/) in September, represents the latest iteration of Offensive Security's premier penetration testing platform. This release continues Kali's evolution as the go-to distribution for security professionals, bringing updated toolsets and kernel improvements built on Debian.

<!-- more -->

Kali Linux support has been a longstanding request from RaspAP users, so we're excited to announce that RaspAP now extends beta support to the latest Kali 2025.3 release. This integration opens up powerful possibilities for security researchers and penetration testers who want to combine RaspAP's wireless routing capabilities with Kali's extensive security toolkit.

## Why Kali with RaspAP?

Kali Linux is specifically designed for digital forensics and penetration testing, shipping with hundreds of security-focused tools out of the box. When paired with RaspAP on a Raspberry Pi, you get a portable, low-power platform that's ideal for wireless security assessments.

Common use cases include:

- **Wireless penetration testing**: Create controlled test environments for evaluating WPA/WPA2/WPA3 security implementations
- **Rogue access point detection**: Deploy monitoring stations to identify unauthorized wireless networks
- **Packet analysis**: Capture and analyze wireless traffic in controlled testing scenarios
- **Client isolation testing**: Verify wireless client security controls and network segmentation
- **Evil twin assessments**: Test organizational defenses against access point spoofing attacks

With RaspAP handling the wireless infrastructure, you can focus on running Kali's security tools like `aircrack-ng`, `wifite`, `bettercap`, and `reaver` without worrying about the underlying network configuration.

## Installing RaspAP on Kali

Getting started with RaspAP on Kali Linux 2025.3 is straightforward. The [Quick installer](https://docs.raspap.com/quick) works seamlessly with Kali's Debian-based architecture:
```
curl -sL https://install.raspap.com | bash
```

The installer automatically detects Kali Linux and configures all necessary dependencies, including PHP-FPM support for optimal performance.

!!! Tip "Testing environment"
    RaspAP with Kali Linux should only be used in authorized testing environments. Always ensure you have proper permission before conducting any wireless security assessments, and limit testing to networks under your direct control.

## Getting started

If you're already running Kali Linux 2025.3 on your Raspberry Pi, simply invoke the Quick installer to add RaspAP. For those starting fresh, download the latest [Kali Linux ARM image](https://www.kali.org/get-kali/#kali-arm) for Raspberry Pi, flash it to your SD card, and then install RaspAP.

Custom Kali configurations and testing scenarios will vary depending on your specific use case, but RaspAP provides the flexible wireless foundation you need for professional security work.

## Discussions

Questions or comments about Kali Linux support? Join the [discussion here](https://github.com/RaspAP/raspap-webgui/discussions/).