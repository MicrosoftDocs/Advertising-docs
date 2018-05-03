---
title: GenderType Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the genders that are available for gender criterion.
---
# GenderType Value Set - Campaign Management
Defines the genders that are available for gender criterion.

## Syntax
```xml
<xs:simpleType name="GenderType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Unknown" />
    <xs:enumeration value="Male" />
    <xs:enumeration value="Female" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="female"></a>Female|The gender is female.|
|<a name="male"></a>Male|The gender is male.|
|<a name="unknown"></a>Unknown|The gender is not known.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[GenderCriterion](gendercriterion.md)  
