---
title: AdGroupAdditionalField Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a list of optional AdGroup properties that you can request when calling GetAdGroupsByCampaignId and GetAdGroupsByIds.
---
# AdGroupAdditionalField Value Set - Campaign Management
Defines a list of optional [AdGroup](adgroup.md) properties that you can request when calling [GetAdGroupsByCampaignId](getadgroupsbycampaignid.md) and [GetAdGroupsByIds](getadgroupsbyids.md). This set of flags enables you to get the latest features using the current version of Bing Ads Campaign Management API, and in the next version the corresponding properties will be included in the [AdGroup](adgroup.md) object by default.

## Syntax
```xml
<xs:simpleType name="AdGroupAdditionalField" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="InheritedBidStrategyType" />
        <xs:enumeration value="PrivacyStatus" />
        <xs:enumeration value="TargetSetting" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="inheritedbidstrategytype"></a>InheritedBidStrategyType|Request that the *InheritedBidStrategyType* element be included within each returned [InheritFromParentBiddingScheme](inheritfromparentbiddingscheme.md) object (nested within the *BiddingScheme* element of an [AdGroup](adgroup.md)).|
|<a name="privacystatus"></a>PrivacyStatus|Reserved.|
|<a name="targetsetting"></a>TargetSetting|Reserved.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[GetAdGroupsByCampaignId](getadgroupsbycampaignid.md)  
[GetAdGroupsByIds](getadgroupsbyids.md)  
