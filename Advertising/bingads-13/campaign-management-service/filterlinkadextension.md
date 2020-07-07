---
title: FilterLinkAdExtension Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Reserved.
---
# FilterLinkAdExtension Data Object - Campaign Management
Reserved.

## Syntax
```xml
<xs:complexType name="FilterLinkAdExtension" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:AdExtension">
      <xs:sequence>
        <xs:element minOccurs="0" name="AdExtensionHeaderType" nillable="true" type="tns:AdExtensionHeaderType" />
        <xs:element minOccurs="0" name="FinalMobileUrls" nillable="true" type="q53:ArrayOfstring" xmlns:q53="https://schemas.microsoft.com/2003/10/Serialization/Arrays" />
        <xs:element minOccurs="0" name="FinalUrls" nillable="true" type="q54:ArrayOfstring" xmlns:q54="https://schemas.microsoft.com/2003/10/Serialization/Arrays" />
        <xs:element minOccurs="0" name="Language" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="Texts" nillable="true" type="q55:ArrayOfstring" xmlns:q55="https://schemas.microsoft.com/2003/10/Serialization/Arrays" />
        <xs:element minOccurs="0" name="TrackingUrlTemplate" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="UrlCustomParameters" nillable="true" type="tns:CustomParameters" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [FilterLinkAdExtension](filterlinkadextension.md) object has the following elements: [AdExtensionHeaderType](#adextensionheadertype), [FinalMobileUrls](#finalmobileurls), [FinalUrls](#finalurls), [Language](#language), [Texts](#texts), [TrackingUrlTemplate](#trackingurltemplate), [UrlCustomParameters](#urlcustomparameters).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adextensionheadertype"></a>AdExtensionHeaderType|Reserved.|[AdExtensionHeaderType](adextensionheadertype.md)|
|<a name="finalmobileurls"></a>FinalMobileUrls|Reserved.|**string** array|
|<a name="finalurls"></a>FinalUrls|Reserved.|**string** array|
|<a name="language"></a>Language|Reserved.|**string**|
|<a name="texts"></a>Texts|Reserved.|**string** array|
|<a name="trackingurltemplate"></a>TrackingUrlTemplate|Reserved.|**string**|
|<a name="urlcustomparameters"></a>UrlCustomParameters|Reserved.|[CustomParameters](customparameters.md)|

The [FilterLinkAdExtension](filterlinkadextension.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsadextension"></a>Inherited Elements from AdExtension
The [FilterLinkAdExtension](filterlinkadextension.md) object derives from the [AdExtension](adextension.md) object, and inherits the following elements: [DevicePreference](#devicepreference), [ForwardCompatibilityMap](#forwardcompatibilitymap), [Id](#id), [Scheduling](#scheduling), [Status](#status), [Type](#type), [Version](#version). The descriptions below are specific to [FilterLinkAdExtension](filterlinkadextension.md), and might not apply to other objects that inherit the same elements from the [AdExtension](adextension.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="devicepreference"></a>DevicePreference|Reserved.|**long**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|Reserved.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|Reserved.|**long**|
|<a name="scheduling"></a>Scheduling|Reserved.|[Schedule](schedule.md)|
|<a name="status"></a>Status|Reserved.|[AdExtensionStatus](adextensionstatus.md)|
|<a name="type"></a>Type|Reserved.|**string**|
|<a name="version"></a>Version|Reserved.|**int**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

