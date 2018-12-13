---
title: "Validating your Hotel Feed"
description: Shows how to validate your hotel feed file before sending it to Bing.
ms.service: "hotel-ads-hotel-feed"
ms.topic: "article"
author: "swhite-msft"
manager: ehansen
ms.author: "scottwhi"
---

# Validate your Hotel Feed

Bing provides the [Hotel XSD](https://bhacstatic.blob.core.windows.net/schemas/hotelV2.xsd) that you use to validate your hotels feed before sending it to Bing. This saves time and round trips by catching document syntax errors. You should always validate your feed file before sending it to Bing.

The following example shows using xmllint to validate the SampleHotelsFeed.xml feed file.

```
xmllint.exe --schema hotel.xsd SampleHotelsFeed.xml
```
