---
title: HistoricalSearchCountPeriodic Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains the number of times that the keyword was used in a search query during the specified time period.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# HistoricalSearchCountPeriodic Data Object - Ad Insight
Defines an object that contains the number of times that the keyword was used in a search query during the specified time period.

## Syntax
```xml
<xs:complexType name="HistoricalSearchCountPeriodic" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="SearchCount" type="xs:long" />
    <xs:element minOccurs="0" name="DayMonthAndYear" nillable="true" type="tns:DayMonthAndYear" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="daymonthandyear"></a>DayMonthAndYear|The time period in which the count was captured. The type of aggregation (daily, weekly, or monthly) that you specify in the request determines the length of the time period. For example, if you specified weekly aggregation, the time period is a week and the date is the Sunday of the week when the count was captured.|[DayMonthAndYear](daymonthandyear.md)|
|<a name="searchcount"></a>SearchCount|The number of times that the keyword was used in a search query on the specified device type during the time period. The count aggregates data from all specified countries.|**long**|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity  

## Used By
[SearchCountsByAttributes](searchcountsbyattributes.md)  
