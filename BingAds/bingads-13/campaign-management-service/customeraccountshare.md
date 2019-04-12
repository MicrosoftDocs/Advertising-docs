---
title: CustomerAccountShare Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Reserved for future use.
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# CustomerAccountShare Data Object - Campaign Management
Reserved for future use.

## Syntax
```xml
<xs:complexType name="CustomerAccountShare" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AccountId" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="Associations" nillable="true" type="tns:ArrayOfCustomerAccountShareAssociation" />
    <xs:element minOccurs="0" name="CustomerId" nillable="true" type="xs:long" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|Reserved for future use.|**long**|
|<a name="associations"></a>Associations|Reserved for future use.|[CustomerAccountShareAssociation](customeraccountshareassociation.md) array|
|<a name="customerid"></a>CustomerId|Reserved for future use.|**long**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[CustomerShare](customershare.md)  
