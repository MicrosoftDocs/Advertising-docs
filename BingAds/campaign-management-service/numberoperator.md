---
title: NumberOperator Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: "article"
author: eric-urban
ms.author: eur
description: Defines the operators that can be applied to remarketing list rule item number values.
---
# NumberOperator Value Set - Campaign Management
Defines the operators that can be applied to remarketing list rule item number values.

## Syntax
```xml
<xs:simpleType name="NumberOperator" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="None" />
    <xs:enumeration value="Equals" />
    <xs:enumeration value="GreaterThan" />
    <xs:enumeration value="LessThan" />
    <xs:enumeration value="GreaterThanEqualTo" />
    <xs:enumeration value="LessThanEqualTo" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="equals"></a>Equals|Equals the corresponding number value.|
|<a name="greaterthan"></a>GreaterThan|Greater than the corresponding number value.|
|<a name="greaterthanequalto"></a>GreaterThanEqualTo|Greater than or equal to the corresponding number value.|
|<a name="lessthan"></a>LessThan|Less than the corresponding number value.|
|<a name="lessthanequalto"></a>LessThanEqualTo|Less than or equal to the corresponding number value.|
|<a name="none"></a>None|Reserved for future use.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[CustomEventsRule](customeventsrule.md)  
