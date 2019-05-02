---
title: "Supported JavaScript features"
description: "Identifies the JavaScript specification that Microsoft Advertising Scripts supports."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Supported JavaScript features

[!INCLUDE[preview-note](../includes/preview-note.md)]

Microsoft Advertising Scripts’ JavaScript engine supports most of [ECMAScript® 2015 Language Specification](http://www.ecma-international.org/ecma-262/6.0/). Use the auto-complete feature in the Scripts editor to confirm support of specific features and objects. Because the script’s code runs on Microsoft Advertising's servers, browser-based features like the DOM and Window APIs are not available.


> [!NOTE]
> The iterators don't support the **for-of** loop construct. For example:
>  
> ```javascript
>     for (var campaign of AdsApp.campaigns().get())
> ```
