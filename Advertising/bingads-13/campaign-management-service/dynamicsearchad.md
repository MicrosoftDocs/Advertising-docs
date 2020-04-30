---
title: DynamicSearchAd Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a dynamic search ad.
---
# DynamicSearchAd Data Object - Campaign Management
Defines a dynamic search ad. With a dynamic search ads campaign, the ad title and display URL are generated automatically based on the website domain and language that you want to target. The combination of the Path1, Path2, and Text elements make the dynamic search ad unique.

> [!NOTE]
> This feature is currently available in Australia, Canada, France, Germany, the United Kingdom, and the United States.  

To get started with dynamic search ads, first you'll need to [add](addcampaigns.md) a new [Campaign](campaign.md) with its type set to *DynamicSearchAds*. When you create the campaign, you'll need to include a [DynamicSearchAdsSetting](dynamicsearchadssetting.md) that specifies the target website domain and language.

Next, [create](addadgroups.md) a new [AdGroup](adgroup.md) within the dynamic search ads campaign. You can add one or more [Webpage](webpage.md) criterion to each ad group that helps determine whether or not to serve dynamic search ads, by calling the [AddAdGroupCriterions](addadgroupcriterions.md) operation. 

If you want to exclude certain portions of your website, you can add negative [Webpage](webpage.md) criterion at the campaign and ad group level using the respective [AddCampaignCriterions](addcampaigncriterions.md) and [AddAdGroupCriterions](addadgroupcriterions.md) service operations. The negative [Webpage](webpage.md) criterion at the campaign level applies to all ad groups within the campaign; however, if you define ad group level negative [Webpage](webpage.md) criterion, the campaign criterion is ignored for that ad group. 

Whether the criterion is positive or negative, you can choose whether you want the criterion argument to match partial URLs, page content, page title, or categories that Bing thinks applies to your website. To discover the categories that you can use for [Webpage](webpage.md) criterion (positive or negative), use the [GetDomainCategories](../ad-insight-service/getdomaincategories.md) operation with the Ad Insight service.

Finally you can [add](addads.md) a [DynamicSearchAd](dynamicsearchad.md) to the ad group. The ad title and display URL are generated automatically based on the website domain and language that you want to target.

