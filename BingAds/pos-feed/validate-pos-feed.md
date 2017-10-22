---
title: "Validating your Points of Sale Feed"
ms.service: "hotel-ads-pos-feed"
ms.topic: "article"
ms.date: 11/1/2017
author: "swhite-msft"
ms.author: "scottwhi"
description: 
---
# Validating your Points of Sale Feed
Bing provides the [PointsOfSale XSD](https://bhacstatic.blob.core.windows.net/schemas/point_of_sale.xsd) that you use to validate your points of sale feed before sending it to Bing. This saves time and round trips by catching document syntax errors. You should always validate your feed file before sending it to Bing.

The following example shows using xmllint to validate the SamplePointsOfSale.xml feed file.

```powershell
xmllint.exe --schema point_of_sale.xsd SamplePointsOfSale.xml
```
