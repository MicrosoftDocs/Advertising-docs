---
title: "Dynamic Search Ads Code Example"
ms.service: "bing-ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
description: Setup Dynamic Search Ads in C#, Java, PHP, or Python.
dev_langs:
  - csharp
  - java
  - php
  - python
---
# Dynamic Search Ads Code Example
This example uses the Campaign Management API to setup a Dynamic Search Ads (DSA) campaign.

> [!IMPORTANT]
> Beginning early Q2 calendar year 2021, Bing Ads API clients will not be allowed to add new campaigns with the campaign type set to "DynamicSearchAds". You can still edit and read dynamic search ads campaigns.  
> 
> Shortly after the dynamic search ads campaign creation calls began to fail, the campaign type for all dynamic search ads campaigns will be updated from "DynamicSearchAds" to "Search." Both "SearchDynamic" and "SearchStandard" ad groups will be allowed for these campaigns as described in the [mixed campaigns](mixed-campaigns.md) guide. We anticipate that it could take a couple of weeks to convert dynamic search ads campaigns to search campaigns across all accounts.  
> 
> We will announce more specific dates closer to Q2. 

[!INCLUDE[request-header](./includes/code-tips.md)]

[!code-csharp[Main](../../../BingAds-dotNet-SDK/examples/BingAdsExamples/BingAdsExamplesLibrary/v13/DynamicSearchAds.cs)]

[!code-java[Main](../../../BingAds-Java-SDK/examples/BingAdsDesktopApp/src/main/java/com/microsoft/bingads/examples/v13/DynamicSearchAds.java)]

[!code-php[Main](../../../BingAds-PHP-SDK/samples/V13/DynamicSearchAds.php)]

[!code-python[Main](../../../BingAds-Python-SDK/examples/v13/dynamic_search_ads.py)]

## See Also
[Get Started with the Bing Ads API](get-started.md)  
