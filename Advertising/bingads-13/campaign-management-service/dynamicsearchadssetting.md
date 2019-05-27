---
title: DynamicSearchAdsSetting Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the campaign level settings for a Dynamic Search Ads campaign.
---
# DynamicSearchAdsSetting Data Object - Campaign Management
Defines the campaign level settings for a Dynamic Search Ads campaign.

## Syntax
```xml
<xs:complexType name="DynamicSearchAdsSetting" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Setting">
      <xs:sequence>
        <xs:element minOccurs="0" name="DomainName" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="Language" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="PageFeedIds" nillable="true" type="q6:ArrayOflong" xmlns:q6="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
        <xs:element minOccurs="0" name="Source" nillable="true" type="tns:DynamicSearchAdsSource" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="domainname"></a>DomainName|The domain name of the website that you want to target for dynamic search ads.<br/><br/>The length of the string is limited to 2,048 characters. If the domain name includes *www* it will be trimmed and not used.<br/><br/>**Add:** Required<br/>**Update:** Read-only. You cannot update the domain name.|**string**|
|<a name="language"></a>Language|The language of the website pages that you want to target for dynamic search ads.<br/><br/>Your website language determines where your ads are eligible to appear. For example, a German-language ad can appear in Germany, Austria, and Switzerland, but not in Spain. The supported languages are English, French, and German. If your website contains pages in multiple languages and you want to advertise all of these pages, you should create a separate campaign for each language.<br/><br/>Note, if you set the campaign [Languages](campaign.md#languages) or ad group [Language](adgroup.md#language), they will be ignored.<br/><br/>**Add:** Required<br/>**Update:** Read-only. You cannot update the language.|**string**|
|<a name="pagefeedids"></a>PageFeedIds|Reserved for future use.|**long** array|
|<a name="source"></a>Source|Determines whether to use Bing's index, advertiser supplied URLs, or both.<br/><br/>By default only Bing's index is used.<br/><br/>Although you can manage the page feeds source and custom labels via Bing Ads API, page feeds upload is only supported through the Microsoft Advertising web application. For more details about uploading page feeds, see the [About dynamic search ads page feeds](https://help.ads.microsoft.com/#apex/3/en/60010/0) help article.<br/><br/>**Add:** Optional<br/>**Update:** Optional|[DynamicSearchAdsSource](dynamicsearchadssource.md)|

The [DynamicSearchAdsSetting](dynamicsearchadssetting.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementssetting"></a>Inherited Elements from Setting
The [DynamicSearchAdsSetting](dynamicsearchadssetting.md) object derives from the [Setting](setting.md) object, and inherits the following elements. The descriptions below are specific to [DynamicSearchAdsSetting](dynamicsearchadssetting.md), and might not apply to other objects that inherit the same elements from the [Setting](setting.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of the setting. This value is *DynamicSearchAds* when you retrieve a dynamic search ads setting. For more information about setting types, see the [Setting Data Object Remarks](setting.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

