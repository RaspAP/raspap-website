---
date:
  created: 2025-10-26
title: New multilingual support
linkTitle: New multilingual support
authors:
    - billz
---

<img src="/blog/assets/images/jason-leung-mZNRsYE9Qi4-unsplash.jpg" width="600px"><br/>
<sub>_Photo by <a href="https://unsplash.com/@ninjason?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Jason Leung</a> on <a href="https://unsplash.com/photos/white-neon-light-signage-on-wall-mZNRsYE9Qi4?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>_</sub>
      

We're glad to announce the release of [RaspAP 3.4.6](https://github.com/RaspAP/raspap-webgui/releases/tag/3.4.6) and Insiders 3.5.3, which bring comprehensive localization updates across five of our community's most popular languages. This release represents a significant milestone in making RaspAP accessible to users worldwide, with fully translated interfaces that now load automatically based on your browser's language preferences.

<!-- more -->

## New locale support
This latest release includes complete locale updates for the following:

- **Italian (it_IT)** - full Italian translation
- **Spanish (es_MX)** - full Spanish localization
- **German (de_DE)** - complete German translation
- **French (fr_FR)** - full French localization
- **Chinese (zh_CN)** - complete simplified Chinese translation

Each of these languages now features 100% coverage of RaspAP's interface, from basic settings to advanced configuration options. Every menu item, button label, help text, and system message has been carefully translated to provide a native experience for speakers of these languages.

## Locales baked in
RaspAP's [custom OS images](/quick-start), built using our specialized `pi-gen` [fork](https://github.com/RaspAP/pi-gen), now include the `locales-all` package by default. This package provides comprehensive locale data for all supported languages, ensuring that character encoding, date formats, number formatting, and other regional conventions work correctly across the entire system.

## What this means
In the past, users were required to manually generate a locale on their system to enable translations. Now, with locales baked in to our custom images, RaspAP will automatically display your preferred language without any special configuration.

This means that speakers of Spanish, French, German, Italian, Korean, and Chinese (simplified) will see RaspAP in their native language the moment they access the web interface. No trips to the system settings menu are required.

## How it works
RaspAP reads your browser's language preference settings in the `HTTP_ACCEPT_LANGUAGE` header. If your browser language matches one of our supported locales, the interface loads in that language immediately.

<img src="/blog/assets/images/german-login.png" width="400px"><br/>

The system works out of the box on first boot. Behind the scenes, the application stores a "locale" cookie value to persist your preferred language across sessions.

You can still configure a different locale in the **System > Language** tab, as before.

## Getting involved
Our localization effort spans 24 languages and is managed centrally on [Crowdin](https://crowdin.com/project/raspap). Here you'll find our supported translations, recent activity, discussions and so on. You can get started by simply choosing the language you'd like to contribute to. Crowdin makes it easy to get involved as a translator, proofreader or QA specialist.

We've integrated [DeepL](https://www.deepl.com/en/translator) machine translations via their API, in addition to Crowdin's own predictive translations. This means you can get suggestions from one of the best available machine translators currently available.

For more info, see Crowdin's [walkthrough](https://support.crowdin.com/crowdin-intro/#translation-process) of the translation process.

## Discussions
Questions or comments about our multilingual support? Join the [discussion here](https://github.com/RaspAP/raspap-webgui/discussions/).