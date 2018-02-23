---
title: EditorialReason Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that you can use to determine the component of an ad or keyword that failed editorial review, and the reason for the failure.
---
# EditorialReason Data Object - Campaign Management
Defines an object that you can use to determine the component of an ad or keyword that failed editorial review, and the reason for the failure.

## Syntax
```xml
<xs:complexType name="EditorialReason" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Location" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="PublisherCountries" nillable="true" type="q38:ArrayOfstring" xmlns:q38="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
    <xs:element minOccurs="0" name="ReasonCode" type="xs:int" />
    <xs:element minOccurs="0" name="Term" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="location"></a>Location|The component of the ad or keyword that failed editorial review.|**string**|
|<a name="publishercountries"></a>PublisherCountries|A list of countries where the ad or keyword failed editorial review. Each string in the list contains a two character country code.|**string** array|
|<a name="reasoncode"></a>ReasonCode|A code that identifies the reason for the failure. For a list of possible reason codes, see [Editorial Failure Reason Codes](../guides/editorial-failure-reason-codes.md).|**int**|
|<a name="term"></a>Term|The term that failed editorial review.<br /><br />This element cannot be set if a combination of terms caused the failure or if the failure was based on a policy violation.|**string**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[EditorialReasonCollection](editorialreasoncollection.md)  
