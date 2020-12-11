---
title: ProfileType Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible types of profile criterions.
---
# ProfileType Value Set - Campaign Management
Defines the possible types of profile criterions.

## Syntax
```xml
<xs:simpleType name="ProfileType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="CompanyName">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">0</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="JobFunction">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="Industry">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">2</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

The [ProfileType](profiletype.md) value set has the following values: [CompanyName](#companyname), [Industry](#industry), [JobFunction](#jobfunction).

|Value|Description|
|-----------|---------------|
|<a name="companyname"></a>CompanyName|Target people at a specific company according to LinkedIn.|
|<a name="industry"></a>Industry|Target people in a specific industry according to LinkedIn.|
|<a name="jobfunction"></a>JobFunction|Target people in a specific job function according to LinkedIn.|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[GetProfileDataFileUrl](getprofiledatafileurl.md)  
[ProfileCriterion](profilecriterion.md)  
