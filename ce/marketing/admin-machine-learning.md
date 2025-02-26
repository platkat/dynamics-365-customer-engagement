---
title: "Set up artificial intelligence features (Dynamics 365 for Marketing) | Microsoft Docs"
description: "How to enable artificial intelligence features and make related privacy settings in Dynamics 365 for Marketing"
keywords:
ms.date: 06/12/2019
ms.service: dynamics-365-marketing
ms.custom: 
  - dyn365-admin
  - dyn365-marketing
ms.topic: get-started-article
applies_to: 
  - Dynamics 365 for Customer Engagement (online)
  - Dynamics 365 for Customer Engagement Version 9.x
ms.assetid: 34da685e-94c6-46bf-8b5e-a9cddc01bbba
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

# Preview: Enable and configure artificial intelligence features

> [!IMPORTANT]
> All AI features are currently preview features. [!INCLUDE[cc_preview_features_definition](../includes/cc-preview-features-definition.md)]
> [!INCLUDE[cc_preview_features_no_MS_support](../includes/cc-preview-features-no-ms-support.md)]  

Dynamics 365 for Marketing provides several artificial intelligence (AI), which include:

- **[Spam score](spam-score.md)**, which analyzes the content of each marketing email message and generates a score that predicts how likely it is to be flagged by content-based spam filters.
- **[Smart scheduler](smart-scheduler.md)**, which analyzes email results to identify the days and times when each contact is most likely to be actively reading his or her email. It combines specific results for each contact with general results that apply to similar contacts identified by the AI. 
- **[Segment booster](segment-boost.md)**, which finds prospects who resemble and behave like the best contacts from a current segment and automatically adds those contacts to a running customer journey.

Each of these features applies AI technologies to generate their recommendations. The system "learns" by analyzing all the data available in your system in combination with general trends found across Microsoft services. The recommendations provided are tuned to apply to your specific customers based on your collected history of marketing activities and contact interactions. The more results you have in your system, and the more you use these features, the "smarter" the system becomes.

When you first install Dynamics 365 for Marketing, all artificial intelligence (AI) features are disabled by default and include privacy settings that can help make sure that you remain compliant with local privacy regulations (including GDPR) and other laws when you use them.

To enable AI features and make privacy settings for them:

1. Go to **Settings** > **Advanced settings** > **Machine learning** > **Basic feature configuration**.

    ![Enter the keyword name](media/admin-ai-settings.png "Enter the keyword name")

1. For each AI feature you'd like to use, set the **Enabled** slider to **On**.

1. For those AI features that include a **Consent level** setting, choose the level of consent that each contact must provide before being processed by that feature.
    - The **Optimal email sending time** and **Segment booster** features apply automated processing to data collected for each individual contact. Therefore, you probably need a required level of **(5) Profiling** to use these features in countries/regions where GDPR is in effect, and possibly in other countries/regions too.
    - The **Spam score** feature doesn't process any personal data, so no consent level is required for this feature.

1. Select the **Save** button near the top of the page to save your settings.

The level of consent required for each AI feature depends on your geographic location and that of your contacts. It may also depend on the way you have set up the data-protection features of Dynamics 365 for Marketing. It is your organization's responsibility to ensure that you are following all applicable laws in the countries/regions where you operate. More information: [Data protection and the GDPR](gdpr.md)
