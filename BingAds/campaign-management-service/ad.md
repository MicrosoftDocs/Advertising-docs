---
title: Ad Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: "article"
author: eric-urban
ms.author: eur
description: Defines the base object of an ad.
---
# Ad Data Object - Campaign Management
Defines the base object of an ad.

Do not try to instantiate an *Ad*. You can create one or more following objects that derive from it.
- [AppInstallAd](../campaign-management-service/appinstallad.md)
- [DynamicSearchAd](../campaign-management-service/dynamicsearchad.md)
- [ExpandedTextAd](../campaign-management-service/expandedtextad.md)
- [TextAd](../campaign-management-service/textad.md)
- [ProductAd](../campaign-management-service/productad.md) 

## Syntax
```xml
<xs:complexType name="Ad" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AdFormatPreference" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="DevicePreference" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="EditorialStatus" nillable="true" type="tns:AdEditorialStatus" />
    <xs:element minOccurs="0" name="FinalAppUrls" nillable="true" type="q1:ArrayOfAppUrl" xmlns:q1="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" />
    <xs:element minOccurs="0" name="FinalMobileUrls" nillable="true" type="q2:ArrayOfstring" xmlns:q2="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
    <xs:element minOccurs="0" name="FinalUrls" nillable="true" type="q3:ArrayOfstring" xmlns:q3="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
    <xs:element minOccurs="0" name="ForwardCompatibilityMap" nillable="true" type="q4:ArrayOfKeyValuePairOfstringstring" xmlns:q4="http://schemas.datacontract.org/2004/07/System.Collections.Generic" />
    <xs:element minOccurs="0" name="Id" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="Status" nillable="true" type="tns:AdStatus" />
    <xs:element minOccurs="0" name="TrackingUrlTemplate" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Type" nillable="true" type="tns:AdType" />
    <xs:element minOccurs="0" name="UrlCustomParameters" nillable="true" type="q5:CustomParameters" xmlns:q5="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adformatpreference"></a>AdFormatPreference|The Ad Format Preference is used to indicate whether or not you prefer the ad copy to be shown to users as a search or native ad. Search ads tend to be written as a call to action, whereas intent ads should be written in more of an informational style.<br /><br />By defining at least one ad that should be used as native, the search ads will only be shown in search results.<br/><br/>Possible values are *Native* and *All*. If set to *All*, the ad will be eligible for both search and native ad formats. If set to *Native*, the ad will only be eligible for the native ad format.<br /><br />Ad Format Preference is only supported for [ExpandedTextAd](../campaign-management-service/expandedtextad.md) and [TextAd](../campaign-management-service/textad.md) objects.|**string**|
|<a name="devicepreference"></a>DevicePreference|Determines the device preference for showing the ad. <br /><br />Device preference is only supported for [AppInstallAd](../campaign-management-service/appinstallad.md) and [TextAd](../campaign-management-service/textad.md) objects.|**long**|
|<a name="editorialstatus"></a>EditorialStatus|The editorial review status of the ad, which indicates whether the ad is pending review, has been approved, or has been disapproved.|[AdEditorialStatus](adeditorialstatus.md)|
|<a name="finalappurls"></a>FinalAppUrls|Reserved for future use.|[AppUrl](appurl.md) array|
|<a name="finalmobileurls"></a>FinalMobileUrls|The mobile landing page URL. <br /><br />Final mobile URLs is only supported for text ads. For more details see [TextAd](../campaign-management-service/textad.md).|**string**|
|<a name="finalurls"></a>FinalUrls|The last or final URL where a user is ultimately taken, whether or not the click to final URL path included any redirects.<br /><br />Final URLs are only supported for [AppInstallAd](../campaign-management-service/appinstallad.md), [ExpandedTextAd](../campaign-management-service/expandedtextad.md), and [TextAd](../campaign-management-service/textad.md) objects.|**string**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br />Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for this object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The unique Bing Ads identifier for the ad.|**long**|
|<a name="status"></a>Status|The status of the ad.|[AdStatus](adstatus.md)|
|<a name="trackingurltemplate"></a>TrackingUrlTemplate|The tracking template to use as a default for all landing page URLs.<br /><br />Tracking template is only supported for [AppInstallAd](../campaign-management-service/appinstallad.md), [DynamicSearchAd](../campaign-management-service/dynamicsearchad.md), [ExpandedTextAd](../campaign-management-service/expandedtextad.md), and [TextAd](../campaign-management-service/textad.md) objects. It is not supported for the [ProductAd](../campaign-management-service/productad.md) object.|**string**|
|<a name="type"></a>Type|The type of the ad. For more information about ad types, see the [Remarks](#remarks).|[AdType](adtype.md)|
|<a name="urlcustomparameters"></a>UrlCustomParameters|Your custom collection of key and value parameters for URL tracking.<br /><br />Custom parameters are only supported for [AppInstallAd](../campaign-management-service/appinstallad.md), [DynamicSearchAd](../campaign-management-service/dynamicsearchad.md), [ExpandedTextAd](../campaign-management-service/expandedtextad.md), and [TextAd](../campaign-management-service/textad.md) objects. They are not supported for the [ProductAd](../campaign-management-service/productad.md) object.|[CustomParameters](customparameters.md)|

## <a name="remarks"></a>Remarks
For Java and the .NET languages, do not set the *Type* element because the value is determined by whether you instantiate an expanded text ad or another type of ad.

If you generate the SOAP manually, use the *type* attribute of the *Ad* node as shown in the following example, to specify whether the ad is an expanded text ad or another type of ad.

```xml
<Ads xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
  <Ad i:type="ExpandedTextAd">
    <DevicePreference i:nil="true" />
    <EditorialStatus i:nil="true" />
    <ForwardCompatibilityMap i:nil="true" />
    <Id i:nil="true" />
    <Status i:nil="true" />
    <FinalUrls xmlns:a="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
      <a:string>http://www.contoso.com/womenshoesale</a:string>
    </FinalUrls>
    <Path1>seattle</Path1>
    <Path2>shoe sale</Path2>
    <Text>Find New Customers & Increase Sales! Start Advertising on Contoso Today.</Text>
    <TitlePart1>Contoso</TitlePart1>
    <TitlePart2>Fast & Easy Setup</TitlePart2>
  </Ad>
</Ads>
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[AddAds](addads.md)  
[GetAdsByAdGroupId](getadsbyadgroupid.md)  
[GetAdsByEditorialStatus](getadsbyeditorialstatus.md)  
[GetAdsByIds](getadsbyids.md)  
[UpdateAds](updateads.md)  
