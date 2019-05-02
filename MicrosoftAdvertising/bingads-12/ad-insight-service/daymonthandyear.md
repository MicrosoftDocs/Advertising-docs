---
title: DayMonthAndYear Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that you use to specify the start and end dates of a date range.
---
# DayMonthAndYear Data Object - Ad Insight
Defines an object that you use to specify the start and end dates of a date range.

## Syntax
```xml
<xs:complexType name="DayMonthAndYear" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Day" type="xs:int" />
    <xs:element minOccurs="0" name="Month" type="xs:int" />
    <xs:element minOccurs="0" name="Year" type="xs:int" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="day"></a>Day|The day of the month.|**int**|
|<a name="month"></a>Month|The month specified as an integer value in the range of 1 through 12, where 1 is January and 12 is December.|**int**|
|<a name="year"></a>Year|The year specified as a four-digit integer value.|**int**|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity  

## Used By
[AdGroupBidLandscape](adgroupbidlandscape.md)  
[DateRangeSearchParameter](daterangesearchparameter.md)  
[GetHistoricalSearchCount](gethistoricalsearchcount.md)  
[HistoricalSearchCountPeriodic](historicalsearchcountperiodic.md)  
[KeywordBidLandscape](keywordbidlandscape.md)  
