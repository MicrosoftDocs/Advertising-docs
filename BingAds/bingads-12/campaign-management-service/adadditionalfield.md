---
title: AdAdditionalField Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a list of optional ad properties that you can request when calling GetAdsByAdGroupId, GetAdsByEditorialStatus, and GetAdsByIds.
---
# AdAdditionalField Value Set - Campaign Management
Defines a list of optional ad properties that you can request when calling [GetAdsByAdGroupId](getadsbyadgroupid.md), [GetAdsByEditorialStatus](getadsbyeditorialstatus.md), and [GetAdsByIds](getadsbyids.md). The additional field values enable you to get the latest features using the current version of Bing Ads Campaign Management API, and in the next version the corresponding properties will be included in the ad by default.  

## Syntax
```xml
<xs:simpleType name="AdAdditionalField" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="TitlePart3" />
        <xs:enumeration value="TextPart2" />
        <xs:enumeration value="Images" />
        <xs:enumeration value="FinalUrlSuffix" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="finalurlsuffix"></a>FinalUrlSuffix|Request that the [FinalUrlSuffix](ad.md#finalurlsuffix) element be included within each returned [Ad](ad.md) object.|
|<a name="images"></a>Images|Request that the [Images](responsivead.md#images) element be included within each returned [ResponsiveAd](responsivead.md) object.|
|<a name="textpart2"></a>TextPart2|Request that the [TextPart2](expandedtextad.md#textpart2) element be included within each returned [ExpandedTextAd](expandedtextad.md) object.|
|<a name="titlepart3"></a>TitlePart3|Request that the [TitlePart3](expandedtextad.md#titlepart3) element be included within each returned [ExpandedTextAd](expandedtextad.md) object.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[GetAdsByAdGroupId](getadsbyadgroupid.md)  
[GetAdsByEditorialStatus](getadsbyeditorialstatus.md)  
[GetAdsByIds](getadsbyids.md)  
