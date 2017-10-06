---
title: DynamicSearchAdsSetting Data Object
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the campaign level settings for a Dynamic Search Ads campaign.
---
# DynamicSearchAdsSetting Data Object
Defines the campaign level settings for a Dynamic Search Ads campaign.

> [!NOTE]
> Not everyone has this feature yet. If you don?t, don?t worry. It?s coming soon.

## Syntax
```xml
<xs:complexType name="DynamicSearchAdsSetting" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Setting">
      <xs:sequence>
        <xs:element minOccurs="0" name="DomainName" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="Language" nillable="true" type="xs:string" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="domainname"></a>DomainName|The domain name of the website that you want to target for dynamic search ads.<br/><br/>The length of the string is limited to 2,048 characters. If the domain name includes *www* it will be trimmed and not used.<br/><br/>**Add:** Required<br/>**Update:** Read-only. You cannot update the domain name.|**string**|
|<a name="language"></a>Language|The language of the website pages that you want to target for dynamic search ads. Currently the only supported language code is 'en'.<br/><br/>**Add:** Required<br/>**Update:** Read-only. You cannot update the language.|**string**|

The [DynamicSearchAdsSetting](dynamicsearchadssetting.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementssetting"></a>Inherited Elements from Setting
The [DynamicSearchAdsSetting](dynamicsearchadssetting.md) object derives from the [Setting](setting.md) object, and inherits the following elements. The descriptions below are specific to [DynamicSearchAdsSetting](dynamicsearchadssetting.md), and might not apply to other objects that inherit the same elements from the [Setting](setting.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of the setting. This value is *DynamicSearchAds* when you retrieve a dynamic search ads setting. For more information about setting types, see the [Setting Data Object Remarks](../campaign-management-service/setting.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

