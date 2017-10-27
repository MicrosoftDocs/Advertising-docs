---
title: Differences between Google and Bing Ads QueryControl messages
description: Lists the differences between Google's and Bing Ads' QueryControl messages
ms.service: "hotel-ads-query-control-message"
ms.topic: "article"
ms.date: 11/01/2017
author: "swhite-msft"
manager: ehansen
ms.author: "scottwhi"
---

# Differences between Google's and Bing Ads' QueryControl messages

The following are the differences between Google's QueryControl Message implementation and Bing's.

- Bing ignores the `HintControl` element. Your hint message may specify any of the hint formats (exact, date range, expanded date range), and there's no restriction on the number of properties that you may specify with each format.   
  
- The maximum value that you may specify for `MaxAdvancePurchase` is 180.  
  
- The maximum value that you may specify for `MaxLengthOfStay` is 14.  
  
- Bing does not fully overwrite the previous QueryControl message with the contents of the new message. Bing does overwrite the list of property overrides with those in the message, so each successive message needs to contain any overrides that you want to maintain.  
  
  For the \<DefaultValue\> element, only the `State` element defaults back to enabled if the message does not specify it. All other settings retain the previous value if not specified. For example, if you previously specified a value for `MaxAdvancePurchase`, but excluded it from the current message, Bing continues using the previous value.
