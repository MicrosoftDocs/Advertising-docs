---
title: TextAd Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a text ad.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# TextAd Data Object - Campaign Management
Defines a text ad.

> [!IMPORTANT]
> Standard Text Ads have been deprecated in favor of Expanded Text Ads (EXTAs). Support for adding and updating standard text ads (STAs) ended on July 31, 2017. Now, advertisers can get and delete, but can no longer add new STAs or update existing standard text ads with Destination URLs. One exception to the rule, is that you can still update the STA status e.g. from *Active* to *Paused*. Otherwise attempts to add or update STAs will result in the *CampaignServiceAdTypeInvalid* error. 
> 
> It is important to note that all your existing STAs will continue to serve alongside EXTAs for the foreseeable future. While there is no date on when STAs will stop serving, you can expect an update to all of our customers well in advance once we make the decision to sunset serving STAs.

## Syntax
```xml
<xs:complexType name="TextAd" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Ad">
      <xs:sequence>
        <xs:element minOccurs="0" name="DestinationUrl" nillable="true" type="xs:string" />
        <xs:element name="DisplayUrl" nillable="true" type="xs:string" />
        <xs:element name="Text" nillable="true" type="xs:string" />
        <xs:element name="Title" nillable="true" type="xs:string" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="destinationurl"></a>DestinationUrl|The URL of the webpage to take the user to when they click the ad.<br /><br />The URL can contain dynamic parameters such as {MatchType}.<br/><br/>For a list of supported parameters, see the Bing Ads help article [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2).<br /><br />The URL can contain a maximum of 1,024 characters. If the URL does not specify a protocol, the system uses the HTTP protocol when a user clicks the ad. If the URL specifies the HTTP protocol when you add an ad, the service will remove the http:// protocol string (the HTTP protocol string does not count against the 1,024 character limit); however, the service will not remove an HTTPS protocol string (https://) from the URL.<br/><br/>**Important:** If you are currently using Destination URLs, you must eventually replace them with Final URLs. For more information, see [URL Tracking with Upgraded URLs](../guides/url-tracking-upgraded-urls.md).<br /><br /> This URL is used only if the keyword does not specify a destination URL.<br /><br />**Add:** Required<br />**Update:** Optional|**string**|
|<a name="displayurl"></a>DisplayUrl|The URL to display in the ad.<br /><br />The subdirectory of the display URL can contain dynamic text strings such as {keyword}; however, the URL hostname cannot contain dynamic text. For more information, see the Bing Ads help article [Automatically customize your ads with dynamic text parameters](http://help.bingads.microsoft.com/#apex/3/en/50811/1).<br /><br />The maximum input length of the URL is 200 characters, and can contain dynamic text strings. However, the ad will fail to display if the URL exceeds 35 characters after dynamic text substitution occurs.<br /><br />**Add:** Required<br />**Update:** Optional|**string**|
|<a name="text"></a>Text|The ad copy. The copy must contain at least one word. The ad's copy and title combined must total at least three words.<br /><br />The text can contain dynamic text strings such as {keyword}. For more information, see the Bing Ads help article [Automatically customize your ads with dynamic text parameters](http://help.bingads.microsoft.com/#apex/3/en/50811/1).<br /><br />The maximum input length of the copy is 300 characters, and can contain dynamic text strings. However, the ad will fail to display if the copy exceeds 71 characters after dynamic text substitution occurs. Note that for ad groups that use Traditional Chinese, the text is limited to 38 characters after substitution.<br /><br />The text cannot contain the newline (\n) character.<br /><br />**Add:** Required<br />**Update:** Optional|**string**|
|<a name="title"></a>Title|The title of the ad. The title must contain at least one word. The ad's copy and title combined must total at least three words.<br /><br />The title can contain dynamic text strings such as {keyword}. For more information, see the Bing Ads help article [Automatically customize your ads with dynamic text parameters](http://help.bingads.microsoft.com/#apex/3/en/50811/1).<br /><br />The maximum input length of the title is 80 characters, and can contain dynamic text strings. However, the ad will fail to display if title exceeds 25 characters after dynamic text substitution occurs. Note that for ad groups that use Traditional Chinese, the title is limited to 15 characters after substitution.<br /><br />The title cannot contain the newline (\n) character.<br /><br />**Add:** Required<br />**Update:** Optional|**string**|

The [TextAd](textad.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsad"></a>Inherited Elements from Ad
The [TextAd](textad.md) object derives from the [Ad](ad.md) object, and inherits the following elements. The descriptions below are specific to [TextAd](textad.md), and might not apply to other objects that inherit the same elements from the [Ad](ad.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adformatpreference"></a>AdFormatPreference|The Ad Format Preference is used to indicate whether or not you prefer the ad copy to be shown to users as a search or native ad. Search ads tend to be written as a call to action, whereas intent ads should be written in more of an informational style.<br /><br />By defining at least one ad that should be used as native, the search ads will only be shown in search results.<br /><br />**IMPORTANT:** You must define at least one text ad per ad group that is not native preferred, otherwise the ad copy of all text ads will be eligible for both search and intent ads.<br/><br/>Possible values are *Native* and *All*. If set to *All*, the ad will be eligible for both search and native ad formats. If set to *Native*, the ad will only be eligible for the native ad format.<br/><br/>**Add:** Optional. If you do not set this field when creating a text ad, by default the ad format preference will be set to *All*.<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="devicepreference"></a>DevicePreference|This element determines whether the preference is for text ads to be displayed on mobile devices or all devices.<br /><br />To specify a preference for mobile devices, set this element to *30001*.<br /><br />To specify all devices, set this element to *0* (zero) or leave the element nil. By default, this element will be nil. You must define at least one text ad per ad group that is not mobile preferred, otherwise the ad will be eligible for all devices. <br /><br />**Add:** Optional<br />**Update:** Optional|**long**|
|<a name="editorialstatus"></a>EditorialStatus|The editorial review status of the ad, which indicates whether the ad is pending review, has been approved, or has been disapproved.<br /><br />**Add:** Read-only<br />**Update:** Read-only|[AdEditorialStatus](adeditorialstatus.md)|
|<a name="finalappurls"></a>FinalAppUrls|Not supported for text ads.|[AppUrl](appurl.md) array|
|<a name="finalmobileurls"></a>FinalMobileUrls|The mobile landing page URL.<br /><br /> This URL is used only if the keyword does not specify a final mobile URL.<br /><br />The following validation rules apply to Final URLs and Final Mobile URLs.- The length of the URL is limited to 2,048 characters.     The HTTP or HTTPS protocol string does count towards the 2,048 character limit.- You may specify up to 10 items for both *FinalUrls* and *FinalMobileUrls*; however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.- Usage of '{' and '}' is only allowed to delineate tags, for example "{lpurl}".- Final URLs must each be a well-formed URL starting with either http:// or https://.- If you specify *FinalMobileUrls*, you must also specify *FinalUrls*.- You may not specify *FinalMobileUrls* if the device preference is set to mobile.Also note that for [TextAd](textad.md) objects you may not specify *FinalMobileUrls* if the *DevicePreference* is set to *30001* (mobile).|**string** array|
|<a name="finalurls"></a>FinalUrls|The landing page URL.<br /><br /> This URL is used only if the keyword does not specify a final URL.<br /><br />The following validation rules apply to Final URLs and Final Mobile URLs.- The length of the URL is limited to 2,048 characters.     The HTTP or HTTPS protocol string does count towards the 2,048 character limit.- You may specify up to 10 items for both *FinalUrls* and *FinalMobileUrls*; however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.- Usage of '{' and '}' is only allowed to delineate tags, for example "{lpurl}".- Final URLs must each be a well-formed URL starting with either http:// or https://.- If you specify *FinalMobileUrls*, you must also specify *FinalUrls*.- You may not specify *FinalMobileUrls* if the device preference is set to mobile.Also note that  if this ad's *TrackingUrlTemplate* or *UrlCustomParameters* element are set, then at least one final URL is required.<br /><br />**Add:** Required<br />**Update:** Optional|**string** array|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br />Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for this object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The unique Bing Ads identifier for the ad.<br /><br />**Add:** Read-only<br />**Update:** Required and Read-only|**long**|
|<a name="status"></a>Status|The status of the ad.<br/><br/>You can set the ad status to Active or Paused.<br /><br />**Add:** Optional<br />**Update:** Optional|[AdStatus](adstatus.md)|
|<a name="trackingurltemplate"></a>TrackingUrlTemplate|The tracking template to use as a default for all landing page URLs.<br /><br />The following validation rules apply to tracking templates. For more details about supported templates and parameters, see the Bing Ads help article [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2)- Tracking templates defined for lower level entities e.g. ads override those set for higher level entities e.g. campaign. For more information, see [Entity Hierarchy and Limits](../guides/entity-hierarchy-limits.md).- The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.- The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*. - Bing Ads does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the landing page URL will include the key and value placeholders of your custom parameters without substitution. For example if your tracking template is for example *http://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}*, and neither *{_season}* or *{_promocode}* are defined at the campaign, ad group, criterion, keyword, or ad level, then the landing page URL will be the same.<br /><br />**Add:** Optional<br />**Update:** Optional|**string**|
|<a name="type"></a>Type|The type of the ad. This value is *Text* when you retrieve a text ad. For more information about ad types, see the [Ad Data Object Remarks](ad.md#remarks).<br /><br />**Add:** Read-only<br />**Update:** Read-only|[AdType](adtype.md)|
|<a name="urlcustomparameters"></a>UrlCustomParameters|Your custom collection of key and value parameters for URL tracking.<br /><br />You may include up to 3 individual [CustomParameter](customparameter.md) objects within the [CustomParameters](customparameters.md) object. Each [CustomParameter](customparameter.md) contains a *Key* and *Value* element.<br /><br />On update, set the *UrlCustomParameters* element to null or empty to retain any existing custom parameters. To remove all custom parameters, set the *Parameters* element of the [CustomParameters](customparameters.md) object to null or empty. To remove a subset of custom parameters, specify the custom parameters that you want to keep in the *Parameters* element of the [CustomParameters](customparameters.md) object.<br /><br />**Add:** Optional<br />**Update:** Optional|[CustomParameters](customparameters.md)|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

