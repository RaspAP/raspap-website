---
date:
  created: 2025-09-22
title: What's new in 2025
linkTitle: What's new in 2025
authors:
    - ruralmeltdown
---

<img src="/blog/assets/images/claudio-schwarz-v2MJSgfBT70-unsplash.jpg" width="600px"><br/>
<sub>_Photo by <a href="https://unsplash.com/@purzlbaum?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Claudio Schwarz</a> on <a href="https://unsplash.com/photos/white-and-red-train-in-tunnel-v2MJSgfBT70?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>_</sub><br/>

## Introduction
Welcome to the inaugural post for our new blog on our refreshed website! Have a read-through below to see what we've been up to this year. We look forward to hearing from you, whether it's a [feature request or bug report](https://github.com/raspap/raspap-webgui/issues), just to say "hi" in [Discord](https://discord.gg/KVAsaAR), or join our [Insiders](https://github.com/sponsors/RaspAP) for more features or to support our work.

<!-- more -->

## New website (now with a blog!)
If you've been to [raspap.com](https://raspap.com) before, you've probably noticed a brand-new look. The new site uses the [MkDocs framework](https://www.mkdocs.org) with the [SimpleAF](https://a3bagged.github.io/theme-test/) theme, which is based on Squidfunk's [Material for MkDocs](https://squidfunk.github.io/mkdocs-material). This new deployment aligns the website with our [documentation site](https://docs.raspap.com), which streamlines administration. It also easily enables us to have a [blog](/blog) now (which was previously hosted through Medium). We would love to hear from you if you have a blog post idea for how you're using RaspAP — just connect with us, or open a pull request in this site's [GitHub repository](https://github.com/RaspAP/raspap-website).  

## Status page
We thought it would be useful to have a status page to communicate the availability of RaspAP's various services. We chose [Uptime Robot](https://stats.uptimerobot.com/TDu7wXbKue) for this as lets us monitor uptime, response time and log incidents if they occur. Please [add this site](https://stats.uptimerobot.com/TDu7wXbKue) to your bookmarks if you rely on RaspAP's resources. 

<a href="/blog/assets/images/status-page.png" target="_blank"><img src="/blog/assets/images/status-page.png" width="250px" style="border: 4px; border-color: white;"></a><br/><sub>_(Click to view larger in new tab)_</sub><br/>

## Tidying up documentation
If you haven't been to our [documentation site](https://docs.raspap.com) in a while, please check it out now. We've added things like:  

- "Landing pages" to each of the major categories:
    - [Get Started](https://docs.raspap.com/get-started)
    - [Core Features](https://docs.raspap.com/features-core)
    - [Experimental Features](https://docs.raspap.com/features-experimental)
    - [Insiders](https://docs.raspap.com/features-insiders)
- Tabbed sections for pages that have "either/or" options; e.g.:
    - [Docker setup](https://docs.raspap.com/get-started/docker)
    - [SSL page](https://docs.raspap.com/features-core/ssl) (which also got quite an update to add detailed walkthroughs for various clients)  
    <a href="/blog/assets/images/ssl-tabs.png" target="_blank"><img src="/blog/assets/images/ssl-tabs.png" width="250px" style="border: 4px; border-color: white;"></a><br/><sub>_(Click to view larger in new tab)_</sub>

## New custom image downloads
We've made an effort to enable more people to download RaspAP's [pre-built OS images](/quick-start/#custom-os), particularly those with slow or unreliable internet connections. Starting with [v3.4.1](https://github.com/RaspAP/raspap-webgui/releases/tag/3.4.1), we've made available Torrent files for RaspAP's 64- and 32-bit image files. The downloads will still originate from GitHub, but are much easier to transfer, pause or resume using your preferred torrent client. Please connect with us if you still have issues downloading.

## Insider goals met
Earlier this year, **we met our [2nd Insiders Edition goal](https://docs.raspap.com/features-insiders/#1000-2nd-insiders-edition)** and **merged a big set of features into the main repository**! Thanks to this project's [sponsors](https://github.com/sponsors/RaspAP), we're able to allocate more time to develop and ship new features and bug fixes. This also means **we donated a record amount to the Raspberry Pi Foundation last quarter**. It was so significant that Open Collective, our fiscal sponsor, reached out to help us register the Foundation as a vendor. This will streamline our future giving and allow funds to be paid directly from our OC-managed balance.

## New features
Here's a rundown of the newest features you can start using straight away:

- [Firewall settings](https://docs.raspap.com/features-core/firewall/)
- [WPA3-Personal AP security](https://docs.raspap.com/features-core/ap-basics/#wpa3-personal)
- [802.11w Protected Management Frames](https://docs.raspap.com/features-core/ap-basics/#80211w)
- [Printable Wi-Fi signs](https://docs.raspap.com/features-core/ap-basics/#printable-signs)
- [Network diagnostics](https://docs.raspap.com/features-insiders/net-devices/#diagnostics)
- [Dynamic DNS](https://docs.raspap.com/features-insiders/dynamicdns/)
- [WireGuard kill switch](https://docs.raspap.com/features-core/wireguard/#kill-switch)
- [NTP Service](https://docs.raspap.com/features-insiders/ntp/)

## New contributors
Thank you and welcome to our newest contributors, we are grateful for their contributions over the last several releases: 

- [@tulik](https://github.com/tulik): Fix: add validation for CSS color formats in `getColorOpt` function
- [@YichaoXu](https://github.com/YichaoXu): Fix: mitigate UUF vulnerability by escaping entity with `escapeshellarg`
- [@Dhanus3133](https://github.com/Dhanus3133): 
    - CI builds 32 bit and 64 bit images, and
    - Add common script to configure public and Insiders builds
- [@francescoforcellini](https://github.com/francescoforcellini): Feature suggestion: Refactor `dhcpd.conf` handling with `updateDhcpdConfig()`
- [@no-sec-marko](https://github.com/no-sec-marko): Add interface validation and improve shell argument escaping
- [@danidemingo](https://github.com/danidemingo): Feature suggestion: User-configurable interface for WG PostUp/PostDown rules
- [@RuralMeltdown](https://github.com/rurarlmeltdown): helped with the new website, blog, and docs tidying; as well as some minor tweaks to the RaspAP base code

## Looking ahead
All currently planned milestones and goals can be found on our [GitHub project board](https://github.com/orgs/RaspAP/projects/2). If you would like to add, fix or change something, please feel free to create a GitHub issue (in the respective repository, of the relevant type), and we'll review it with you and get it slotted into the pipeline. 

One item that's high on our list is [supporting Debian Trixie](https://github.com/RaspAP/raspap-webgui/issues/1930). Users are encouraged to connect with us if they'd like to help test RaspAP with the latest Debian distribution.

It is worth noting that (most) new features land in [Insiders](https://docs.raspap.com/features-insiders) first, which you are encouraged to join, for as little as $10 USD per month.