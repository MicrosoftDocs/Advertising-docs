---
title: AdAdditionalField Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a list of optional Ad properties that you can request when calling GetAdsByAdGroupId, GetAdsByEditorialStatus, and GetAdsByIds.
---
# AdAdditionalField Value Set - Campaign Management
Defines a list of optional [Ad](ad.md) properties that you can request when calling [GetAdsByAdGroupId](getadsbyadgroupid.md), [GetAdsByEditorialStatus](getadsbyeditorialstatus.md), and [GetAdsByIds](getadsbyids.md). This set of flags enables you to get the latest features using the current version of Bing Ads Campaign Management API, and in the next version the corresponding propertys will be included in the [Ad](ad.md) object by default.

> [!NOTE]
> This value set is reserved for future use.

## Syntax
```xml
<xs:simpleType name="AdAdditionalField" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="TitlePart3" />
        <xs:enumeration value="TextPart2" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="textpart2"></a>TextPart2|Request that the *TextPart2* element be included within each returned [ExpandedTextAd](expandedtext.md) object.|
|<a name="titlepart3"></a>TitlePart3|Request that the *TitlePart3* element be included within each returned [ExpandedTextAd](expandedtext.md) object.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[GetAdsByAdGroupId](getadsbyadgroupid.md)  
[GetAdsByEditorialStatus](getadsbyeditorialstatus.md)  
[GetAdsByIds](getadsbyids.md)  
