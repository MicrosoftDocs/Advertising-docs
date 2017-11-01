---
title: AccountThroughCampaignReportScope Data Object - Reporting
ms.service: bing-ads-reporting-service
ms.topic: "article"
ms.date: 11/01/2017
author: eric-urban
ms.author: eur
description: Defines the set of accounts and campaigns to include in the report.
---
# AccountThroughCampaignReportScope Data Object - Reporting
Defines the set of accounts and campaigns to include in the report.

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
|<a name="accountids"></a>AccountIds|An array of account identifiers that identifies the account data to include in the report. You can specify a maximum of 1,000 account identifiers.|**long**|
|<a name="campaigns"></a>Campaigns|An array of *CampaignReportScope* objects that identifies the campaign data to include in the report. You can specify a maximum of 300 campaign identifiers.|[CampaignReportScope](campaignreportscope.md) array|

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https://bingads.microsoft.com/Reporting/v11  

## Used By
[BudgetSummaryReportRequest](budgetsummaryreportrequest.md)  
[CampaignPerformanceReportRequest](campaignperformancereportrequest.md)  
