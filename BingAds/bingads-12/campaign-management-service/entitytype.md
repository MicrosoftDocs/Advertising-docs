---
title: EntityType Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible types of entities.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.
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
    <xs:enumeration value="Target">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">3</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Ad">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">4</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Keyword">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">5</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdExtension">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">6</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroupCriterion">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">7</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="ad"></a>Ad|Request editorial appeal or status for ads.|
|<a name="adextension"></a>AdExtension|Reserved for future use.|
|<a name="adgroup"></a>AdGroup|Reserved for future use.|
|<a name="adgroupcriterion"></a>AdGroupCriterion|Reserved for future use.|
|<a name="campaign"></a>Campaign|Reserved for future use.|
|<a name="keyword"></a>Keyword|Request editorial appeal or status for keywords.|
|<a name="target"></a>Target|Reserved for future use.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[AppealEditorialRejections](appealeditorialrejections.md)  
[DeleteLabelAssociations](deletelabelassociations.md)  
[GetEditorialReasonsByIds](geteditorialreasonsbyids.md)  
[GetLabelAssociationsByEntityIds](getlabelassociationsbyentityids.md)  
[GetLabelAssociationsByLabelIds](getlabelassociationsbylabelids.md)  
[SetLabelAssociations](setlabelassociations.md)  
