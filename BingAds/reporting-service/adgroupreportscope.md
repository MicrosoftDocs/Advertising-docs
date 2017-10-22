---
title: AdGroupReportScope Data Object - Reporting
ms.service: bing-ads-reporting-service
ms.topic: "article"
ms.date: 11/1/2017
author: eric-urban
ms.author: eur
description: Defines an ad group to include in the report.
---
# AdGroupReportScope Data Object - Reporting
Defines an ad group to include in the report.

## Syntax
```xml
<xs:complexType name="AdGroupReportScope" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element name="AccountId" type="xs:long" />
    <xs:element name="CampaignId" type="xs:long" />
    <xs:element name="AdGroupId" type="xs:long" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The identifier of the account that the ad group belongs to.|**long**|
|<a name="adgroupid"></a>AdGroupId|The identifier of the ad group to limit the scope to.|**long**|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign that the ad group belongs to.|**long**|

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https://bingads.microsoft.com/Reporting/v11  

## Used By
[AccountThroughAdGroupReportScope](accountthroughadgroupreportscope.md)  
