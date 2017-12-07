---
title: DateRangeSearchParameter Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: The date range search parameter that you can include when requesting keyword ideas.
---
# DateRangeSearchParameter Data Object - Ad Insight
The date range search parameter that you can include when requesting keyword ideas.

For more information about the significance of the date range search parameter, see *MonthlySearchCounts* with the [KeywordIdea](../ad-insight-service/keywordidea.md) object.

## Syntax
```xml
<xs:complexType name="DateRangeSearchParameter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:SearchParameter">
      <xs:sequence>
        <xs:element minOccurs="0" name="EndDate" nillable="true" type="q9:DayMonthAndYear" xmlns:q9="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" />
        <xs:element minOccurs="0" name="StartDate" nillable="true" type="q10:DayMonthAndYear" xmlns:q10="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="enddate"></a>EndDate|The end date range of monthly search counts for the returned keyword ideas.|[DayMonthAndYear](daymonthandyear.md)|
|<a name="startdate"></a>StartDate|The start date range of monthly search counts for the returned keyword ideas.|[DayMonthAndYear](daymonthandyear.md)|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: *http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.SearchParameters*  

