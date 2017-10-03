---
title: AdGroupCriterionStatus Value Set
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# AdGroupCriterionStatus Value Set
Defines the possible ad group criterion status values.

## Syntax
```xml
<xs:simpleType name="AdGroupCriterionStatus" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Active" />
    <xs:enumeration value="Paused" />
    <xs:enumeration value="Deleted" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="active"></a>Active|The criterion is active.|
|<a name="deleted"></a>Deleted|The criterion was deleted. Note that the *Get* operations will not return deleted objects.|
|<a name="paused"></a>Paused|The criterion is paused.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[AdGroupCriterion](adgroupcriterion.md)  
