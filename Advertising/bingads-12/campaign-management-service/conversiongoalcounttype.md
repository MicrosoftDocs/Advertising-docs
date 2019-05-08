---
title: ConversionGoalCountType Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines how your conversions are recorded within your chosen conversion window.
---
# ConversionGoalCountType Value Set - Campaign Management
Defines how your conversions are recorded within your chosen conversion window.

For example, you track two conversions: leads and sales. You pick *Unique* for leads and *All* for sales. When one ad click turns into two leads and two sales, it's counted as three conversions: one for the unique lead, and two for all the sales. 

## Syntax
```xml
<xs:simpleType name="ConversionGoalCountType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="All" />
    <xs:enumeration value="Unique" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="all"></a>All|All conversions that happen after an ad click will be counted. This is a common choice for sales.|
|<a name="unique"></a>Unique|Only one conversion that happens after an ad click will be counted. This is a common choice for leads.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[ConversionGoal](conversiongoal.md)  
