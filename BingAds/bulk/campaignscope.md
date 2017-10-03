---
title: CampaignScope Data Object
ms.service: bing-ads-bulk
ms.topic: article
author: eric-urban
ms.author: eur
---
# CampaignScope Data Object
Defines an object that identifies a campaign to download.

## Syntax
```xml
<xs:complexType name="CampaignScope" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="CampaignId" type="xs:long" />
    <xs:element minOccurs="0" name="ParentAccountId" type="xs:long" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign to download.|**long**|
|<a name="parentaccountid"></a>ParentAccountId|	The identifier of the account that owns the campaign to download.|**long**|

## Requirements
Service: [BulkService.svc v11](https://bulk.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/BulkService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md)  
