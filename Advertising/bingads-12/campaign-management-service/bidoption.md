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

> [!NOTE]
> This setting is only applicable for ad groups in Microsoft Shopping Campaigns that are setup for Sponsored Products. Sponsored Products are only available in the United States and are currently under open beta.

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
|<a name="bidboost"></a>BidBoost|A bid boost allows you to amplify your partner's bid.<br/><br/>You should only use BidBoost if your partner uses BidValue.|
|<a name="bidvalue"></a>BidValue|A bid value ad group allows you to bid on products that your merchandising partner doesn't target.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[CoOpSetting](coopsetting.md)  
