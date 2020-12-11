---
title: CampaignReportScope Data Object - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a campaign to include in the report.
---
# CampaignReportScope Data Object - Reporting
Defines a campaign to include in the report.

## Syntax
```xml
<xs:complexType name="CampaignReportScope" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element name="AccountId" type="xs:long" />
    <xs:element name="CampaignId" type="xs:long" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [CampaignReportScope](campaignreportscope.md) object has the following elements: [AccountId](#accountid), [CampaignId](#campaignid).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The identifier of the account that the campaign belongs to.|**long**|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign to limit the scope to.|**long**|

## Requirements
Service: [ReportingService.svc v13](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v13/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v13  

## Used By
[AccountThroughAdGroupReportScope](accountthroughadgroupreportscope.md)  
[AccountThroughCampaignReportScope](accountthroughcampaignreportscope.md)  
