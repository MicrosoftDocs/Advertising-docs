---
title: BidOption Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Determines whether or not to amplify your partner's bid.
---
# BidOption Value Set - Campaign Management
Determines whether or not to amplify your partner's bid.

## Syntax
```xml
<xs:simpleType name="BidOption" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="BidValue" />
    <xs:enumeration value="BidBoost" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="bidboost"></a>BidBoost|A bid boost allows you to amplify your partner's bid.|
|<a name="bidvalue"></a>BidValue|A bid value ad group allows you to bid on products that your merchandising partner doesn't target.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[CoOpSetting](coopsetting.md)  
