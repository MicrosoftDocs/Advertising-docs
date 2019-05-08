---
title: MediaAssociation Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that represents the identified media and an associated entity, for example media associated with an ad group.
---
# MediaAssociation Data Object - Campaign Management
Defines an object that represents the identified media and an associated entity, for example media associated with an ad group.

You can get this object by calling [GetMediaAssociations](getmediaassociations.md), and then use the media identifier with [GetMediaMetaDataByIds](getmediametadatabyids.md), for example.

## Syntax
```xml
<xs:complexType name="MediaAssociation" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="EntityId" type="xs:long" />
    <xs:element minOccurs="0" name="MediaEnabledEntity" type="tns:MediaEnabledEntityFilter" />
    <xs:element minOccurs="0" name="MediaId" type="xs:long" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="entityid"></a>EntityId|The system identifier of the media enabled entity, for example the identifier of an ImageAdExtension.|**long**|
|<a name="mediaenabledentity"></a>MediaEnabledEntity|Determines the type of media to get.<br/><br/>Currently only ImageAdExtension is supported.|[MediaEnabledEntityFilter](mediaenabledentityfilter.md)|
|<a name="mediaid"></a>MediaId|The system identifier of the media.|**long**|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[GetMediaAssociations](getmediaassociations.md)  
