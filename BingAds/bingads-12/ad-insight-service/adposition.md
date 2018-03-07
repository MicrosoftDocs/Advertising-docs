---
title: AdPosition Value Set - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible positions of an ad in the search results or on a content-based webpage.
---
# AdPosition Value Set - Ad Insight
Defines the possible positions of an ad in the search results or on a content-based webpage.

## Syntax
```xml
<xs:simpleType name="AdPosition" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="All" />
    <xs:enumeration value="MainLine1" />
    <xs:enumeration value="MainLine2" />
    <xs:enumeration value="MainLine3" />
    <xs:enumeration value="MainLine4" />
    <xs:enumeration value="SideBar1" />
    <xs:enumeration value="SideBar2" />
    <xs:enumeration value="SideBar3" />
    <xs:enumeration value="SideBar4" />
    <xs:enumeration value="SideBar5" />
    <xs:enumeration value="SideBar6" />
    <xs:enumeration value="SideBar7" />
    <xs:enumeration value="SideBar8" />
    <xs:enumeration value="SideBar9" />
    <xs:enumeration value="SideBar10" />
    <xs:enumeration value="Aggregate" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="aggregate"></a>Aggregate|Aggregates the data for all supported positions.<br /><br />The following are examples of how the data is aggregated: Average bid would be the average bid of all the keywords in all the ad positions; Impressions is the sum of the number of impressions in all the ad positions; Clicks is the sum of the number of clicks in all the ad positions; Total cost is the sum of the cost of using the keywords in all the ad positions; AverageCTR is calculated by dividing the number of clicks by the number of impressions and multiplying the result by 100; AverageCPC is calculated by dividing the cost of all clicks by the number of clicks.|
|<a name="all"></a>All|Indicates all search result positions.|
|<a name="mainline1"></a>MainLine1|The first ad to appear at the top of the search results page.|
|<a name="mainline2"></a>MainLine2|The second ad to appear at the top of the search results page.|
|<a name="mainline3"></a>MainLine3|The third ad to appear at the top of the search results page.|
|<a name="mainline4"></a>MainLine4|The fourth ad to appear at the top of the search results page.|
|<a name="sidebar1"></a>SideBar1|The first ad to appear on the right side of the first search results page.|
|<a name="sidebar10"></a>SideBar10|The tenth ad to appear on the right side of the first search results page.|
|<a name="sidebar2"></a>SideBar2|The second ad to appear on the right side of the first search results page.|
|<a name="sidebar3"></a>SideBar3|The third ad to appear on the right side of the first search results page.|
|<a name="sidebar4"></a>SideBar4|The fourth ad to appear on the right side of the first search results page.|
|<a name="sidebar5"></a>SideBar5|The fifth ad to appear on the right side of the first search results page.|
|<a name="sidebar6"></a>SideBar6|The sixth ad to appear on the right side of the first search results page.|
|<a name="sidebar7"></a>SideBar7|The seventh ad to appear on the right side of the first search results page.|
|<a name="sidebar8"></a>SideBar8|The eighth ad to appear on the right side of the first search results page.|
|<a name="sidebar9"></a>SideBar9|The ninth ad to appear on the right side of the first search results page.|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V12  

## Used By
[GetHistoricalKeywordPerformance](gethistoricalkeywordperformance.md)  
[KeywordKPI](keywordkpi.md)  
