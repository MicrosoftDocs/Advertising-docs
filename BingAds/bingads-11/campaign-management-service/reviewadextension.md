---
title: ReviewAdExtension Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that specifies third-party reviews (exact or paraphrased) about your business, products, or services to include in an expanded text ad.
---
# ReviewAdExtension Data Object - Campaign Management
Defines an object that specifies third-party reviews (exact or paraphrased) about your business, products, or services to include in an expanded text ad.

You can associate a review ad extension with the account or with campaigns and ad groups in the account. Each entity (account, campaign, or ad group) can be associated with up to 20 review ad extensions. An expanded text ad will only include one review per impression.

## Syntax
```xml
<xs:complexType name="ReviewAdExtension" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:AdExtension">
      <xs:sequence>
        <xs:element minOccurs="0" name="IsExact" type="xs:boolean" />
        <xs:element minOccurs="0" name="Source" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="Text" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="Url" nillable="true" type="xs:string" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="isexact"></a>IsExact|Determines whether the review text is an exact quote or paraphrased. <br/><br/>If not specified, the default value of false indicates that the review text is paraphrased from the source. If set to *True*, the review text will be surrounded automatically with quotation marks when displayed with the ad.<br/><br/>**Add:** Optional<br/>**Update:** Optional|**boolean**|
|<a name="source"></a>Source|The review source name.<br/><br/>The combined length of the *Source* and *Text* strings must not exceed 67 characters. Note that for Traditional Chinese characters, the combined length of the Source and Text *Source* and *Text* strings is limited to 33 characters.<br/><br/>**Add:** Required<br/>**Update:** Optional|**string**|
|<a name="text"></a>Text|The text that is either a paraphrase or an exact quote from the review source.<br/><br/>The combined length of the *Source* and *Text* strings must not exceed 67 characters. Note that for Traditional Chinese characters, the combined length of the Source and Text *Source* and *Text* strings is limited to 33 characters.<br/><br/> Do not surround the text with quotation marks. If *IsExact* is set to *True*, the review text will be surrounded automatically with quotation marks when displayed with the ad.<br/><br/>**Add:** Required<br/>**Update:** Optional|**string**|
|<a name="url"></a>Url|The review source Url.<br/><br/>The Url must begin with either the *http://* or *https://* prefix.<br/><br/>The length of this string is limited to 2,048 characters.<br/><br/>**Add:** Required<br/>**Update:** Optional|**string**|

The [ReviewAdExtension](reviewadextension.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsadextension"></a>Inherited Elements from AdExtension
The [ReviewAdExtension](reviewadextension.md) object derives from the [AdExtension](adextension.md) object, and inherits the following elements. The descriptions below are specific to [ReviewAdExtension](reviewadextension.md), and might not apply to other objects that inherit the same elements from the [AdExtension](adextension.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="devicepreference"></a>DevicePreference|Reserved for future use.|**long**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br />There are currently no forward compatibility changes for the *AdExtension* object.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The unique Bing Ads identifier of the ad extension.<br/><br/>**Add:** Read-only and Required<br/>**Update:** Read-only|**long**|
|<a name="scheduling"></a>Scheduling|Determines the calendar day and time ranges when the ad extension is eligible to be shown in ads.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If you set this element null, any existing scheduling set for the ad extension will remain unchanged. If you set this to any non-null [Schedule](schedule.md) object, you are effectively replacing existing scheduling settings for the ad extension. To remove all scheduling set this element to an empty [Schedule](schedule.md) object.|[Schedule](schedule.md)|
|<a name="status"></a>Status|The status of the ad extension. The value will always be *Active* because the Campaign Management service does not return deleted ad extensions.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AdExtensionStatus](adextensionstatus.md)|
|<a name="type"></a>Type|The type of the ad extension. This value is *ReviewAdExtension* when you retrieve a review ad extension. <br/><br/>**Add:** Read-only<br/>**Update:** Read-only<br/><br/>For more information about ad extension types, see the [Ad Extension Data Object Remarks](adextension.md#remarks).|**string**|
|<a name="version"></a>Version|The number of times the contents of the ad extension has been updated. The version is set to 1 when you add the extension and is incremented each time it's revised.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**int**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

