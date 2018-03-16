---
title: AdGroupCriterionEditorialStatus Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the editorial review status values of an ad group criterion.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# AdGroupCriterionEditorialStatus Value Set - Campaign Management
Defines the editorial review status values of an ad group criterion.

## Syntax
```xml
<xs:simpleType name="AdGroupCriterionEditorialStatus" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Active" />
    <xs:enumeration value="Disapproved" />
    <xs:enumeration value="Inactive" />
    <xs:enumeration value="ActiveLimited" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="active"></a>Active|The criterion passed editorial review.|
|<a name="activelimited"></a>ActiveLimited|The criterion passed editorial review in one or more markets, and one or more elements of the criterion is undergoing editorial review in another market. For example the criterion passed editorial review for Canada and is still pending review in the United States.|
|<a name="disapproved"></a>Disapproved|The criterion failed editorial review.|
|<a name="inactive"></a>Inactive|The criterion is undergoing editorial review.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[BiddableAdGroupCriterion](biddableadgroupcriterion.md)  
