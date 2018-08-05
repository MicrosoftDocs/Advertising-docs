---
title: CustomParameter Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a key and value custom parameter for URL tracking.
---
# CustomParameter Data Object - Campaign Management
Defines a key and value custom parameter for URL tracking. Used for campaign, ad group, ad, keyword, sitelink, and ad group criterion URL custom parameters.

## Syntax
```xml
<xs:complexType name="CustomParameter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Key" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Value" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="key"></a>Key|The name of the custom parameter that you want to track.<br/><br/>The maximum length of this string is 16, in UTF-8 bytes. With the Campaign Management service you may not specify special characters such as braces and underscore: \"\{\", \"\_\", and \"\}\".  With the Bulk service the surrounding braces and underscore are required. The maximum length of 16 UTF-8 bytes does not include the optional braces and underscore: \"\{\", \"\_\", and \"\}\".<br/><br/>**Add:** Required<br/>**Update:** Required|**string**|
|<a name="value"></a>Value|The value to track using your custom parameter.<br/><br/>The maximum length of this string is 200, in UTF-8 bytes.<br/><br/>**Add:** Required<br/>**Update:** Required|**string**|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[CustomParameters](customparameters.md)  
