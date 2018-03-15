---
title: Network Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible search networks on which an ad can display.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# Network Value Set - Campaign Management
Defines the possible search networks on which an ad can display.
For more information about networks and ad distribution, see the [About Ad Distribution](http://help.bingads.microsoft.com/#apex/3/en/50871/0) help article.

## Syntax
```xml
<xs:simpleType name="Network" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="OwnedAndOperatedAndSyndicatedSearch" />
    <xs:enumeration value="OwnedAndOperatedOnly" />
    <xs:enumeration value="SyndicatedSearchOnly" />
    <xs:enumeration value="InHousePromotion" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="inhousepromotion"></a>InHousePromotion|Reserved.|
|<a name="ownedandoperatedandsyndicatedsearch"></a>OwnedAndOperatedAndSyndicatedSearch|Display ads on owned and operated networks, as well as syndicated search networks.|
|<a name="ownedandoperatedonly"></a>OwnedAndOperatedOnly|Display ads on only owned and operated networks.<br /><br />Owned and operated networks refer to the Bing, AOL, and Yahoo search networks.|
|<a name="syndicatedsearchonly"></a>SyndicatedSearchOnly|Display ads on only syndicated search networks.<br /><br />Syndicated search refers to partner sites that host Bing, AOL, and Yahoo search.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[AdGroup](adgroup.md)  
