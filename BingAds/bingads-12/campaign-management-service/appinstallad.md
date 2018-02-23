---
title: AppInstallAd Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an app install ad.
---
# AppInstallAd Data Object - Campaign Management

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

Defines an app install ad. Create an app install ad if your intention is to drive app downloads, and not necessarily to direct leads to a web site. If you want to direct leads to a web site in addition to driving app downloads, then you should create a text ad with app ad extensions.

> [!NOTE]
> Before you can use app install ads, you must upgrade to Final Urls. For more information, see [URL Tracking with Upgraded URLs](../guides/url-tracking-upgraded-urls.md).
>
> Bing Ads only supports *EN-US* apps.

## Syntax
```xml
<xs:complexType name="AppInstallAd" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Ad">
      <xs:sequence>
        <xs:element minOccurs="0" name="AppPlatform" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="AppStoreId" nillable="true" type="xs:string" />
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
|<a name="appplatform"></a>AppPlatform|The application platform.<br /><br />Possible values include *iOS* and *Android*.<br /><br />**Add:** Required<br/>**Update:** Optional|**string**|
|<a name="appstoreid"></a>AppStoreId|The application identifier provided by the app store.<br /><br /> If the application is new, please expect to wait 4-7 days before the ad will be eligible to deliver.<br /><br />**Add:** Required<br/>**Update:** Optional|**string**|
|<a name="text"></a>Text|The ad copy. The copy must contain at least one word. The ad's copy and title combined must total at least three words.<br /><br />The ad copy cannot contain dynamic text strings such as {keyword}. <br /><br />The maximum input length of the copy is 71 characters. Note that for ad groups that use Traditional Chinese, the text is limited to 38 characters.<br /><br />The ad copy cannot contain the newline (\n) character.<br /><br />**Add:** Required<br/>**Update:** Optional|**string**|
|<a name="title"></a>Title|The title of the ad. The title must contain at least one word. The ad's copy and title combined must total at least three words.<br /><br />The title cannot contain dynamic text strings such as {keyword}.<br /><br />The maximum input length of the title is 25 characters. Note that for ad groups that use Traditional Chinese, the title is limited to 15 characters.<br /><br />The title cannot contain the newline (\n) character.<br /><br />**Add:** Required<br/>**Update:** Optional|**string**|

The [AppInstallAd](appinstallad.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsad"></a>Inherited Elements from Ad
The [AppInstallAd](appinstallad.md) object derives from the [Ad](ad.md) object, and inherits the following elements. The descriptions below are specific to [AppInstallAd](appinstallad.md), and might not apply to other objects that inherit the same elements from the [Ad](ad.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adformatpreference"></a>AdFormatPreference|This element is not applicable for app install ads.|**string**|
|<a name="devicepreference"></a>DevicePreference|This element determines whether the preference is for app install ads to be displayed on mobile and tablet devices or only on mobile devices. (App install ads are not currently supported on desktop computers.)<br /><br />To specify a preference for mobile devices only (i.e. excluding tablets), set this element to *30001*.<br /><br />To specify a preference for both mobile and tablet devices, set this element to *0* (zero) or leave the element nil. By default, this element will be nil. <br /><br />**Add:** Optional<br/>**Update:** Optional|**long**|
|<a name="editorialstatus"></a>EditorialStatus|The editorial review status of the ad, which indicates whether the ad is pending review, has been approved, or has been disapproved.<br /><br />**Add:** Read-only<br/>**Update:** Read-only|[AdEditorialStatus](adeditorialstatus.md)|
|<a name="finalappurls"></a>FinalAppUrls|Not supported for app install ads.|[AppUrl](appurl.md) array|
|<a name="finalmobileurls"></a>FinalMobileUrls|Not supported for app install ads.|**string** array|
|<a name="finalurls"></a>FinalUrls|The URL where a search user lands and can choose to install an app.<br /><br />**Add:** Required<br/>**Update:** Optional|**string** array|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br />There are currently not any ForwardCompatibilityMap key and value pairs that are applicable for this object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The unique Bing Ads identifier for the ad.<br /><br />**Add:** Read-only<br/>**Update:** Required and Read-only|**long**|
|<a name="status"></a>Status|The status of the ad.<br/><br/>You can set the ad status to Active or Paused.<br /><br />**Add:** Optional<br/>**Update:** Optional|[AdStatus](adstatus.md)|
|<a name="trackingurltemplate"></a>TrackingUrlTemplate|The tracking template to use as a default for the URL specified with *FinalUrls*.<br /><br />The following validation rules apply to tracking templates. For more details about supported templates and parameters, see the Bing Ads help article [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2)- Tracking templates defined for lower level entities e.g. ads override those set for higher level entities e.g. campaign. For more information, see [Entity Hierarchy and Limits](../guides/entity-hierarchy-limits.md).- The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.- The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*. - Bing Ads does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the landing page URL will include the key and value placeholders of your custom parameters without substitution. For example if your tracking template is for example *http://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}*, and neither *{_season}* or *{_promocode}* are defined at the campaign, ad group, criterion, keyword, or ad level, then the landing page URL will be the same.<br /><br />**Add:** Optional<br/>**Update:** Optional|**string**|
|<a name="type"></a>Type|The type of the ad. This value is *AppInstall* when you retrieve an app install ad. For more information about ad types, see the [Ad Data Object Remarks](../campaign-management-service/ad.md#remarks).<br /><br />**Add:** Read-only<br/>**Update:** Read-only|[AdType](adtype.md)|
|<a name="urlcustomparameters"></a>UrlCustomParameters|Your custom collection of key and value parameters for URL tracking.<br /><br />You may include up to 3 individual [CustomParameter](../campaign-management-service/customparameter.md) objects within the [CustomParameters](../campaign-management-service/customparameters.md) object. Each [CustomParameter](../campaign-management-service/customparameter.md) contains a *Key* and *Value* element.<br /><br />On update, set the *UrlCustomParameters* element to null or empty to retain any existing custom parameters. To remove all custom parameters, set the *Parameters* element of the [CustomParameters](../campaign-management-service/customparameters.md) object to null or empty. To remove a subset of custom parameters, specify the custom parameters that you want to keep in the *Parameters* element of the [CustomParameters](../campaign-management-service/customparameters.md) object.<br /><br />**Add:** Optional<br/>**Update:** Optional|[CustomParameters](customparameters.md)|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

