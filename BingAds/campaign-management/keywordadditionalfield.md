---
title: KeywordAdditionalField Value Set
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# KeywordAdditionalField Value Set
Defines a list of optional [Keyword](../campaign-management/keyword.md) properties that you can request when calling [GetKeywordsByAdGroupId](../campaign-management/getkeywordsbyadgroupid.md), [GetKeywordsByEditorialStatus](../campaign-management/getkeywordsbyeditorialstatus.md), and [GetKeywordsByIds](../campaign-management/getkeywordsbyids.md). This set of flags enables you to get the latest features using the current version of Bing Ads Campaign Management API, and in the next version the corresponding propertys will be included in the [Keyword](../campaign-management/keyword.md) object by default.

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
|<a name="inheritedbidstrategytype"></a>InheritedBidStrategyType|Includes the *InheritedBidStrategyType* element that can be nested within the *BiddingScheme* element of an [Keyword](../campaign-management/keyword.md) object. The *InheritedBidStrategyType* will only be returned if the *BiddingScheme* element is an [InheritFromParentBiddingScheme](../campaign-management/inheritfromparentbiddingscheme.md) object.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[GetKeywordsByAdGroupId](getkeywordsbyadgroupid.md)  
[GetKeywordsByEditorialStatus](getkeywordsbyeditorialstatus.md)  
[GetKeywordsByIds](getkeywordsbyids.md)  
