---
title: AdGroupAdditionalField Value Set
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a list of optional AdGroup properties that you can request when calling [GetAdGroupsByCampaignId](../campaign-management-service/getadgroupsbycampaignid.md) and [GetAdGroupsByIds](../campaign-management-service/getadgroupsbyids.md).
---
# AdGroupAdditionalField Value Set
Defines a list of optional [AdGroup](../campaign-management-service/adgroup.md) properties that you can request when calling [GetAdGroupsByCampaignId](../campaign-management-service/getadgroupsbycampaignid.md) and [GetAdGroupsByIds](../campaign-management-service/getadgroupsbyids.md). This set of flags enables you to get the latest features using the current version of Bing Ads Campaign Management API, and in the next version the corresponding properties will be included in the [AdGroup](../campaign-management-service/adgroup.md) object by default.

## Syntax
```xml
<xs:simpleType name="AdGroupAdditionalField" xmlns:xs="http://www.w3.org/2001/XMLSchema">
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
|<a name="inheritedbidstrategytype"></a>InheritedBidStrategyType|Includes the *InheritedBidStrategyType* element that can be nested within the *BiddingScheme* element of an [AdGroup](../campaign-management-service/adgroup.md) object. The *InheritedBidStrategyType* will only be returned if the *BiddingScheme* element is an [InheritFromParentBiddingScheme](../campaign-management-service/inheritfromparentbiddingscheme.md) object.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[GetAdGroupsByCampaignId](getadgroupsbycampaignid.md)  
[GetAdGroupsByIds](getadgroupsbyids.md)  
