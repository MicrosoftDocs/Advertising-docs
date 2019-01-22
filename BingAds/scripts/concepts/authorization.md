---
title: "Bing Ads Scripts Authorization"
description: "Describes how authorization works in Bing Ads Scripts."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# How does authorization work in Bing Ads Scripts?

[!INCLUDE[preview-note](../includes/preview-note.md)]

Scripts run in the context of the user that is signed in to Bing Ads. Scripts execute in the script editor or may be scheduled to run later. Because scripts run asynchronously, if the user signs out of Bing Ads while a script is running, the script continues running to completion.


