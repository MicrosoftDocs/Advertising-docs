---
title: EntityScope Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines values that you can use to determine whether the remarketing list can only be associated with ad groups within one specified account, or can be associated with any ad groups across all of the customer's accounts.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# EntityScope Value Set - Campaign Management
Defines values that you can use to determine whether the remarketing list can only be associated with ad groups within one specified account, or can be associated with any ad groups across all of the customer's accounts.

## Syntax
```xml
<xs:simpleType name="EntityScope" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Account" />
    <xs:enumeration value="Customer" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="account"></a>Account|The remarketing list can only be associated with ad groups within one specified account.|
|<a name="customer"></a>Customer|The remarketing list can be associated with any ad groups across all of the customer's accounts.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[Audience](audience.md)  
[ConversionGoal](conversiongoal.md)  
