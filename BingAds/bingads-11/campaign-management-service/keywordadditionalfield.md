---
title: KeywordAdditionalField Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a list of optional Keyword properties that you can request when calling GetKeywordsByAdGroupId, GetKeywordsByEditorialStatus, and GetKeywordsByIds.
---
# KeywordAdditionalField Value Set - Campaign Management
Defines a list of optional [Keyword](/bingads/campaign-management-service/keyword.md) properties that you can request when calling [GetKeywordsByAdGroupId](/bingads/campaign-management-service/getkeywordsbyadgroupid.md), [GetKeywordsByEditorialStatus](/bingads/campaign-management-service/getkeywordsbyeditorialstatus.md), and [GetKeywordsByIds](/bingads/campaign-management-service/getkeywordsbyids.md). This set of flags enables you to get the latest features using the current version of Bing Ads Campaign Management API, and in the next version the corresponding propertys will be included in the [Keyword](/bingads/campaign-management-service/keyword.md) object by default.

## Syntax
```xml
<xs:simpleType name="KeywordAdditionalField" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="InheritedBidStrategyType" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="inheritedbidstrategytype"></a>InheritedBidStrategyType|Request that the *InheritedBidStrategyType* element be included within each returned [InheritFromParentBiddingScheme](/bingads/campaign-management-service/inheritfromparentbiddingscheme.md) object (nested within the *BiddingScheme* element of a [Keyword](/bingads/campaign-management-service/keyword.md)).|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[GetKeywordsByAdGroupId](getkeywordsbyadgroupid.md)  
[GetKeywordsByEditorialStatus](getkeywordsbyeditorialstatus.md)  
[GetKeywordsByIds](getkeywordsbyids.md)  
