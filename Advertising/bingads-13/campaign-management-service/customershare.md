---
title: CustomerShare Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Reserved for future use.
---
# CustomerShare Data Object - Campaign Management
Reserved for future use.

## Syntax
```xml
<xs:complexType name="CustomerShare" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="CustomerAccountShares" nillable="true" type="tns:ArrayOfCustomerAccountShare" />
    <xs:element minOccurs="0" name="OwnerCustomerId" nillable="true" type="xs:long" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="customeraccountshares"></a>CustomerAccountShares|Reserved for future use.|[CustomerAccountShare](customeraccountshare.md) array|
|<a name="ownercustomerid"></a>OwnerCustomerId|Reserved for future use.|**long**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[Audience](audience.md)  
[UetTag](uettag.md)  
