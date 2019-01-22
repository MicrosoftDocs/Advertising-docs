---
title: "Bing Ads Scripts Reference"
description: "Provides information about the JavaScript objects that you use in your scripts."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Bing Ads Scripts Reference

[!INCLUDE[preview-note](./includes/preview-note.md)]

Bing Ads Scripts lets you access and manage your Bing Ads data using JavaScript in Bing Ads' browser-based [script editor](./get-started.md).

This section provides information about the JavaScript objects that you use in your scripts.

For information about Bing Ads entities and the limits that apply to each entity, see [Entity Hierarchy and Limits](/bingads/guides/entity-hierarchy-limits).

The following are the top-level objects that you use to access your Bing Ads entities and perform other tasks.

|Object|Description|
|-|-
[AccountsApp](./reference/AccountsApp.md)|This is the top-level object that you use if you're managing accounts for others. Use it to get the list of accounts you have access to, and to select the account to manage. [Read more](./guides/multi-account-access.md).
[BingAdsApp](./reference/BingAdsApp.md)|This is the top-level object used to access and manage single-account entities, such as campaigns and keywords. [Read more](./guides/single-account-access.md).
[UrlFetchApp](./reference/UrlFetchApp.md)|This is the top-level object used to fetch resources from the web.


