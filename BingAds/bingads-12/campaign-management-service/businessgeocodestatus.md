---
title: BusinessGeoCodeStatus Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible status values that indicate the progress of determining the latitude and longitude values of a business.
---
# BusinessGeoCodeStatus Value Set - Campaign Management
Defines the possible status values that indicate the progress of determining the latitude and longitude values of a business.

## Syntax
```xml
<xs:simpleType name="BusinessGeoCodeStatus" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Pending" />
    <xs:enumeration value="Complete" />
    <xs:enumeration value="Invalid" />
    <xs:enumeration value="Failed" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="complete"></a>Complete|Successfully determined the latitude and longitude of the business.|
|<a name="failed"></a>Failed|Unable to determine the latitude and longitude of the business.|
|<a name="invalid"></a>Invalid|Unable to determine the latitude and longitude of the business, possibly because the address did not resolve.|
|<a name="pending"></a>Pending|In the process of determining the latitude and longitude of the business.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[LocationAdExtension](locationadextension.md)  
