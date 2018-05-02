---
title: "Bing Ads API Release Notes"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Get information about the changes to the Bing Ads services for each month.
---
# Bing Ads API Release Notes
For information about the changes to the Bing Ads Version 12 services for each month, see the following sections. 

## <a name="may2018"></a>May 2018
For information about this month's changes to Bing Ads services, see the following sections.

-   [Microsoft Audience Network Preview](#audiencenetwork-may2018)  

### <a name="audiencenetwork-may2018"></a>Microsoft Audience Network Preview
Support is added for the Microsoft Audience Network in preview. For differences between version 11 and 12, see [Migrate to Version 12](migration-guide.md). 

Available audiences e.g., in-market audiences differ between Audience campaigns and other campaign types. To determine which audiences are available and supported for a given campaign type, check the [SupportedCampaignTypes](../campaign-management-service/audience.md#supportedcampaigntypes) element of each [Audience](../campaign-management-service/audience.md) i.e., [CustomAudience](../campaign-management-service/customaudience.md#supportedcampaigntypes), [InMarketAudience](../campaign-management-service/inmarketaudience.md#supportedcampaigntypes), and [RemarketingList](../campaign-management-service/remarketinglist.md#supportedcampaigntypes). 

The audience list sizes between the Search and Audience network can vary. To determine the audience list size for the Microsoft Audience Network, check the [AudienceNetworkSize](../campaign-management-service/audience.md#audiencenetworksize) element of each [Audience](../campaign-management-service/audience.md) i.e., [CustomAudience](../campaign-management-service/customaudience.md#audiencenetworksize), [InMarketAudience](../campaign-management-service/inmarketaudience.md#audiencenetworksize), and [RemarketingList](../campaign-management-service/remarketinglist.md#audiencenetworksize). 

## <a name="april2018"></a>April 2018
For information about this month's changes to Bing Ads services, see the following sections.

-   [Version 12 General Availability](#v12-april2018)  
-   [Bing Ads Software Development Kit (SDK) Updates](#sdk-april2018)   
-   [Product Match Count Report](#reporting-productmatchcount-april2018)   

### <a name="v12-april2018"></a>Version 12 General Availability
Bing Ads API version 12 is now generally available. With the availability of Bing Ads API version 12, version 11 is deprecated and will sunset by October 31, 2018. For more details, see [Migrate to Version 12](migration-guide.md).

### <a name="sdk-april2018"></a>Bing Ads Software Development Kit (SDK) Updates
The Bing Ads .NET, Java, PHP, and Python SDKs are updated to support Bing Ads API Version 12. 

#### <a name="netsdk-april2018"></a>Bing Ads .NET SDK
The Bing Ads .NET SDK is updated to support .NET Standard 2.0. This will enable you to choose from a variety of platforms e.g., .NET Core or .NET Framework 4.6.1. For more information on .NET Standard and how it relates to other .NET frameworks, refer to this article on [.NET Standard](https://docs.microsoft.com/en-us/dotnet/standard/net-standard). 

#### <a name="pythonsdk-april2018"></a>Bing Ads Python SDK
The version parameter is now required when creating each ServiceClient. Previously the version was optional and defaulted to version 11. The version parameter is moved to the second position between the service client name and the authorization data. 

The file_type parameter now defaults to 'Csv' as an *str* datatype instead of the DownloadFileType for BulkFileReader, BulkServiceManager, DownloadParameters and SubmitDownloadParameters. You can set 'Tsv' if you prefer the tab separated file format type.

### <a name="reporting-productmatchcount-april2018"></a>Product Match Count Report
The [ProductMatchCountReportRequest](../reporting-service/productmatchcountreportrequest.md) is added for Bing Shopping campaigns. You can include details in the report such as impressions, clicks, and spend that you can use to see if you are covering and bidding across your Bing shopping campaigns inventory. Note that this only provides the matched data for your current Product Group level, and you cannot obtain historical views.

## <a name="march2018"></a>March 2018
For information about this month's changes to Bing Ads services, see the following sections.

-   [Version 12 Sandbox Beta](#v12-march2018)  

### <a name="v12-march2018"></a>Version 12 Sandbox Beta
The sandbox endpoints for Bing Ads API version 12 are available in beta. The interfaces are subject to change prior to general availability. For more details, see [Migrate to Version 12](migration-guide.md).
