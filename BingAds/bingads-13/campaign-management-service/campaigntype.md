---
title: CampaignType Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible campaign types.
---
# CampaignType Value Set - Campaign Management
Defines the possible campaign types.

> [!NOTE]
> Not everyone is enabled for Audience campaigns in the Microsoft Audience Network yet. If you don't, don't worry. It's coming soon. 

## Syntax
```xml
<xs:simpleType name="CampaignType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="Search" />
        <xs:enumeration value="Shopping" />
        <xs:enumeration value="DynamicSearchAds" />
        <xs:enumeration value="Audience" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="audience"></a>Audience|The campaign is an Audience campaign.|
|<a name="dynamicsearchads"></a>DynamicSearchAds|The campaign is a Dynamic Search Ads campaign.|
|<a name="search"></a>Search|The campaign is a Search campaign.|
|<a name="shopping"></a>Shopping|The campaign is a Bing Shopping campaign.<br/><br/>You should also check the campaign [SubType](campaign.md#subtype) to determine whether it is a Cooperative campaign.|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[Campaign](campaign.md)  
[GetCampaignsByAccountId](getcampaignsbyaccountid.md)  
[GetCampaignsByIds](getcampaignsbyids.md)  
