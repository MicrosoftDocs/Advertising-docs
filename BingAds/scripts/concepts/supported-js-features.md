---
title: "Supported JavaScript features"
description: "Identifies the JavaScript specification that Bing Ads Scripts supports."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Supported JavaScript features

[!INCLUDE[preview-note](../includes/preview-note.md)]

Bing Ads Scripts’ JavaScript engine supports most of [ECMAScript® 2015 Language Specification](http://www.ecma-international.org/ecma-262/6.0/). Use the auto-complete feature in the Bing Ads Scripts editor to confirm support of specific features and objects. Because the script’s code runs on Bing Ads' servers, browser-based features like the DOM and Window APIs are not available.


> [!NOTE]
> The iterators don't support the **for-of** loop construct. For example:
>  
> ```javascript
>     for (var campaign of BingAdsApp.campaigns().get())
> ```