---
title: CampaignType Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: "article"
ms.date: 11/01/2017
author: eric-urban
ms.author: eur
description: Defines the possible campaign types.
---
# CampaignType Value Set - Campaign Management
Defines the possible campaign types.

## Syntax
```xml
<xs:simpleType name="CampaignType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="SearchAndContent" />
        <xs:enumeration value="Shopping" />
        <xs:enumeration value="DynamicSearchAds" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="dynamicsearchads"></a>DynamicSearchAds|The campaign is a Dynamic Search Ads campaign.|
|<a name="searchandcontent"></a>SearchAndContent|The campaign is a Search and Content campaign.|
|<a name="shopping"></a>Shopping|The campaign is a Bing Shopping campaign.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[Campaign](campaign.md)  
[GetCampaignsByAccountId](getcampaignsbyaccountid.md)  
[GetCampaignsByIds](getcampaignsbyids.md)  
