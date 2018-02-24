---
title: Sitelink2AdExtension Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object with *one* sitelink per ad extension.
---
# Sitelink2AdExtension Data Object - Campaign Management
Defines an object with *one* sitelink per ad extension. You can use the sitelink to promote certain products, services, or sections of your website and take potential customers to exactly the information they were searching for. This can increase both click-through-rate and conversions.

> [!NOTE]
> During calendar year 2017, Bing Ads upgraded all [SiteLinksAdExtension](/bingads/campaign-management-service/sitelinksadextension.md) objects (contains multiple sitelinks per ad extension) to [Sitelink2AdExtension](/bingads/campaign-management-service/sitelink2adextension.md) objects (contains one sitelink per ad extension). In a future version of the API the deprecated sitelink programming interface will be consolidated and the '2' suffix will be removed from the new sitelink ad extensions.

You can associate a sitelink2 ad extension with the account or with campaigns and ad groups in the account. Each entity (account, campaign, or ad group) can be associated with up to 20 sitelink2 ad extensions.

## Syntax
```xml
<xs:complexType name="Sitelink2AdExtension" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:AdExtension">
      <xs:sequence>
        <xs:element minOccurs="0" name="Description1" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="Description2" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="DestinationUrl" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="DisplayText" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="FinalAppUrls" nillable="true" type="q54:ArrayOfAppUrl" xmlns:q54="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" />
        <xs:element minOccurs="0" name="FinalMobileUrls" nillable="true" type="q55:ArrayOfstring" xmlns:q55="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
        <xs:element minOccurs="0" name="FinalUrls" nillable="true" type="q56:ArrayOfstring" xmlns:q56="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
        <xs:element minOccurs="0" name="TrackingUrlTemplate" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="UrlCustomParameters" nillable="true" type="q57:CustomParameters" xmlns:q57="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="description1"></a>Description1|The site link description line 1.<br /><br />The maximum input length is 35 characters. If any Traditional Chinese characters are included, the limit is 15 characters.<br/><br/> Starting the week of September 18th, the limit will be relaxed such that only the Traditional Chinese characters will be counted double against the character limit. Each Traditional Chinese character will count as two and each English character will count only as one character.<br /><br /> If you specify *Description1* then *Description2* is required.<br/><br/>**Add:** Optional<br/>**Update:** Optional|**string**|
|<a name="description2"></a>Description2|The site link description line 2.<br /><br />The maximum input length is 35 characters. If any Traditional Chinese characters are included, the limit is 15 characters.<br/><br/> Starting the week of September 18th, the limit will be relaxed such that only the Traditional Chinese characters will be counted double against the character limit. Each Traditional Chinese character will count as two and each English character will count only as one character.<br /><br /> If you specify *Description2* then *Description1* is required.<br/><br/>**Add:** Optional<br/>**Update:** Optional|**string**|
|<a name="destinationurl"></a>DestinationUrl|**Important:** If you are currently using Destination URLs, you must eventually replace them with Final URLs. For more information, see [URL Tracking with Upgraded URLs](/bingads/guides/url-tracking-upgraded-urls.md).The URL of the webpage that users are taken to when they click the site link.<br /><br />The URL can contain dynamic parameters such as {MatchType}. For a list of supported parameters, see the *Available parameters* section within the Bing Ads help article [Learn more about each click: Use URL tracking](http://help.bingads.microsoft.com/#apex/3/en/51091/2).<br /><br />The URL can contain a maximum of 1,024 characters. If the URL does not specify a protocol, the system uses the HTTP protocol when a user clicks the ad. If the URL specifies the HTTP protocol when you add an ad, the service will remove the http:// protocol string (the HTTP protocol string does not count against the 1,024 character limit); however, the service will not remove an HTTPS protocol string (https://) from the URL.<br/><br/>**Add:** Required<br/>**Update:** Optional|**string**|
|<a name="displaytext"></a>DisplayText|The site-link text displayed in the ad.<br /><br />If you specify Description1 or Description2 then the display text can contain a maximum of 25 characters; otherwise, the display text can contain a maximum of 35 characters. If any Traditional Chinese characters are included, the limits are 11 characters given Description1 or Description2, and 15 characters otherwise.<br/><br/> Starting the week of September 18th, the limit will be relaxed such that only the Traditional Chinese characters will be counted double against the character limit. Each Traditional Chinese character will count as two and each English character will count only as one character.<br/><br/>**Add:** Required<br/>**Update:** Optional|**string**|
|<a name="finalappurls"></a>FinalAppUrls|Reserved for future use.|[AppUrl](appurl.md) array|
|<a name="finalmobileurls"></a>FinalMobileUrls|The mobile landing page URL.<br /><br />The following validation rules apply to Final URLs and Final Mobile URLs.- The length of the URL is limited to 2,048 characters.     The HTTP or HTTPS protocol string does count towards the 2,048 character limit.- You may specify up to 10 items for both *FinalUrls* and *FinalMobileUrls*; however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.- Usage of '{' and '}' is only allowed to delineate tags, for example "{lpurl}".- Final URLs must each be a well-formed URL starting with either http:// or https://.- If you specify *FinalMobileUrls*, you must also specify *FinalUrls*.- You may not specify *FinalMobileUrls* if the device preference is set to mobile.Also note that you may not specify *FinalMobileUrls* if the *DevicePreference* is set to *30001* (mobile).<br/><br/>**Add:** Optional<br/>**Update:** Optional|**string** array|
|<a name="finalurls"></a>FinalUrls|The landing page URL.<br /><br />The following validation rules apply to Final URLs and Final Mobile URLs.- The length of the URL is limited to 2,048 characters.     The HTTP or HTTPS protocol string does count towards the 2,048 character limit.- You may specify up to 10 items for both *FinalUrls* and *FinalMobileUrls*; however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.- Usage of '{' and '}' is only allowed to delineate tags, for example "{lpurl}".- Final URLs must each be a well-formed URL starting with either http:// or https://.- If you specify *FinalMobileUrls*, you must also specify *FinalUrls*.- You may not specify *FinalMobileUrls* if the device preference is set to mobile.Also note that  if this site link's *TrackingUrlTemplate* or *UrlCustomParameters* element are set, then at least one final URL is required.<br/><br/>**Add:** Optional<br/>**Update:** Optional|**string** array|
|<a name="trackingurltemplate"></a>TrackingUrlTemplate|The tracking template to use as a default for all *FinalUrls* and *FinalMobileUrls*.<br /><br />The following validation rules apply to tracking templates. For more details about supported templates and parameters, see the Bing Ads help article [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2)- Tracking templates defined for lower level entities e.g. ads override those set for higher level entities e.g. campaign. For more information, see [Entity Hierarchy and Limits](/bingads/guides/entity-hierarchy-limits.md).- The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.- The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*. - Bing Ads does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the landing page URL will include the key and value placeholders of your custom parameters without substitution. For example if your tracking template is for example *http://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}*, and neither *{_season}* or *{_promocode}* are defined at the campaign, ad group, criterion, keyword, or ad level, then the landing page URL will be the same.<br/><br/>**Add:** Optional<br/>**Update:** Optional|**string**|
|<a name="urlcustomparameters"></a>UrlCustomParameters|Your custom collection of key and value parameters for URL tracking.<br /><br />You may include up to 3 individual [CustomParameter](/bingads/campaign-management-service/customparameter.md) objects within the [CustomParameters](/bingads/campaign-management-service/customparameters.md) object. Each [CustomParameter](/bingads/campaign-management-service/customparameter.md) contains a *Key* and *Value* element.<br /><br />On update, set the *UrlCustomParameters* element to null or empty to retain any existing custom parameters. To remove all custom parameters, set the *Parameters* element of the [CustomParameters](/bingads/campaign-management-service/customparameters.md) object to null or empty. To remove a subset of custom parameters, specify the custom parameters that you want to keep in the *Parameters* element of the [CustomParameters](/bingads/campaign-management-service/customparameters.md) object.<br/><br/>**Add:** Optional<br/>**Update:** Optional|[CustomParameters](customparameters.md)|

The [Sitelink2AdExtension](sitelink2adextension.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsadextension"></a>Inherited Elements from AdExtension
The [Sitelink2AdExtension](sitelink2adextension.md) object derives from the [AdExtension](adextension.md) object, and inherits the following elements. The descriptions below are specific to [Sitelink2AdExtension](sitelink2adextension.md), and might not apply to other objects that inherit the same elements from the [AdExtension](adextension.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="devicepreference"></a>DevicePreference|This element determines whether the preference is for the ad extension to be displayed on mobile devices or all devices.<br /><br />To specify a preference for mobile devices, set this element to *30001*.<br /><br />To specify all devices, set this element to *0* (zero) or leave the element nil. By default, this element will be nil.<br/><br/>**Add:** Optional<br/>**Update:** Optional|**long**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br />There are currently no forward compatibility changes for the *AdExtension* object.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The unique Bing Ads identifier of the ad extension.<br/><br/>**Add:** Read-only and Required<br/>**Update:** Read-only|**long**|
|<a name="scheduling"></a>Scheduling|Determines the calendar day and time ranges when the ad extension is eligible to be shown in ads.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If you set this element null, any existing scheduling set for the ad extension will remain unchanged. If you set this to any non-null [Schedule](/bingads/campaign-management-service/schedule.md) object, you are effectively replacing existing scheduling settings for the ad extension. To remove all scheduling set this element to an empty [Schedule](/bingads/campaign-management-service/schedule.md) object.|[Schedule](schedule.md)|
|<a name="status"></a>Status|The status of the ad extension. The value will always be *Active* because the Campaign Management service does not return deleted ad extensions.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AdExtensionStatus](adextensionstatus.md)|
|<a name="type"></a>Type|The type of the ad extension. This value is *Sitelink2AdExtension* when you retrieve a sitelink2 ad extension. <br/><br/>**Add:** Read-only<br/>**Update:** Read-only<br/><br/>For more information about ad extension types, see the [Ad Extension Data Object Remarks](/bingads/campaign-management-service/adextension.md#remarks).|**string**|
|<a name="version"></a>Version|The number of times the contents of the ad extension has been updated. The version is set to 1 when you add the extension and is incremented each time it's revised.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**int**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

