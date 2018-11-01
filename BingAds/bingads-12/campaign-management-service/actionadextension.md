---
title: ActionAdExtension Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Reserved for future use.
---
# ActionAdExtension Data Object - Campaign Management
Reserved for future use.

## Syntax
```xml
<xs:complexType name="ActionAdExtension" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:AdExtension">
      <xs:sequence>
        <xs:element name="ActionType" type="tns:ActionAdExtensionActionType" />
        <xs:element minOccurs="0" name="FinalMobileUrls" nillable="true" type="q45:ArrayOfstring" xmlns:q45="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
        <xs:element minOccurs="0" name="FinalUrls" nillable="true" type="q46:ArrayOfstring" xmlns:q46="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
        <xs:element minOccurs="0" name="Language" nillable="true" type="xs:string" />
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
|<a name="actiontype"></a>ActionType|Reserved.|[ActionAdExtensionActionType](actionadextensionactiontype.md)|
|<a name="finalmobileurls"></a>FinalMobileUrls|Reserved.|**string** array|
|<a name="finalurls"></a>FinalUrls|Reserved.|**string** array|
|<a name="language"></a>Language|Reserved.|**string**|
|<a name="trackingurltemplate"></a>TrackingUrlTemplate|Reserved.|**string**|
|<a name="urlcustomparameters"></a>UrlCustomParameters|Reserved.|[CustomParameters](customparameters.md)|

The [ActionAdExtension](actionadextension.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsadextension"></a>Inherited Elements from AdExtension
The [ActionAdExtension](actionadextension.md) object derives from the [AdExtension](adextension.md) object, and inherits the following elements. The descriptions below are specific to [ActionAdExtension](actionadextension.md), and might not apply to other objects that inherit the same elements from the [AdExtension](adextension.md) object.  

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
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

