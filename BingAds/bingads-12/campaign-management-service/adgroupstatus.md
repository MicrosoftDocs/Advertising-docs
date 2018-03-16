---
title: AdGroupStatus Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible status values of an ad group.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# AdGroupStatus Value Set - Campaign Management
Defines the possible status values of an ad group.

## Syntax
```xml
<xs:simpleType name="AdGroupStatus" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Active" />
    <xs:enumeration value="Paused" />
    <xs:enumeration value="Expired" />
    <xs:enumeration value="Deleted" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="active"></a>Active|The ad group is active, which indicates that the ad group's ads can be served.|
|<a name="deleted"></a>Deleted|This status is for internal use only. Because all Get operations do not return deleted objects, you will not see an object with this status.|
|<a name="expired"></a>Expired|The ad group expired. This status is set if you specify an end date for the ad group and the end date passes.|
|<a name="paused"></a>Paused|The ad group is paused, which indicates that the ad group's ads will not serve. Ads and keywords that you add in this state are subject to editorial review.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[AdGroup](adgroup.md)  