## Syntax
```xml
<xs:complexType name="DynamicSearchAd" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Ad">
      <xs:sequence>
        <xs:element minOccurs="0" name="Path1" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="Path2" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="Text" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="TextPart2" nillable="true" type="xs:string" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="path1"></a>Path1|The first part of the optional path that will be appended to the domain portion of your display URL. The display URL e.g. *www.contoso.com* will be generated from the domain of your display URL. Then if you have specified a value for *Path 1* it will be appended to the display URL. If you have also specified a value for *Path 2*, then it will also be appended to the display URL after *Path 1*. For example if your domain is *contoso.com*, *Path 1* is set to *subdirectory1*, and *Path 2* is set to *subdirectory2*, then the URL displayed will be *www.contoso.com/subdirectory1/subdirectory2*. <br/><br/>The maximum input length of the path is 15 characters. Note that for languages with double-width characters e.g. Traditional Chinese the maximum input length of the path is 7 characters. Although dynamic text substitution is supported for other ad types like Expanded Text ads, it is not supported for dynamic search ads.<br/><br/>The path cannot contain the forward slash (/) or newline (\n) characters.<br/><br/>If the path includes a space, it will be replaced with an underscore (_) when the ad is shown.<br/><br/>**Add:** Optional<br/>**Update:** Optional|**string**|
|<a name="path2"></a>Path2|The second part of the optional path that will be appended to the domain portion of your display URL. The display URL e.g. *www.contoso.com* will be generated from the domain of your dynamic search ads campaign level settings. Then if you have specified a value for *Path 1* it will be appended to the display URL. If you have also specified a value for *Path 2*, then it will also be appended to the display URL after *Path 1*. For example if your domain is *contoso.com*, *Path 1* is set to *subdirectory1*, and *Path 2* is set to *subdirectory2*, then the URL displayed will be *www.contoso.com/subdirectory1/subdirectory2*.<br/><br/>You can only specify *Path2* if *Path1* is also set. <br/><br/>The maximum input length of the path is 15 characters. Note that for languages with double-width characters e.g. Traditional Chinese the maximum input length of the path is 7 characters. Although dynamic text substitution is supported for other ad types like Expanded Text ads, it is not supported for dynamic search ads.<br/><br/>The path cannot contain the forward slash (/) or newline (\n) characters.<br/><br/>If the path includes a space, it will be replaced with an underscore (_) when the ad is shown.<br/><br/>**Add:** Optional<br/>**Update:** Optional|**string**|
|<a name="text"></a>Text|The first part of the ad description.<br/><br/>The text must contain at least one word.<br/><br/>The maximum input length of the copy is 90 characters. Note that for ad groups that use Traditional Chinese the maximum input length of the copy is 45 characters. Although dynamic text substitution is supported for other ad types like Expanded Text ads, it is not supported for dynamic search ads.<br/><br/>The text cannot contain the newline (\n) character.<br/><br/>**Add:** Required<br/>**Update:** Optional|**string**|
|<a name="textpart2"></a>TextPart2|The second part of the ad description.<br/><br/>The text must contain at least one word.<br/><br/>The maximum input length of the copy is 90 characters. Note that for ad groups that use Traditional Chinese the maximum input length of the copy is 45 characters. Although dynamic text substitution is supported for other ad types like Expanded Text ads, it is not supported for dynamic search ads.<br/><br/>The text cannot contain the newline (\n) character.<br/><br/>This feature is only available for customers in the Dynamic Search Ads Text Part 2 pilot ([GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) returns 600). If you are not in the pilot and you try to set this property an error will be returned. During calendar year 2019 this feature will be enabled for all customers.<br/><br/>**Add:** Optional<br/>**Update:** Optional|**string**|

The [DynamicSearchAd](dynamicsearchad.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsad"></a>Inherited Elements from Ad
The [DynamicSearchAd](dynamicsearchad.md) object derives from the [Ad](ad.md) object, and inherits the following elements. The descriptions below are specific to [DynamicSearchAd](dynamicsearchad.md), and might not apply to other objects that inherit the same elements from the [Ad](ad.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adformatpreference"></a>AdFormatPreference|Not supported for this ad type.|**string**|
|<a name="devicepreference"></a>DevicePreference|Not supported for this ad type.|**long**|
|<a name="editorialstatus"></a>EditorialStatus|The editorial review status of the ad, which indicates whether the ad is pending review, has been approved, or has been disapproved.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AdEditorialStatus](adeditorialstatus.md)|
|<a name="finalappurls"></a>FinalAppUrls|Not supported for this ad type.|[AppUrl](appurl.md) array|
|<a name="finalmobileurls"></a>FinalMobileUrls|Not supported for this ad type.|**string** array|
|<a name="finalurls"></a>FinalUrls|Not supported for this ad type.|**string** array|
|<a name="finalurlsuffix"></a>FinalUrlSuffix|The final URL suffix can include tracking parameters that will be appended to the end of your landing page URL. We recommend placing tracking parameters that your landing page requires in a final URL suffix so that your customers are always sent to your landing page. For more details and validation rules see [Final URL Suffix](../guides/url-tracking-upgraded-urls.md#finalurlsuffixvalidation) in the technical guides.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is set for the update, this setting is not changed. If you set this element to an empty string (*""*), the previous setting will be deleted.|**string**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br/><br/>Currently there are no supported forward compatibility map key and value pairs for dynamic search ads.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The unique Microsoft Advertising identifier of the ad.<br/><br/>**Add:** Read-only<br/>**Update:** Required and Read-Only|**long**|
|<a name="status"></a>Status|The status of the ad.<br/><br/>You can set the ad status to Active or Paused.<br/><br/>**Add:** Optional<br/>**Update:** Optional|[AdStatus](adstatus.md)|
|<a name="trackingurltemplate"></a>TrackingUrlTemplate|The tracking template to use as a default for all landing page URLs.<br/><br/>The following validation rules apply to tracking templates. For more details about supported templates and parameters, see the Microsoft Advertising help article [What tracking or URL parameters can I use?](https://help.ads.microsoft.com/#apex/3/en/56799/2)<br/>- Tracking templates defined for lower level entities e.g. ads override those set for higher level entities e.g. campaign. For more information, see [Entity Limits](../guides/entity-hierarchy-limits.md).<br/>- The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.<br/>- The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*.<br/>- Microsoft Advertising does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the landing page URL will include the key and value placeholders of your custom parameters without substitution. For example, if your tracking template is *https://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}* and neither *{_season}* or *{_promocode}* are defined at the campaign, ad group, criterion, keyword, or ad level, then the landing page URL will be the same.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is set for the update, this setting is not changed. If you set this element to an empty string (*""*), the previous setting will be deleted.|**string**|
|<a name="type"></a>Type|The type of the ad. This value is *DynamicSearch* when you retrieve an dynamic search ad. For more information about ad types, see the [Ad Data Object Remarks](ad.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AdType](adtype.md)|
|<a name="urlcustomparameters"></a>UrlCustomParameters|Your custom collection of key and value parameters for URL tracking.<br/><br/>Microsoft Advertising will accept the first 8 [CustomParameter](customparameter.md) objects that you include within the [CustomParameters](customparameters.md) object, and if you include more than 8 custom parameters an error will be returned. Each [CustomParameter](customparameter.md) includes [Key](customparameter.md#key) and [Value](customparameter.md#value) elements.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is set for the update, this setting is not changed. Set the *UrlCustomParameters* element to null or empty to retain any existing custom parameters. To remove all custom parameters, set the [Parameters](customparameters.md#parameters) element of the [CustomParameters](customparameters.md) object to null or empty. To remove a subset of custom parameters, specify the custom parameters that you want to keep in the [Parameters](customparameters.md#parameters) element of the [CustomParameters](customparameters.md) object.|[CustomParameters](customparameters.md)|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

