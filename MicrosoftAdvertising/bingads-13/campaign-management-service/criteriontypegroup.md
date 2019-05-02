---
title: CriterionTypeGroup Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: The type used to group criterions.
---
# CriterionTypeGroup Value Set - Campaign Management
The type used to group criterions.

You can use one of the criterion type group values in each [TargetSettingDetail](targetsettingdetail.md) object to determine whether to use the "target and bid" option or the "bid only" target option for that campaign or ad group. For supported criterion type groups per campaign type, see [TargetSettingDetail Remarks](targetsettingdetail.md#remarks).

## Syntax
```xml
<xs:simpleType name="CriterionTypeGroup" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Unknown" />
    <xs:enumeration value="Gender" />
    <xs:enumeration value="Age" />
    <xs:enumeration value="Audience" />
    <xs:enumeration value="CompanyName" />
    <xs:enumeration value="JobFunction" />
    <xs:enumeration value="Industry" />
    <xs:enumeration value="IncomeRange" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="age"></a>Age|The age criterion type group.|
|<a name="audience"></a>Audience|The audience criterion type group.|
|<a name="companyname"></a>CompanyName|The company name criterion type group.|
|<a name="gender"></a>Gender|The gender criterion type group.|
|<a name="incomerange"></a>IncomeRange|Reserved for future use.|
|<a name="industry"></a>Industry|The industry criterion type group.|
|<a name="jobfunction"></a>JobFunction|The job function criterion type group.|
|<a name="unknown"></a>Unknown|Reserved for future use.|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[TargetSettingDetail](targetsettingdetail.md)  
