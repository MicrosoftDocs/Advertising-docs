---
title: MediaAssociation Data Object
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# MediaAssociation Data Object
Defines an object that represents the identified media and an associated entity, for example media associated with an ad group.

You can get this object by calling [GetMediaAssociations](../campaign-management/getmediaassociations.md), and then use the media identifier with [GetMediaMetaDataByIds](../campaign-management/getmediametadatabyids.md), for example.

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
|<a name="mediaenabledentity"></a>MediaEnabledEntity|Determines the type of media to get. Currently only ImageAdExtension is supported.|[MediaEnabledEntityFilter](mediaenabledentityfilter.md)|
|<a name="mediaid"></a>MediaId|The system identifier of the media.|**long**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[GetMediaAssociations](getmediaassociations.md)  
