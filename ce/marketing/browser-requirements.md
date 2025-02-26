---
title: "Browser requirements for Dynamics 365 for Marketing | Microsoft Docs"
description: "Learn about the browser requirements for Dynamics 365 for Marketing"
keywords: browser;requirements
ms.date: 04/01/2018
ms.service: dynamics-365-marketing
ms.custom: 
  - dyn365-marketing
ms.topic: article
applies_to: 
  - Dynamics 365 for Customer Engagement (online)
  - Dynamics 365 for Customer Engagement Version 9.x
ms.assetid: 69bb4966-4abc-474a-8696-216441f1f530
author: kamaybac
ms.author: kamaybac
manager: shellyha
ms.reviewer:
topic-status: Drafting
search.audienceType: 
  - admin
  - customizer
  - enduser
search.app: 
  - D365CE
  - D365Mktg
---

# Browser and system requirements

Dynamics 365 for Marketing is a cloud-based service that does not require special software other than an up-to-date web browser, though some restrictions apply. Read this topic to find out which devices, browser, and browser settings you should use when working with Dynamics 365 for Marketing.

## Supported desktop browsers

For desktop systems, the system and browser requirements for Dynamics 365 for Marketing are the same as those for Office 365 plans for business, education, and government, as listed in [System requirements for Office](https://go.microsoft.com/fwlink/p/?LinkId=723597). This includes  the following OS/browser combinations:

- **Windows** : current versions of Google Chrome, Mozilla Firefox, and Microsoft Edge, plus Microsoft Internet Explorer 11.
- **Mac OS** : current versions of Apple Safari and Google Chrome

## Supported tablet browsers

You can use the following OS/browser combinations to work with Dynamics 365 for Marketing on a tablet:

- Apple iOS 11 (or higher) with the current Apple Safari browser
- Google Android 7 (or higher) with the current Google Chrome browser
- Microsoft surface tablets running any supported desktop browser

## Accessibility

Dynamics 365 for Marketing has been tested to work correctly with the following accessibility technologies:

- Microsoft Edge browser (current version) with Microsoft Narrator screen reader
- Google Chrome browser (current version) with NV Access NVDA screen reader
- Google Chrome browser (current version) with Freedom Scientific JAWS screen reader
- Google Android Talkback screen reader
- Apple iOS Voice Over screen reader

## Browser configuration

Regardless of which supported browser you use, you must configure your browser as follows:

- **Allow pop-up windows from Dynamics 365 for Marketing**<br>You must configure your browser to allow all pop-up windows from your Dynamics 365 domain (see your browser's documentation for instructions). Most modern web browsers block all pop-up windows by default. Some browsers alert you when they block a pop-up window, (for example by showing an icon in the address bar), but others do not.
- **Allow JavaScript from Dynamics 365 for Marketing**<br>JavaScript must be enabled for your browser, at least for your Dynamics 365 domain. Most browsers enable JavaScript by default.
- **Allow cookies from Dynamics 365 for Marketing**<br>Cookies must be enabled for your browser, at least for your Dynamics 365 domain. Most browsers enable cookies by default.

## Enable touch for Microsoft Edge browsers

If you are using Microsoft Edge on a touch device, such as a tablet, then you must do the following to enable the touch-based drag-and-drop features:

1. Run Microsoft Edge.
2. Type &quot;about:flags&quot; into the address bar and select Enter.
3. A page of local browser settings opens. Under Standards Preview, set Enable touch events to Always on.
4. Restart your browser.

## Supported email clients

Marketing emails created and delivered using Dynamics 365 for Marketing, including all templates included with Dynamics 365 for Marketing, will render correctly on a wide range of recipient email clients, though older clients typically support fewer formatting options. For a complete list of tested email clients, see [Tested email clients](email-templates.md#tested-clients)
