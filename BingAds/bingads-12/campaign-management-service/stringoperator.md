---
title: StringOperator Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the operators that can be applied to remarketing list rule item string values.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# StringOperator Value Set - Campaign Management
Defines the operators that can be applied to remarketing list rule item string values.

## Syntax
```xml
<xs:simpleType name="StringOperator" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="None" />
    <xs:enumeration value="Equals" />
    <xs:enumeration value="Contains" />
    <xs:enumeration value="BeginsWith" />
    <xs:enumeration value="EndsWith" />
    <xs:enumeration value="NotEquals" />
    <xs:enumeration value="DoesNotContain" />
    <xs:enumeration value="DoesNotBeginWith" />
    <xs:enumeration value="DoesNotEndWith" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="beginswith"></a>BeginsWith|Begin with the corresponding string value.|
|<a name="contains"></a>Contains|Contain the corresponding string value.|
|<a name="doesnotbeginwith"></a>DoesNotBeginWith|Does not begin with the corresponding string value.|
|<a name="doesnotcontain"></a>DoesNotContain|Does not contain the corresponding string value.|
|<a name="doesnotendwith"></a>DoesNotEndWith|Does not end with the corresponding string value.|
|<a name="endswith"></a>EndsWith|Does not end with the corresponding string value.|
|<a name="equals"></a>Equals|Equals the corresponding string value.|
|<a name="none"></a>None|Reserved for future use.|
|<a name="notequals"></a>NotEquals|Does not equal the corresponding string value.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[CustomEventsRule](customeventsrule.md)  
[StringRuleItem](stringruleitem.md)  
