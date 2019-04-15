---
title: "Bing Advertising Scripts IDs"
description: "Describes how IDs are handled in Bing Advertising Scripts."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Defining IDs in scripts

[!INCLUDE[preview-note](../includes/preview-note.md)]

IDs in Bing Advertising Scripts are strings not integers. For example, when calling a selector's `withIds()` method, you pass an array of string IDs, not an array of integer IDs. Or, if you call an entity's `getId()` method, it returns the ID as a string, not an integer.

## Next steps

> [!div class="nextstepaction"]
> [Review the reference guide](../reference/BingAdsApp.md)