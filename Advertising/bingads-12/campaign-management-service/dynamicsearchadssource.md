---
title: DynamicSearchAdsSource Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible targeting source values for dynamic search ads campaigns.
---
# DynamicSearchAdsSource Value Set - Campaign Management
Defines the possible targeting source values for dynamic search ads campaigns.

## Syntax
```xml
<xs:simpleType name="DynamicSearchAdsSource" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="All" />
    <xs:enumeration value="SystemIndex" />
    <xs:enumeration value="AdvertiserSuppliedUrls" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="advertisersuppliedurls"></a>AdvertiserSuppliedUrls|Use URLs from my page feed only. Only URLs specified in the feed file will be served from this campaign. We recommend using this option for highly specific campaigns with tailored ad copy.|
|<a name="all"></a>All|Use URLs from both Bing's index of my website and my page feed. Pages from both sources will be used but URLs within the feed file will be given priority.|
|<a name="systemindex"></a>SystemIndex|Use Bing's index of my website. This is the default behavior of dynamic search ad campaigns on Bing.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[DynamicSearchAdsSetting](dynamicsearchadssetting.md)  
