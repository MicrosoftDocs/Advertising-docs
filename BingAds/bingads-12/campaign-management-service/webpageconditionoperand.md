---
title: WebpageConditionOperand Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the operands that can be applied to arguments of a webpage condition or criterion for dynamic search ads.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.
# WebpageConditionOperand Value Set - Campaign Management
Defines the operands that can be applied to arguments of a webpage condition or criterion for dynamic search ads. 

## Syntax
```xml
<xs:simpleType name="WebpageConditionOperand" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Unknown" />
    <xs:enumeration value="Url" />
    <xs:enumeration value="Category" />
    <xs:enumeration value="PageTitle" />
    <xs:enumeration value="PageContent" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="category"></a>Category|Set a condition that the argument must match one of the categories that Bing thinks is applicable for your site.|
|<a name="pagecontent"></a>PageContent|Set a condition that the argument must match any of your site's content that is indexed by Bing.|
|<a name="pagetitle"></a>PageTitle|Set a condition that the argument must match any of your site's page titles that are indexed by Bing.|
|<a name="unknown"></a>Unknown|Reserved for future use.|
|<a name="url"></a>Url|Set a condition that the argument must match any of your site's URLs that are indexed by Bing.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[WebpageCondition](webpagecondition.md)  
