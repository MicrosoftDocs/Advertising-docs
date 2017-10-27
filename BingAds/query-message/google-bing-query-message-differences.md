---
title: Differences between Google and Bing Ads Query messages
description: Lists the differences between Google's and Bing Ads' Query messages
ms.service: "hotel-ads-query-message"
ms.topic: "article"
ms.date: 11/01/2017
author: "swhite-msft"
manager: ehansen
ms.author: "scottwhi"
---

# Differences between Google's and Bing Ads' Query messages

The following are the differences between Google's Query Message implementation and Bing's.

- Bing does not support Live Queries. Bing will not include the following elements and attributes related to Live Queries.  
  - The `latencySensitive` attribute of the `Query` element. 
  - The `DeadlineMs` element.  
  
- Bing does not support room and room bundle information in Transaction Message. Bing will not include the `HotelInfoProperties` element.
