---
title: ResponsiveAd Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Reserved.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# ResponsiveAd Data Object - Campaign Management
Reserved.

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
|<a name="businessname"></a>BusinessName|Reserved.|**string**|
|<a name="calltoaction"></a>CallToAction|Reserved.|[CallToAction](calltoaction.md)|
|<a name="headline"></a>Headline|Reserved.|**string**|
|<a name="landscapeimagemediaid"></a>LandscapeImageMediaId|Reserved.|**long**|
|<a name="landscapelogomediaid"></a>LandscapeLogoMediaId|Reserved.|**long**|
|<a name="longheadline"></a>LongHeadline|Reserved.|**string**|
|<a name="squareimagemediaid"></a>SquareImageMediaId|Reserved.|**long**|
|<a name="squarelogomediaid"></a>SquareLogoMediaId|Reserved.|**long**|
|<a name="text"></a>Text|Reserved.|**string**|

The [ResponsiveAd](responsivead.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsad"></a>Inherited Elements from Ad
The [ResponsiveAd](responsivead.md) object derives from the [Ad](ad.md) object, and inherits the following elements. The descriptions below are specific to [ResponsiveAd](responsivead.md), and might not apply to other objects that inherit the same elements from the [Ad](ad.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adformatpreference"></a>AdFormatPreference|Reserved.|**string**|
|<a name="devicepreference"></a>DevicePreference|Reserved.|**long**|
|<a name="editorialstatus"></a>EditorialStatus|Reserved.|[AdEditorialStatus](adeditorialstatus.md)|
|<a name="finalappurls"></a>FinalAppUrls|Reserved.|[AppUrl](appurl.md) array|
|<a name="finalmobileurls"></a>FinalMobileUrls|Reserved.|**string** array|
|<a name="finalurls"></a>FinalUrls|Reserved.|**string** array|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|Reserved.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|Reserved.|**long**|
|<a name="status"></a>Status|Reserved.|[AdStatus](adstatus.md)|
|<a name="trackingurltemplate"></a>TrackingUrlTemplate|Reserved.|**string**|
|<a name="type"></a>Type|Reserved.|[AdType](adtype.md)|
|<a name="urlcustomparameters"></a>UrlCustomParameters|Reserved.|[CustomParameters](customparameters.md)|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

