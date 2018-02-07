---
title: IdCollection Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains a list of entity identifiers.
---
# IdCollection Data Object - Campaign Management

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

Defines an object that contains a list of entity identifiers.

## Syntax
```xml
<xs:complexType name="IdCollection" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Ids" nillable="true" type="q83:ArrayOfNullableOflong" xmlns:q83="http://schemas.datacontract.org/2004/07/System" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="ids"></a>Ids|A list of entity identifiers.|**long** array|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[AddNegativeKeywordsToEntities](addnegativekeywordstoentities.md)  
[GetCampaignIdsByBudgetIds](getcampaignidsbybudgetids.md)  
