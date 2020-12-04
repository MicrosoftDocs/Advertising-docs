---
title: Differences between Google's and Microsoft Advertising's QueryControl messages
description: Lists the differences between Google's and Microsoft Advertising's QueryControl messages
ms.service: "bing-ads-hotel-service"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Differences between Google's and Microsoft Advertising's QueryControl messages

The following are the differences between Google's QueryControl Message implementation and Microsoft's.

- Microsoft ignores the `HintControl` element. Your hint message may specify any of the hint formats (exact, date range, expanded date range), and there's no restriction on the number of properties that you may specify with each format.   
  
- The maximum value that you may specify for `MaxAdvancePurchase` is 180.  
  
- The maximum value that you may specify for `MaxLengthOfStay` is 14.  
  
- Microsoft does not fully overwrite the previous QueryControl message with the contents of the new message. Microsoft does overwrite the list of property overrides with those in the message, so each successive message needs to contain any overrides that you want to maintain.  
  
  For the \<DefaultValue\> element, only the `State` element defaults back to enabled if the message does not specify it. All other settings retain the previous value if not specified. For example, if you previously specified a value for `MaxAdvancePurchase`, but excluded it from the current message, Microsoft continues using the previous value.
