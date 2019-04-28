---
title: AdGroupCriterionAdditionalField Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a list of optional ad group criterion properties that you can request when calling GetAdGroupCriterionsByIds.
---
# AdGroupCriterionAdditionalField Value Set - Campaign Management
Defines a list of optional ad group criterion properties that you can request when calling [GetAdGroupCriterionsByIds](getadgroupcriterionsbyids.md). The additional field values enable you to get the latest features using the current version of Campaign Management API, and in the next version the corresponding properties will be included in the ad group criterion by default. 

## Syntax
```xml
<xs:simpleType name="AdGroupCriterionAdditionalField" xmlns:xs="http://www.w3.org/2001/XMLSchema">
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
|<a name="finalurlsuffix"></a>FinalUrlSuffix|Request that the [FinalUrlSuffix](biddableadgroupcriterion.md#finalurlsuffix) element be included within each returned [BiddableAdGroupCriterion](biddableadgroupcriterion.md) object.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[GetAdGroupCriterionsByIds](getadgroupcriterionsbyids.md)  
