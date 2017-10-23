---
title: "Validating your Transaction Message"
description: Shows how to validate a transaction message.
ms.service: "hotel-ads-transaction-message"
ms.topic: "article"
ms.date: 11/1/2017
author: "swhite-msft"
manager: ehansen
ms.author: "scottwhi"
ms.date: 11/1/2017
---

# Validate your Transaction Message

Bing provides the [Transaction XSD](https://bhacstatic.blob.core.windows.net/schemas/transaction.xsd) that you use to validate your transaction message before sending it to Bing. This saves time and round trips by catching document syntax errors. You should always validate your transaction messages before sending them to Bing.

The following example shows using xmllint to validate the message contained in SampleTransaction.xml.

```
xmllint.exe --schema transaction.xsd SampleTransaction.xml
```
