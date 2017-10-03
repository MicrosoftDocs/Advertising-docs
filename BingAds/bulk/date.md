---
title: Date Data Object
ms.service: bing-ads-bulk
ms.topic: article
author: eric-urban
ms.author: eur
---
# Date Data Object
Defines a calendar date by month, day, and year.

## Syntax
```xml
<xs:complexType name="Date" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element name="Day" type="xs:int" />
    <xs:element name="Month" type="xs:int" />
    <xs:element name="Year" type="xs:int" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="day"></a>Day|Specifies the day of the month.|**int**|
|<a name="month"></a>Month|Specifies the month.|**int**|
|<a name="year"></a>Year|Specifies the year.|**int**|

## Requirements
Service: [BulkService.svc v11](https://bulk.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/BulkService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[PerformanceStatsDateRange](performancestatsdaterange.md)  
