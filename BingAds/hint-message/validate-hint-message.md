---
title: Validate a hint message
description: Shows how to validate a hint message before sending it to Bing Ads.
ms.service: "hotel-ads-hint-message"
ms.topic: "article"
author: "swhite-msft"
manager: ehansen
ms.author: "scottwhi"
ms.date: 11/1/2017
---

# Validate a hint message

Bing provides the [QueryControl XSD](https://bhacstatic.blob.core.windows.net/schemas/hint.xsd) that you use to validate your Hint message before sending it to Bing. This saves time and round trips by catching document syntax errors. You should always validate your messages before sending them to Bing.

The following example shows using xmllint to validate the message contained in SampleHint.xml.

```
xmllint.exe --schema hint.xsd SampleHint.xml
```
