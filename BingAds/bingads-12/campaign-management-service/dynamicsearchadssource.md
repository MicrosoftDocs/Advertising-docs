---
title: DynamicSearchAdsSource Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Reserved.
---
# DynamicSearchAdsSource Value Set - Campaign Management
Reserved.

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
|<a name="advertisersuppliedurls"></a>AdvertiserSuppliedUrls|Reserved.|
|<a name="all"></a>All|Reserved.|
|<a name="systemindex"></a>SystemIndex|Reserved.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[DynamicSearchAdsSetting](dynamicsearchadssetting.md)  
