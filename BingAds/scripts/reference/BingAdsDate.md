---
title: "BingAdsDate object"
description: "Contains properties that define a date."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# BingAdsDate

Contains properties that define a date.

Do not use this object to specify a date when calling one of the `forDateRange()` methods such as [AdGroupSelect.forDateRange()](AdGroupSelector.md#fordaterange~object-datefrom_-object-dateto~). Instead, you use this object to receive a date from methods such as [AdGroup.getStartDate()](AdGroup.md#getstartdate).


## Properties

|Property Name|Description|
|-|-
|day|The day of the month. For example, 30.
|month|The numeric calendar month, where 1 is January and 12 is December.
|year|The four-digit calendar year. For example, 2018.

