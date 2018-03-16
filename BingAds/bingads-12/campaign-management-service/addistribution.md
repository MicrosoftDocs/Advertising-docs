---
title: AdDistribution Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the ad distribution for the ad group.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# AdDistribution Value Set - Campaign Management
Defines the ad distribution for the ad group.

## Syntax
```xml
<xs:simpleType name="AdDistribution" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="Search" />
        <xs:enumeration value="Content" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="content"></a>Content|The content network is the ad distribution network for Bing Ads running in Windows apps. When you select the content network as the distribution channel, any keyword you add will have the content match type in addition to any other match type you select. Ads for the content network are referred to as "content ads."<br /><br />For example, content ads display if a keyword for the ad is part of the app. If an ad for a clothing company has the keyword "dress" and the keyword "shoes", a content-network app related to fashion could display the ad even though a person viewing the app did not search for "dress" or "shoes." That's where the content match type keyword works for you. To learn more see, [Differences between search ads and content ads](https://help.bingads.microsoft.com/#apex/3/en/52030/0) and [How content ads work](https://help.bingads.microsoft.com/#apex/3/en/51063/0).<br /><br /> Bing Ads no longer serves ads on the content network. Starting July 30th, 2017 you cannot set the Content ad distribution either. If you try to add or update an ad group with ad distribution set only to Content, the *CampaignServiceAdGroupMediumNotAllowedForDistributionChannel* error will be returned.  If you try to add or update an ad group with ad distribution set to both Search and Content, the operation will succeed, however the ad distribution will be stored as Search only. By end of calendar year 2017, Bing Ads will migrate the remaining Search and Content ad groups to Search only. Then when you retrieve the ad groups which were previously set to Search and Content, the ad distribution will be Search only. By end of calendar year 2017, Bing Ads will also delete Content-only ad groups.|
|<a name="search"></a>Search|The search network includes Bing.com, AOL.com, Yahoo.com, other Bing, AOL, or Yahoo owned and operated sites, and syndicated search partner sites that offer search capabilities, as well as on a variety of other syndicated search partner sites. For more information, see the `Network` element of [AdGroup](adgroup.md).<br /><br />With the search network, you can narrow ad distribution if needed: you can display your search ads on all sites in the search network; just Bing, AOL, and Yahoo owned and operated websites; or just the syndicated search partner sites. See [Differences between search ads and content ads](https://help.bingads.microsoft.com/#apex/3/en/52030/0) for more information.<br /><br />You might also be interested in Native Ads. A native ad is an ad whose subject matter and visual design are relevant to the page it is displayed on. More and more advertisers are turning to intent ads for their proven ability to assist in brand building and to drive purchase intent. Both search ads and intent ads are distributed on the search network. [Intent ads](../guides/intent-ads.md) are currently available to only a limited number of customers and will be shown only on select websites such as MSN. If intent ads are available for your campaign, you can manage your use of these ads and their bids using the intent ads bid adjustment on both the campaign and ad group settings pages. For more information, see the [About Bing Native Ads](http://help.bingads.microsoft.com/#apex/3/en/56674/0) article in Bing Ads help.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[AdGroup](adgroup.md)  
