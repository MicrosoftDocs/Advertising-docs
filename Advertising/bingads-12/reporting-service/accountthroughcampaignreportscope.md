---
title: AccountThroughCampaignReportScope Data Object - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the set of accounts and campaigns to include in the report.
---
# AccountThroughCampaignReportScope Data Object - Reporting
Defines the set of accounts and campaigns to include in the report.

The report scope includes a union of the included [AccountIds](#accountids) and [Campaigns](#campaigns) elements.

## Syntax
```xml
<xs:complexType name="AccountThroughCampaignReportScope" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AccountIds" nillable="true" type="q2:ArrayOflong" xmlns:q2="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
    <xs:element minOccurs="0" name="Campaigns" nillable="true" type="tns:ArrayOfCampaignReportScope" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountids"></a>AccountIds|A list of up to 1,000 account identifiers to include in the report.|**long** array|
|<a name="campaigns"></a>Campaigns|A list of up to 300 campaigns to include in the report.|[CampaignReportScope](campaignreportscope.md) array|

## Requirements
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v12/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v12  

## Used By
[BudgetSummaryReportRequest](budgetsummaryreportrequest.md)  
[CampaignPerformanceReportRequest](campaignperformancereportrequest.md)  
