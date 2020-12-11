---
title: "Microsoft Advertising Scripts Authorization"
description: "Describes how authorization works in Microsoft Advertising Scripts."
author: eric-urban
ms.author: eur
ms.service: "bing-ads-scripts"
ms.topic: "article"
---

# How does authorization work in Microsoft Advertising Scripts?

[!INCLUDE[preview-note](../includes/preview-note.md)]

Scripts run in the context of the user that is signed into the Microsoft Advertising web application. Scripts execute in the script editor or may be scheduled to run later. Because scripts run asynchronously, if the user signs out of Microsoft Advertising while a script is running, the script continues running to completion.


