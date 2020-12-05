---
title: FlyerAdExtension Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the FlyerAdExtension Data Object.
---
# FlyerAdExtension Data Object - Campaign Management
Defines the FlyerAdExtension Data Object.

## Syntax
```xml
<xs:complexType name="FlyerAdExtension" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:AdExtension">
      <xs:sequence>
        <xs:element minOccurs="0" name="Description" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="FinalAppUrls" nillable="true" type="tns:ArrayOfAppUrl" />
        <xs:element minOccurs="0" name="FinalMobileUrls" nillable="true" type="q57:ArrayOfstring" xmlns:q57="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
        <xs:element minOccurs="0" name="FinalUrlSuffix" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="FinalUrls" nillable="true" type="q58:ArrayOfstring" xmlns:q58="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
        <xs:element minOccurs="0" name="FlyerName" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="ImageMediaIds" nillable="true" type="q59:ArrayOflong" xmlns:q59="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
        <xs:element minOccurs="0" name="ImageMediaUrls" nillable="true" type="q60:ArrayOfstring" xmlns:q60="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
        <xs:element minOccurs="0" name="StoreId" nillable="true" type="xs:long" />
        <xs:element minOccurs="0" name="TrackingUrlTemplate" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="UrlCustomParameters" nillable="true" type="tns:CustomParameters" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [FlyerAdExtension](flyeradextension.md) object has the following elements: [Description](#description), [FinalAppUrls](#finalappurls), [FinalMobileUrls](#finalmobileurls), [FinalUrls](#finalurls), [FinalUrlSuffix](#finalurlsuffix), [FlyerName](#flyername), [ImageMediaIds](#imagemediaids), [ImageMediaUrls](#imagemediaurls), [StoreId](#storeid), [TrackingUrlTemplate](#trackingurltemplate), [UrlCustomParameters](#urlcustomparameters).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="description"></a>Description|Reserved.|**string**|
|<a name="finalappurls"></a>FinalAppUrls|Reserved.|[AppUrl](appurl.md) array|
|<a name="finalmobileurls"></a>FinalMobileUrls|Reserved.|**string** array|
|<a name="finalurls"></a>FinalUrls|Reserved.|**string** array|
|<a name="finalurlsuffix"></a>FinalUrlSuffix|Reserved.|**string**|
|<a name="flyername"></a>FlyerName|Reserved.|**string**|
|<a name="imagemediaids"></a>ImageMediaIds|Reserved.|**long** array|
|<a name="imagemediaurls"></a>ImageMediaUrls|Reserved.|**string** array|
|<a name="storeid"></a>StoreId|Reserved.|**long**|
|<a name="trackingurltemplate"></a>TrackingUrlTemplate|Reserved.|**string**|
|<a name="urlcustomparameters"></a>UrlCustomParameters|Reserved.|[CustomParameters](customparameters.md)|

The [FlyerAdExtension](flyeradextension.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsadextension"></a>Inherited Elements from AdExtension
The [FlyerAdExtension](flyeradextension.md) object derives from the [AdExtension](adextension.md) object, and inherits the following elements: [DevicePreference](#devicepreference), [ForwardCompatibilityMap](#forwardcompatibilitymap), [Id](#id), [Scheduling](#scheduling), [Status](#status), [Type](#type), [Version](#version). The descriptions below are specific to [FlyerAdExtension](flyeradextension.md), and might not apply to other objects that inherit the same elements from the [AdExtension](adextension.md) object.  

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

