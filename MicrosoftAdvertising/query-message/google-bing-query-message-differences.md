---
title: Differences between Google's and Microsoft Advertising's Query messages
description: Lists the differences between Google's and Microsoft Advertising's Query messages
ms.service: "hotel-ads-query-message"
ms.topic: "article"
author: "swhite-msft"
manager: ehansen
ms.author: "scottwhi"
---

# Differences between Google's and Microsoft Advertising's Query messages

The following are the differences between Google's Query Message implementation and Microsoft's.

- Microsoft does not support Live Queries. Microsoft will not include the following elements and attributes related to Live Queries.  
  - The `latencySensitive` attribute of the `Query` element. 
  - The `DeadlineMs` element.  
  
- Microsoft does not support room and room bundle information in Transaction Message. Microsoft will not include the `HotelInfoProperties` element.
