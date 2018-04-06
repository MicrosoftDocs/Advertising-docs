---
title: CallAdExtension Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that specifies a click-to-call phone number to include in a text ad.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# CallAdExtension Data Object - Campaign Management
Defines an object that specifies a click-to-call phone number to include in a text ad.

You can associate a call ad extension with campaigns in the account. Each entity (campaign) can be associated with one call ad extension.

## Syntax
```xml
<xs:complexType name="CallAdExtension" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:AdExtension">
      <xs:sequence>
        <xs:element minOccurs="0" name="CountryCode" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="IsCallOnly" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="IsCallTrackingEnabled" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="PhoneNumber" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="RequireTollFreeTrackingNumber" nillable="true" type="xs:boolean" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="countrycode"></a>CountryCode|The country code where the phone number is registered. The country code must contain a 2 character country code. For a list of country code values, see [Geographical Location Codes](../guides/geographical-location-codes.md).<br/><br/>**Add:** Required<br/>**Update:** Optional|**string**|
|<a name="iscallonly"></a>IsCallOnly|The option to show both your phone number and website, or just your phone number, to people seeing your ads on a smartphone. You might want to show only your phone number if your business requires that you talk to each customer.<br/><br/>Set this property to *true* if you want the ad extension to only show the phone number without a link to your website, and otherwise if you want the ad extension include a link to your website in addition to the phone number set it to *false*.<br/><br/>**Add:** Optional. If you do not specify this field or leave it empty, the default value of *false* will be set and the ad extension will include a link to your website in addition to the phone number.<br/>**Update:** Optional|**boolean**|
|<a name="iscalltrackingenabled"></a>IsCallTrackingEnabled|Determines whether call tracking is enabled for the call ad extension.<br /><br /> Call tracking is only supported in the United States and United Kingdom.<br /><br />Set this property to *true* to enable call tracking, and otherwise set it to *false*.<br/><br/>**Add:** Optional. If you do not specify this field or leave it empty, the default value of *false* will be set.<br/>**Update:** Optional|**boolean**|
|<a name="phonenumber"></a>PhoneNumber|The clickable phone number to include in the ad. <br /><br />The phone number can contain a maximum of 35 characters and must be valid for the specified country.<br /><br />If the campaign includes call and location ad extensions, this phone number will override the phone number specified in the location ad extensions.<br /><br />Note that the phone number may be reformatted. For example, if you set phone number to 4255551212, it would be reformatted to (425) 555-1212.<br/><br/>**Add:** Required<br/>**Update:** Optional|**string**|
|<a name="requiretollfreetrackingnumber"></a>RequireTollFreeTrackingNumber|You can either use your own phone number or use a Bing Ads forwarding phone number. A Bing Ads forwarding phone number is a unique phone number that is routed to your business phone number. With a Bing Ads forwarding number, you can track all calls from your ad so that you can analyze the ad's performance. This element determines whether a toll-free Bing Ads forwarding phone number should be created for call tracking. This element can only be set if *IsCallTrackingEnabled* is also true.<br /><br />Set this property to *true* if a Bing Ads forwarding phone number should be created for call tracking, and otherwise set it to *false*.<br /><br />**Important:** Beginning the week of August 14th, 2017 you can no longer create a new toll-free Bing Ads forwarding phone number. If you set this value *True* then the operation will succeed; however, a toll-free number will not be created and when you retrieve the call ad extension this property will be set to *False*. If a toll-free forwarding number was provisioned prior to the week of August 14th, 2017 then this property will be *True* if the number is still active when you retrieve the call ad extension.<br/><br/>**Add:** Optional. If you do not specify this field or leave it empty, the default value of *false* will be set.<br/>**Update:** Optional|**boolean**|

The [CallAdExtension](calladextension.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsadextension"></a>Inherited Elements from AdExtension
The [CallAdExtension](calladextension.md) object derives from the [AdExtension](adextension.md) object, and inherits the following elements. The descriptions below are specific to [CallAdExtension](calladextension.md), and might not apply to other objects that inherit the same elements from the [AdExtension](adextension.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="devicepreference"></a>DevicePreference|Reserved for future use.|**long**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br />There are currently no forward compatibility changes for the *AdExtension* object.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The unique Bing Ads identifier of the ad extension.<br/><br/>**Add:** Read-only and Required<br/>**Update:** Read-only|**long**|
|<a name="scheduling"></a>Scheduling|Determines the calendar day and time ranges when the ad extension is eligible to be shown in ads.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If you set this element null, any existing scheduling set for the ad extension will remain unchanged. If you set this to any non-null [Schedule](schedule.md) object, you are effectively replacing existing scheduling settings for the ad extension. To remove all scheduling set this element to an empty [Schedule](schedule.md) object.|[Schedule](schedule.md)|
|<a name="status"></a>Status|The status of the ad extension. The value will always be *Active* because the Campaign Management service does not return deleted ad extensions.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AdExtensionStatus](adextensionstatus.md)|
|<a name="type"></a>Type|The type of the ad extension. This value is *CallAdExtension* when you retrieve a call ad extension. <br/><br/>**Add:** Read-only<br/>**Update:** Read-only<br/><br/>For more information about ad extension types, see the [Ad Extension Data Object Remarks](adextension.md#remarks).|**string**|
|<a name="version"></a>Version|The number of times the contents of the ad extension has been updated. The version is set to 1 when you add the extension and is incremented each time it's revised.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**int**|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

