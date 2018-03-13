---
title: ConversionGoalRevenueType Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines conversion goal revenue models that you can use to track how much each conversion is worth to your business.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# ConversionGoalRevenueType Value Set - Campaign Management
Defines conversion goal revenue models that you can use to track how much each conversion is worth to your business.   

## Syntax
```xml
<xs:simpleType name="ConversionGoalRevenueType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="FixedValue" />
    <xs:enumeration value="VariableValue" />
    <xs:enumeration value="NoValue" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="fixedvalue"></a>FixedValue|Each time it happens, the conversion has the same value.|
|<a name="novalue"></a>NoValue|Don't assign a value for the conversion.|
|<a name="variablevalue"></a>VariableValue|The value of the conversion may vary for example, by purchase price. You'll need to customize your UET tag tracking code to report variable revenue. For more information, see [How to report variable revenue with UET](https://help.bingads.microsoft.com/#apex/3/en/56687/2/en/#ext:none).|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[ConversionGoalRevenue](conversiongoalrevenue.md)  
