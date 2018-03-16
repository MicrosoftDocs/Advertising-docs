---
title: PricingModel Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the pricing model for an ad group.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# PricingModel Value Set - Campaign Management
Defines the pricing model for an ad group.

## Syntax
```xml
<xs:simpleType name="PricingModel" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Cpc" />
    <xs:enumeration value="Cpm" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="cpc"></a>Cpc|The pricing model is cost-per-click (CPC).|
|<a name="cpm"></a>Cpm|The pricing model is cost per thousand-impressions (CPM).<br /><br /> Available for members of the CPM pilot program.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[AdGroup](adgroup.md)  
