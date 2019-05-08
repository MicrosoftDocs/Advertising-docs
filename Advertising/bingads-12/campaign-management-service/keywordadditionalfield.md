---
title: KeywordAdditionalField Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a list of optional keyword properties that you can request when calling GetKeywordsByAdGroupId, GetKeywordsByEditorialStatus, and GetKeywordsByIds.
---
# KeywordAdditionalField Value Set - Campaign Management
Defines a list of optional keyword properties that you can request when calling [GetKeywordsByAdGroupId](getkeywordsbyadgroupid.md), [GetKeywordsByEditorialStatus](getkeywordsbyeditorialstatus.md), and [GetKeywordsByIds](getkeywordsbyids.md). The additional field values enable you to get the latest features using the current version of Campaign Management API, and in the next version the corresponding properties will be included in the keyword by default.  

## Syntax
```xml
<xs:simpleType name="KeywordAdditionalField" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="FinalUrlSuffix" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="finalurlsuffix"></a>FinalUrlSuffix|Request that the [FinalUrlSuffix](keyword.md#finalurlsuffix) element be included within each returned [Keyword](keyword.md) object.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[GetKeywordsByAdGroupId](getkeywordsbyadgroupid.md)  
[GetKeywordsByEditorialStatus](getkeywordsbyeditorialstatus.md)  
[GetKeywordsByIds](getkeywordsbyids.md)  
