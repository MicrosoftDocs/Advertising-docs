---
title: "Validating your Hotel Feed"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "scottwhi"
---
# Validating your Hotel Feed
Bing provides the [Hotel XSD](https://bhacstatic.blob.core.windows.net/schemas/hotel.xsd) that you use to validate your hotels feed before sending it to Bing. This saves time and round trips by catching document syntax errors. You should always validate your feed file before sending it to Bing.

The following example shows using xmllint to validate the SampleHotelsFeed.xml feed file.

```powershell
xmllint.exe --schema hotel.xsd SampleHotelsFeed.xml
```
