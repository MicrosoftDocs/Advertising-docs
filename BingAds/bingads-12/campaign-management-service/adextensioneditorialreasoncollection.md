---
title: AdExtensionEditorialReasonCollection Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a collection of ad extensions that failed editorial review.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# AdExtensionEditorialReasonCollection Data Object - Campaign Management
Defines a collection of ad extensions that failed editorial review.

## Syntax
```xml
<xs:complexType name="AdExtensionEditorialReasonCollection" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AdExtensionId" type="xs:long" />
    <xs:element minOccurs="0" name="Reasons" nillable="true" type="tns:ArrayOfAdExtensionEditorialReason" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adextensionid"></a>AdExtensionId|The identifier of the ad extension that failed editorial review.|**long**|
|<a name="reasons"></a>Reasons|A list of *AdExtensionEditorialReason* objects that identify the component of an ad extension that failed editorial review, and the reason for the failure.|[AdExtensionEditorialReason](adextensioneditorialreason.md) array|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[GetAdExtensionsEditorialReasons](getadextensionseditorialreasons.md)  
