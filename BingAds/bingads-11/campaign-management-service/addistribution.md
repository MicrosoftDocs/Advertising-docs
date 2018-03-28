---
title: AdDistribution Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the ad distribution for the ad group.
---
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
|<a name="content"></a>Content|The content network is the ad distribution network for Bing Ads running in Windows apps. When you select the content network as the distribution channel, any keyword you add will have the content match type in addition to any other match type you select. Ads for the content network are referred to as "content ads."<br /><br />For example, content ads display if a keyword for the ad is part of the app. If an ad for a clothing company has the keyword "dress" and the keyword "shoes", a content-network app related to fashion could display the ad even though a person viewing the app did not search for "dress" or "shoes." That's where the content match type keyword works for you.<br /><br /> Bing Ads no longer serves ads on the content network. Starting July 30th, 2017 you cannot set the Content ad distribution either. If you try to add or update an ad group with ad distribution set only to Content, the *CampaignServiceAdGroupMediumNotAllowedForDistributionChannel* error will be returned.  If you try to add or update an ad group with ad distribution set to both Search and Content, the operation will succeed, however the ad distribution will be stored as Search only. By end of calendar year 2017, Bing Ads will migrate the remaining Search and Content ad groups to Search only. Then when you retrieve the ad groups which were previously set to Search and Content, the ad distribution will be Search only. By end of calendar year 2017, Bing Ads will also delete Content-only ad groups.|
|<a name="search"></a>Search|The search network includes Bing.com, AOL.com, Yahoo.com, other Bing, AOL, or Yahoo owned and operated sites, and syndicated search partner sites that offer search capabilities, as well as on a variety of other syndicated search partner sites. For more information, see the `Network` element of [AdGroup](adgroup.md).<br /><br />With the search network, you can narrow ad distribution if needed: you can display your search ads on all sites in the search network; just Bing, AOL, and Yahoo owned and operated websites; or just the syndicated search partner sites. See [What is the search network](https://help.bingads.microsoft.com/#apex/3/en/52031/0) for more information.<br /><br />You might also be interested in Intent Ads. Bing Intent Ads is a native advertising solution optimized for search advertisers. This feature enables advertisers to get additional high-quality traffic from non-search placements. Bing Intent Ads experiences, such as ads placed within articles, are engaging for users, integrate naturally into page content, and deliver visually rich ads for advertisers. Bing Intent Ads campaigns are easy to set up, maintain, and optimize because they are fully integrated with existing Bing Ads' workflows. Bing [Intent ads](../guides/intent-ads.md) appear on select MSN pages, including the home page and within relevant articles. Ads may also appear in Outlook. Clicks on these ads will take users to the landing page you specified when you created your ads. If intent ads are available for your campaign, you can manage your use of these ads and their bids using the intent ads bid adjustment via both the campaign and ad group settings. For more information, see the [About Bing Intent Ads](http://help.bingads.microsoft.com/#apex/3/en/56674/0) article in Bing Ads help.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[AdGroup](adgroup.md)  
