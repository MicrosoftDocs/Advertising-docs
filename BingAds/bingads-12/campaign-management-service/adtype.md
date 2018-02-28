---
title: AdType Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the type of ad.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.
# AdType Value Set - Campaign Management
Defines the type of ad.

## Syntax
```xml
<xs:simpleType name="AdType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Text" />
    <xs:enumeration value="Image" />
    <xs:enumeration value="Product" />
    <xs:enumeration value="AppInstall" />
    <xs:enumeration value="ExpandedText" />
    <xs:enumeration value="DynamicSearch" />
    <xs:enumeration value="ResponsiveAd" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="appinstall"></a>AppInstall|Refers to an [AppInstallAd](../campaign-management-service/appinstallad.md).|
|<a name="dynamicsearch"></a>DynamicSearch|Refers to a [DynamicSearchAd](../campaign-management-service/dynamicsearchad.md).|
|<a name="expandedtext"></a>ExpandedText|Refers to an [ExpandedTextAd](../campaign-management-service/expandedtextad.md).|
|<a name="image"></a>Image|Reserved for future use.|
|<a name="product"></a>Product|Refers to a [ProductAd](../campaign-management-service/productad.md).|
|<a name="responsivead"></a>ResponsiveAd|Reserved.|
|<a name="text"></a>Text|Refers to a [TextAd](../campaign-management-service/textad.md).|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[Ad](ad.md)  
[GetAdsByAdGroupId](getadsbyadgroupid.md)  
[GetAdsByEditorialStatus](getadsbyeditorialstatus.md)  
[GetAdsByIds](getadsbyids.md)  
