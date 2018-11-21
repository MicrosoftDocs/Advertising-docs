---
title: AppAdExtension Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an app ad extension that can be included in an ad.
---
# AppAdExtension Data Object - Campaign Management
Defines an app ad extension that can be included in an ad.

You can associate an app ad extension with the account or with campaigns and ad groups in the account. Each entity (account, campaign, or ad group) can be associated with as many app ad extensions as you decide, up to the total number of app ad extensions in your account.

## Syntax
```xml
<xs:complexType name="AppAdExtension" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:AdExtension">
      <xs:sequence>
        <xs:element minOccurs="0" name="AppPlatform" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="AppStoreId" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="DestinationUrl" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="DisplayText" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="FinalAppUrls" nillable="true" type="tns:ArrayOfAppUrl" />
        <xs:element minOccurs="0" name="FinalMobileUrls" nillable="true" type="q41:ArrayOfstring" xmlns:q41="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
        <xs:element minOccurs="0" name="FinalUrls" nillable="true" type="q42:ArrayOfstring" xmlns:q42="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
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
|<a name="appplatform"></a>AppPlatform|The application platform.<br/><br/>Possible values include iOS, Android, Windows Phone, and Windows.<br/><br/>**Add:** Required<br/>**Update:** Optional|**string**|
|<a name="appstoreid"></a>AppStoreId|The application identifier provided by the app store.<br/><br/>If the application is new, please expect to wait 4-7 days before the ad will be eligible to deliver.<br/><br/>**Add:** Required<br/>**Update:** Optional|**string**|
|<a name="destinationurl"></a>DestinationUrl|The URL of the app store download webpage that users are taken to when they click the app extension link.<br/><br/>The URL can contain dynamic text strings such as {keyword}. For a list of supported parameters, see the Available parameters section within the Bing Ads help article [What tracking or URL parameters can I use?](http://help.bingads.microsoft.com/#apex/3/en/56799/2).<br/><br/>The URL can contain a maximum of 1,024 characters. If the URL does not specify a protocol, the system uses the HTTP protocol when a user clicks the ad. If the URL specifies the HTTP protocol when you add an ad, the service will remove the http:// protocol string (the HTTP protocol string does not count against the 1,024 character limit); however, the service will not remove an HTTPS protocol string (https://) from the URL.<br/><br/>**Add:** Required<br/>**Update:** Optional|**string**|
|<a name="displaytext"></a>DisplayText|The text displayed in the app ad extension. The text can contain a maximum of 35 characters.<br/><br/>**Add:** Required<br/>**Update:** Optional|**string**|
|<a name="finalappurls"></a>FinalAppUrls|Reserved for future use.|[AppUrl](appurl.md) array|
|<a name="finalmobileurls"></a>FinalMobileUrls|Reserved for future use.|**string** array|
|<a name="finalurls"></a>FinalUrls|Reserved for future use.|**string** array|
|<a name="trackingurltemplate"></a>TrackingUrlTemplate|Reserved for future use.|**string**|
|<a name="urlcustomparameters"></a>UrlCustomParameters|Reserved for future use.|[CustomParameters](customparameters.md)|

The [AppAdExtension](appadextension.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsadextension"></a>Inherited Elements from AdExtension
The [AppAdExtension](appadextension.md) object derives from the [AdExtension](adextension.md) object, and inherits the following elements. The descriptions below are specific to [AppAdExtension](appadextension.md), and might not apply to other objects that inherit the same elements from the [AdExtension](adextension.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="devicepreference"></a>DevicePreference|This element determines whether the preference is for the app extension to be displayed on mobile devices or all devices.<br/><br/>To specify a preference for mobile devices, set this element to *30001*.<br/><br/>To specify all devices, set this element to *0* (zero) or leave the element nil. By default, this element will be nil.<br/><br/>**Add:** Optional<br/>**Update:** Optional|**long**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br/><br/>There are currently no forward compatibility changes for the *AdExtension* object.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The unique Bing Ads identifier of the ad extension.<br/><br/>**Add:** Read-only and Required<br/>**Update:** Read-only|**long**|
|<a name="scheduling"></a>Scheduling|Determines the calendar day and time ranges when the ad extension is eligible to be shown in ads.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If you set this element null, any existing scheduling set for the ad extension will remain unchanged. If you set this to any non-null [Schedule](schedule.md) object, you are effectively replacing existing scheduling settings for the ad extension. To remove all scheduling set this element to an empty [Schedule](schedule.md) object.|[Schedule](schedule.md)|
|<a name="status"></a>Status|The status of the ad extension. The value will always be *Active* because the Campaign Management service does not return deleted ad extensions.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AdExtensionStatus](adextensionstatus.md)|
|<a name="type"></a>Type|The type of the ad extension. This value is *AppAdExtension* when you retrieve an app ad extension.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only<br/><br/>For more information about ad extension types, see the [Ad Extension Data Object Remarks](adextension.md#remarks).|**string**|
|<a name="version"></a>Version|The number of times the contents of the ad extension has been updated. The version is set to 1 when you add the extension and is incremented each time it's revised.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**int**|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

