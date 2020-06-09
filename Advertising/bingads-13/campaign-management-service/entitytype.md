---
title: EntityType Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible types of entities.
---
# EntityType Value Set - Campaign Management
Defines the possible types of entities.

## Syntax
```xml
<xs:simpleType name="EntityType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Campaign">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroup">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">2</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Ad">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">3</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Keyword">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">4</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

The [EntityType](entitytype.md) value set has the following values: [Ad](#ad), [AdGroup](#adgroup), [Campaign](#campaign), [Keyword](#keyword).

|Value|Description|
|-----------|---------------|
|<a name="ad"></a>Ad|Request editorial appeal or status for ads.|
|<a name="adgroup"></a>AdGroup|Reserved for future use.|
|<a name="campaign"></a>Campaign|Reserved for future use.|
|<a name="keyword"></a>Keyword|Request editorial appeal or status for keywords.|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[AppealEditorialRejections](appealeditorialrejections.md)  
[DeleteLabelAssociations](deletelabelassociations.md)  
[GetEditorialReasonsByIds](geteditorialreasonsbyids.md)  
[GetLabelAssociationsByEntityIds](getlabelassociationsbyentityids.md)  
[GetLabelAssociationsByLabelIds](getlabelassociationsbylabelids.md)  
[SetLabelAssociations](setlabelassociations.md)  
