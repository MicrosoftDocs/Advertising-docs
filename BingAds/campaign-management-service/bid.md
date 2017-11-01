---
title: Bid Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: "article"
author: eric-urban
ms.author: eur
description: Defines a bid.
---
# Bid Data Object - Campaign Management
Defines a bid.

## Syntax
```xml
<xs:complexType name="Bid" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Amount" nillable="true" type="xs:double" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="amount"></a>Amount|The bid value. For details about the valid bid range for your market, see [Currencies](~/guides/currencies.md).|**double**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[AdGroup](adgroup.md)  
[Keyword](keyword.md)  
[MaxClicksBiddingScheme](maxclicksbiddingscheme.md)  
[MaxConversionsBiddingScheme](maxconversionsbiddingscheme.md)  
[TargetCpaBiddingScheme](targetcpabiddingscheme.md)  
