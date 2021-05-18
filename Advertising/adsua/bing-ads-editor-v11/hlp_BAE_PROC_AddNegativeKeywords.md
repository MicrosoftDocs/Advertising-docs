---
title: Add negative keywords
description: Help prevent your ads from being displayed with negative keywords in Microsoft Advertising Editor.
ms.service: "Bing-Ads-Editor-v11"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Add negative keywords

Negative keywords are a great way to help prevent your ads from being displayed when a search query contains your keywords but is not relevant to your landing page content.

Campaign-level keywords apply to all keywords in a campaign. Negative keywords assigned at the campaign level will also be applied at the ad group level (in addition to any ad group-specific negative keywords).

## Add a single negative keyword
1. Select the campaign or ad group from the tree view in the left panel.
1. Select **Negative Keywords** under **Keywords and targeting** from the type list in the left panel.
1. In the data view, click **Add negative keyword** and select **Add ad group negative keyword** or **Add campaign negative keyword**.
1. Type your negative keyword in the edit pane and select a match type.
**Note** [!INCLUDE [NoMinusSign](./includes/NoMinusSign.md)]

## Add multiple negative keyword
1. Select the campaign or ad group from the tree view in the left panel.
1. Select **Negative Keywords** under **Keywords and targeting** from the type list in the left panel.
1. In the data view, click **Make multiple changes** and then select **Add/update multiple ad group negative keywords** or **Add/update multiple campaign negative keywords**.
1. In the **Make multiple Changes** dialog box, do one of the following:
   - If you are going to paste in a list that includes campaign and ad group names, check the **My negative keyword data includes campaign and ad group names**.
   - If you are going to paste in a list that does not contain campaign and ad group names, uncheck **My negative keyword data includes campaign and ad group names**.

1. Under **Select location**, select the campaigns or ad groups that you want to add negative keywords to.
1. Click **Insert headings**.
1. In the text box, type the data for one ad per line, in the order indicated by the headings. [!INCLUDE [MCW_PressTab](MCW_PressTab)]
1. Click **Next**.
1. Select the appropriate column headings in each of the drop-down boxes and click **Import**.
1. [!INCLUDE [MCWImportCompleted](./includes/MCWImportCompleted.md)]

> [!NOTE]
> Microsoft Advertising does not support keyword-level negative keywords. If you're using third-party or custom applications to add negative keywords, those applications might allow you to enter keyword-level negative keywords. However, Microsoft Advertising will not use them when filtering queries. It is therefore important that you avoid using keyword-level negative keywords and instead add those negative keywords to the ad group or campaign level.
> Microsoft Advertising Editor users must be running version 8.1 or later to use exact match negative keywords. Users of earlier versions are limited to phrase match.
> [!INCLUDE [UploadReminder](./includes/UploadReminder.md)]


