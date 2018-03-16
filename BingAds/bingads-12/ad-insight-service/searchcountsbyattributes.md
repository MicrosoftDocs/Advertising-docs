---
title: SearchCountsByAttributes Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains a list of keyword historical search counts for the corresponding device attribute.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# SearchCountsByAttributes Data Object - Ad Insight
Defines an object that contains a list of keyword historical search counts for the corresponding device attribute. Each search count in the list is aggregated by day, month, and year.

## Syntax
```xml
<xs:complexType name="SearchCountsByAttributes" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Device" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="HistoricalSearchCounts" nillable="true" type="tns:ArrayOfHistoricalSearchCountPeriodic" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="device"></a>Device|The device of the user who entered the search query.|**string**|
|<a name="historicalsearchcounts"></a>HistoricalSearchCounts|An array of [HistoricalSearchCountPeriodic](historicalsearchcountperiodic.md) objects that contain a count of the number of times that the keyword was used in a search query. The array contains an item for each month in the specified date range. The items are ordered by calendar month.<br /><br />For each requested keyword that has no available data, the [HistoricalSearchCountPeriodic](historicalsearchcountperiodic.md) element will be nil.|[HistoricalSearchCountPeriodic](historicalsearchcountperiodic.md) array|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity  

## Used By
[KeywordSearchCount](keywordsearchcount.md)  
