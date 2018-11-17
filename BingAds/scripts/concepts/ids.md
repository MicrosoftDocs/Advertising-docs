---
title: "Bing Ads Scripts IDs"
description: "Describes how IDs are handled in Bing Ads Scripts."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Defining IDs in scripts

[!INCLUDE[preview-note](../includes/preview-note.md)]

IDs in Bing Ads Scripts are strings not integers. For example, when calling a selector's `withIds` method, you pass an array of string IDs, not an array of integer IDs. Or, if you call an entity's `getId()` method, it returns the ID as a string, not an integer.

## Next steps

> [!div class="nextstepaction"]
> [Review the reference guide](../reference/BingAdsApp.md)