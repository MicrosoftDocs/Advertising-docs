---
title: EditorialReasonCollection Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a collection of ads or keywords that failed editorial review, and the reason for the failure.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# EditorialReasonCollection Data Object - Campaign Management
Defines a collection of ads or keywords that failed editorial review, and the reason for the failure.

## Syntax
```xml
<xs:complexType name="EditorialReasonCollection" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AdGroupId" type="xs:long" />
    <xs:element minOccurs="0" name="AdOrKeywordId" type="xs:long" />
    <xs:element minOccurs="0" name="AppealStatus" type="tns:AppealStatus" />
    <xs:element minOccurs="0" name="Reasons" nillable="true" type="tns:ArrayOfEditorialReason" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupid"></a>AdGroupId|Identifies the ad group which is the parent of the ad or keyword that failed editorial review.|**long**|
|<a name="adorkeywordid"></a>AdOrKeywordId|Identifies the ad or keyword that failed editorial review.|**long**|
|<a name="appealstatus"></a>AppealStatus|A value that determines whether you can appeal the issues found by the editorial review.|[AppealStatus](appealstatus.md)|
|<a name="reasons"></a>Reasons|An array of editorial reasons that you can use to determine the component of an ad or keyword that failed editorial review, and the reason for the failure.|[EditorialReason](editorialreason.md) array|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[GetEditorialReasonsByIds](geteditorialreasonsbyids.md)  
