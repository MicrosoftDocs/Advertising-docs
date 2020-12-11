---
title: ImportAdditionalField Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a list of optional import properties that you can request when calling GetImportJobsByIds and GetImportResults.
---
# ImportAdditionalField Value Set - Campaign Management
Defines a list of optional import properties that you can request when calling [GetImportJobsByIds](getimportjobsbyids.md#returnadditionalfields) and [GetImportResults](getimportresults.md#returnadditionalfields). The additional field values enable you to get the latest features using the current version of Campaign Management API, and in the next version the corresponding properties will be included in the ad by default. 

## Syntax
```xml
<xs:simpleType name="ImportAdditionalField" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="None">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">0</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="NotificationEmail">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="AutoDeviceBidOptimization">
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

The [ImportAdditionalField](importadditionalfield.md) value set has the following values: [AutoDeviceBidOptimization](#autodevicebidoptimization), [None](#none), [NotificationEmail](#notificationemail).

|Value|Description|
|-----------|---------------|
|<a name="autodevicebidoptimization"></a>AutoDeviceBidOptimization|Request that the [AutoDeviceBidOptimization](googleimportoption.md#autodevicebidoptimization) element be included within each returned [GoogleImportOption](googleimportoption.md) object.|
|<a name="none"></a>None|Reserved for internal use.|
|<a name="notificationemail"></a>NotificationEmail|Request that the [NotificationEmail](googleimportjob.md#notificationemail) element be included within each returned [GoogleImportJob](googleimportjob.md) object.|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[GetImportJobsByIds](getimportjobsbyids.md)  
[GetImportResults](getimportresults.md)  
