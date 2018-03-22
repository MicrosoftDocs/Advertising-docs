---
title: ImageAdExtension Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an ad extension that specifies an image with alternative text to include in an expanded text ad.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# ImageAdExtension Data Object - Campaign Management
Defines an ad extension that specifies an image with alternative text to include in an expanded text ad.

You can associate an image ad extension with the account or with campaigns and ad groups in the account. For each account, only 1,000 campaigns and 1,000 ad groups can be associated with image ad extensions. Each entity (account, campaign, or ad group) can be associated with up to 6 image ad extensions.

## Syntax
```xml
<xs:complexType name="ImageAdExtension" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:AdExtension">
      <xs:sequence>
        <xs:element name="AlternativeText" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="Description" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="DestinationUrl" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="FinalAppUrls" nillable="true" type="tns:ArrayOfAppUrl" />
        <xs:element minOccurs="0" name="FinalMobileUrls" nillable="true" type="q37:ArrayOfstring" xmlns:q37="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
        <xs:element minOccurs="0" name="FinalUrls" nillable="true" type="q38:ArrayOfstring" xmlns:q38="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
        <xs:element name="ImageMediaIds" nillable="true" type="q39:ArrayOflong" xmlns:q39="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
        <xs:element minOccurs="0" name="TrackingUrlTemplate" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="UrlCustomParameters" nillable="true" type="tns:CustomParameters" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="alternativetext"></a>AlternativeText|Alternative description of the image media for usability. If the image could not be displayed, the alternative text is used instead.<br /><br />The maximum length for this element is 35 characters.<br/><br/>**Add:** Optional<br/>**Update:** Optional|**string**|
|<a name="description"></a>Description|Description that can be used by the advertiser, agency, or account manager to track, label, or manage image media. This description is not displayed with the ad or image.<br /><br />The maximum length for this element is 100 characters.<br/><br/>**Add:** Optional<br/>**Update:** Optional|**string**|
|<a name="destinationurl"></a>DestinationUrl|The URL of the webpage to take the user to when they click the image.<br /><br />The URL can contain dynamic text strings such as {keyword}. For more information, see [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2).<br /><br />The URL can contain a maximum of 1,024 characters. If the URL does not specify a protocol, the system uses the HTTP protocol when a user clicks the ad. If the URL specifies the HTTP protocol when you add an ad, the service will remove the *http://* protocol string (the HTTP protocol string does not count against the 1,024 character limit); however, the service will not remove an HTTPS protocol string (https://) from the URL.<br /><br /> If the URL is not specified for the image ad extension, the URL of the ad is used.<br/><br/>**Add:** Optional<br/>**Update:** Optional|**string**|
|<a name="finalappurls"></a>FinalAppUrls|Reserved for future use.|[AppUrl](appurl.md) array|
|<a name="finalmobileurls"></a>FinalMobileUrls|Reserved for future use.|**string** array|
|<a name="finalurls"></a>FinalUrls|Reserved for future use.|**string** array|
|<a name="imagemediaids"></a>ImageMediaIds|The identifiers of the images to include in the ad. You may not specify media identifiers for more than one image of the same aspect ratio. In other words each of  the referenced images must have different aspect ratios.<br /><br />You can specify up to four (4) image media  identifiers. While the minimum required is one image media ID, in order to qualify for all native ad placements you must provide four image media identifiers, where each ID corresponds to an [Image](image.md) of one of the four supported [Media](media.md) types (aspect ratios). The supported aspect ratios for intent ads are 16:9, 1.5:1, 4:3, and 1.2:1. For more information see the [Image](image.md) data object reference documentation.<br /><br />You can get the identifier of each [Image](image.md) when you add them to the image library by calling the [AddMedia](addmedia.md) operation. Otherwise after the media has been added to your image library you can get the media identifiers with the [GetMediaMetaDataByAccountId](getmediametadatabyaccountid.md) operation.<br/><br/>**Add:** Required<br/>**Update:** Optional|**long** array|
|<a name="trackingurltemplate"></a>TrackingUrlTemplate|Reserved for future use.|**string**|
|<a name="urlcustomparameters"></a>UrlCustomParameters|Reserved for future use.|[CustomParameters](customparameters.md)|

The [ImageAdExtension](imageadextension.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsadextension"></a>Inherited Elements from AdExtension
The [ImageAdExtension](imageadextension.md) object derives from the [AdExtension](adextension.md) object, and inherits the following elements. The descriptions below are specific to [ImageAdExtension](imageadextension.md), and might not apply to other objects that inherit the same elements from the [AdExtension](adextension.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="devicepreference"></a>DevicePreference|Reserved for future use.|**long**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br />There are currently no forward compatibility changes for the *AdExtension* object.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The unique Bing Ads identifier of the ad extension.<br/><br/>**Add:** Read-only and Required<br/>**Update:** Read-only|**long**|
|<a name="scheduling"></a>Scheduling|This element is not supported for image ad extensions. Scheduling is supported for other ad extension types.|[Schedule](schedule.md)|
|<a name="status"></a>Status|The status of the ad extension. The value will always be *Active* because the Campaign Management service does not return deleted ad extensions.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AdExtensionStatus](adextensionstatus.md)|
|<a name="type"></a>Type|The type of the ad extension. This value is *ImageAdExtension* when you retrieve an image ad extension. <br/><br/>**Add:** Read-only<br/>**Update:** Read-only<br/><br/>For more information about ad extension types, see the [Ad Extension Data Object Remarks](adextension.md#remarks).|**string**|
|<a name="version"></a>Version|The number of times the contents of the ad extension has been updated. The version is set to 1 when you add the extension and is incremented each time it's revised.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**int**|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

