---
title: Validate QueryControl messages
description: Shows how to validate a QueryControl message
ms.service: "hotel-ads-query-control-message"
ms.topic: "article"
author: "swhite-msft"
manager: ehansen
ms.author: "scottwhi"
---

# Validate QueryControl messages

Bing provides the [QueryControl XSD](https://bhacstatic.blob.core.windows.net/schemas/query_control.xsd) that you use to validate your QueryControl message before sending it to Bing. This saves time and round trips by catching document syntax errors. You should always validate your messages before sending them to Bing.

The following example shows using xmllint to validate the message contained in SampleQueryControl.xml.

```
xmllint.exe --schema query_control.xsd SampleQueryControl.xml
```
