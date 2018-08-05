---
title: ResponsiveAd Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: A responsive ad format for Audience ads in the Microsoft Audience Network.
---
# ResponsiveAd Data Object - Campaign Management
A responsive ad format for Audience ads in the Microsoft Audience Network. 

Responsive ads automatically adjust to accommodate the sizes and shapes of native ad formats.

> [!NOTE]
> Not everyone is enabled for Audience campaigns in the Microsoft Audience Network yet. If you don't, don't worry. It's coming soon. 

## Syntax
```xml
<xs:complexType name="ResponsiveAd" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Ad">
      <xs:sequence>
        <xs:element name="BusinessName" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="CallToAction" nillable="true" type="tns:CallToAction" />
        <xs:element name="Headline" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="LandscapeImageMediaId" nillable="true" type="xs:long" />
        <xs:element minOccurs="0" name="LandscapeLogoMediaId" nillable="true" type="xs:long" />
        <xs:element name="LongHeadline" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="SquareImageMediaId" nillable="true" type="xs:long" />
        <xs:element minOccurs="0" name="SquareLogoMediaId" nillable="true" type="xs:long" />
        <xs:element name="Text" nillable="true" type="xs:string" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="businessname"></a>BusinessName|The name of the business.<br/><br/>Depending on your audience ad's placement, your business's name may appear in your ad.<br/><br/>The length of the string is limited to 25 characters.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="calltoaction"></a>CallToAction|A brief, punchy reason for customers to click your ad right now.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|[CallToAction](calltoaction.md)|
|<a name="headline"></a>Headline|This is one of two possible headlines that could appear in your audience ads.<br/><br/>Because audience ads are responsive, we require multiple headlines so they can flexibly serve across a variety of publishers and placements.<br/><br/>The length of the string is limited to 25 characters.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="landscapeimagemediaid"></a>LandscapeImageMediaId|This is the identifier of the media corresponding to one of two possible aspect ratios for images that could appear in your audience ads.<br/><br/>Because audience ads are responsive, we require multiple images so they can flexibly display across a variety of publishers and placements.<br/><br/>Wide or landscape images have an aspect ratio of 1.91:1.<br/><br/>Media for responsive ads are provisioned via the [Image](image.md) object using the Campaign Management service. When you call the [AddMedia](addmedia.md) operation, make sure that your media adheres to the supported dimensions and aspect ratio. For more information see [Image Data Object Remarks](image.md#remarks).<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**long**|
|<a name="landscapelogomediaid"></a>LandscapeLogoMediaId|This is the identifier of the media corresponding to one of two possible aspect ratios for logos that could appear in your audience ads.<br/><br/>Because audience ads are responsive, we require multiple logos so they can flexibly display across a variety of publishers and placements.<br/><br/>Wide or landscape logos have an aspect ratio of 1.91:1.<br/><br/>Media for responsive ads are provisioned via the [Image](image.md) object using the Campaign Management service. When you call the [AddMedia](addmedia.md) operation, make sure that your media adheres to the supported dimensions and aspect ratio. For more information see [Image Data Object Remarks](image.md#remarks).<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**long**|
|<a name="longheadline"></a>LongHeadline|This is one of two possible headlines that could appear in your audience ads.<br/><br/>Because audience ads are responsive, we require multiple headlines so they can flexibly serve across a variety of publishers and placements.<br/><br/>The length of the string is limited to 90 characters.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="squareimagemediaid"></a>SquareImageMediaId|This is one of two possible aspect ratios for images that could appear in your audience ads.<br/><br/>Because audience ads are responsive, we require multiple images so they can flexibly display across a variety of publishers and placements.<br/><br/>Square images have an aspect ratio of 1:1.<br/><br/>Media for responsive ads are provisioned via the [Image](image.md) object using the Campaign Management service. When you call the [AddMedia](addmedia.md) operation, make sure that your media adheres to the supported dimensions and aspect ratio. For more information see [Image Data Object Remarks](image.md#remarks).<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**long**|
|<a name="squarelogomediaid"></a>SquareLogoMediaId|This is one of two possible aspect ratios for logos that could appear in your audience ads.<br/><br/>Because audience ads are responsive, we require multiple logos so they can flexibly display across a variety of publishers and placements.<br/><br/>Square logos have an aspect ratio of 1:1.<br/><br/>Media for responsive ads are provisioned via the [Image](image.md) object using the Campaign Management service. When you call the [AddMedia](addmedia.md) operation, make sure that your media adheres to the supported dimensions and aspect ratio. For more information see [Image Data Object Remarks](image.md#remarks).<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**long**|
|<a name="text"></a>Text|Depending on your audience ad's placement, this text will appear below or adjacent to your ad's long or short headline.<br/><br/>You have more character space to work with in the ad text than in the headline. So once the imagery and headline have a potential customer's attention, the ad text needs to convince them to click it. What sets your product or service apart?<br/><br/>The text must contain at least one word.<br/><br/>The length of the string is limited to 90 characters.<br/><br/>The text cannot contain the newline (\n) character.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|

The [ResponsiveAd](responsivead.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsad"></a>Inherited Elements from Ad
The [ResponsiveAd](responsivead.md) object derives from the [Ad](ad.md) object, and inherits the following elements. The descriptions below are specific to [ResponsiveAd](responsivead.md), and might not apply to other objects that inherit the same elements from the [Ad](ad.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adformatpreference"></a>AdFormatPreference|This element is not applicable for responsive ads.|**string**|
|<a name="devicepreference"></a>DevicePreference|This element is not applicable for responsive ads.|**long**|
|<a name="editorialstatus"></a>EditorialStatus|The editorial review status of the ad, which indicates whether the ad is pending review, has been approved, or has been disapproved.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AdEditorialStatus](adeditorialstatus.md)|
|<a name="finalappurls"></a>FinalAppUrls|This element is not applicable for responsive ads.|[AppUrl](appurl.md) array|
|<a name="finalmobileurls"></a>FinalMobileUrls|The mobile landing page URL.<br/><br/>The following validation rules apply to Final URLs and Final Mobile URLs.<br/>- The length of the URL is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.<br/>- You may specify up to 10 items for both [FinalUrls](#finalurls) and [FinalMobileUrls](#finalmobileurls); however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.<br/>- Usage of '{' and '}' is only allowed to delineate tags, for example *{lpurl}*.<br/>- Final URLs must each be a well-formed URL starting with either http:// or https://.<br/>- If you specify [FinalMobileUrls](#finalmobileurls), you must also specify [FinalUrls](#finalurls).<br/>- You may not specify [FinalMobileUrls](#finalmobileurls) if the device preference is set to mobile.<br/><br/>This URL is used only if the keyword does not specify a final mobile URL.<br/><br/>**Add:** Optional<br/>**Update:** Optional|**string** array|
|<a name="finalurls"></a>FinalUrls|The landing page URL.<br/><br/>The domain portion of the URL in combination with the path 1 and path 2 strings cannot exceed 67 characters.<br/><br/>The following validation rules apply to Final URLs and Final Mobile URLs.<br/>- The length of the URL is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.<br/>- You may specify up to 10 items for both [FinalUrls](#finalurls) and [FinalMobileUrls](#finalmobileurls); however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.<br/>- Usage of '{' and '}' is only allowed to delineate tags, for example *{lpurl}*.<br/>- Final URLs must each be a well-formed URL starting with either http:// or https://.<br/>- If you specify [FinalMobileUrls](#finalmobileurls), you must also specify [FinalUrls](#finalurls).<br/>- You may not specify [FinalMobileUrls](#finalmobileurls) if the device preference is set to mobile. Also note that  if this ad's *TrackingUrlTemplate* or *UrlCustomParameters* element are set, then at least one final URL is required.<br/><br/>This URL is used only if the keyword does not specify a final URL.<br/><br/>**Add:** Required<br/>**Update:** Required|**string** array|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br/><br/>Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for this object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The unique Bing Ads identifier of the ad.<br/><br/>**Add:** Read-only<br/>**Update:** Required and Read-Only|**long**|
|<a name="status"></a>Status|The status of the ad.<br/><br/>You can set the ad status to Active or Paused.<br/><br/>**Add:** Optional<br/>**Update:** Optional|[AdStatus](adstatus.md)|
|<a name="trackingurltemplate"></a>TrackingUrlTemplate|The tracking template to use as a default for all landing page URLs.<br/><br/>The following validation rules apply to tracking templates. For more details about supported templates and parameters, see the Bing Ads help article [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2)<br/>- Tracking templates defined for lower level entities e.g. ads override those set for higher level entities e.g. campaign. For more information, see [Entity Hierarchy and Limits](../guides/entity-hierarchy-limits.md).<br/>- The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.<br/>- The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*.<br/>- Bing Ads does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the landing page URL will include the key and value placeholders of your custom parameters without substitution. For example, if your tracking template is *http://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}* and neither *{_season}* or *{_promocode}* are defined at the campaign, ad group, criterion, keyword, or ad level, then the landing page URL will be the same.<br/><br/>**Add:** Optional<br/>**Update:** Optional|**string**|
|<a name="type"></a>Type|The type of the ad. This value is *ResponsiveAd* when you retrieve a responsive ad. For more information about ad types, see the [Ad Data Object Remarks](ad.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AdType](adtype.md)|
|<a name="urlcustomparameters"></a>UrlCustomParameters|Your custom collection of key and value parameters for URL tracking.<br/><br/>You may include up to 3 individual [CustomParameter](customparameter.md) objects within the [CustomParameters](customparameters.md) object. Each [CustomParameter](customparameter.md) contains a *Key* and *Value* element.<br/><br/>On update, set the *UrlCustomParameters* element to null or empty to retain any existing custom parameters. To remove all custom parameters, set the *Parameters* element of the [CustomParameters](customparameters.md) object to null or empty. To remove a subset of custom parameters, specify the custom parameters that you want to keep in the *Parameters* element of the [CustomParameters](customparameters.md) object.<br/><br/>**Add:** Optional<br/>**Update:** Optional|[CustomParameters](customparameters.md)|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

