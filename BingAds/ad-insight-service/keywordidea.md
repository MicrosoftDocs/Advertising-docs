---
title: KeywordIdea Data Object
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains a suggested keyword with historical statistics, like monthly search volume, competition, suggested minimum bid, and ad impression share.
---
# KeywordIdea Data Object
Defines an object that contains a suggested keyword with historical statistics, like monthly search volume, competition, suggested minimum bid, and ad impression share.

## Syntax
```xml
<xs:complexType name="KeywordIdea" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AdGroupId" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="AdGroupName" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="AdImpressionShare" type="xs:double" />
    <xs:element minOccurs="0" name="Competition" type="q3:CompetitionLevel" xmlns:q3="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Common" />
    <xs:element minOccurs="0" name="Keyword" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="MonthlySearchCounts" nillable="true" type="q4:ArrayOflong" xmlns:q4="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
    <xs:element minOccurs="0" name="Relevance" type="xs:double" />
    <xs:element minOccurs="0" name="Source" type="q5:SourceType" xmlns:q5="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Common" />
    <xs:element minOccurs="0" name="SuggestedBid" type="xs:double" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupid"></a>AdGroupId|The negative ad group identifier that groups keyword ideas into suggested new ad groups. Keyword ideas for existing ad group identifiers is not supported.<br/><br/>If the ad group ID is null then the keyword idea *Source* element is set to *Seed*, and there is not any specific recommended ad group.|**long**|
|<a name="adgroupname"></a>AdGroupName|The suggested name of the ad group for the keyword idea.<br/><br/>If the ad group name is null then the keyword idea *Source* element is set to *Seed*, and there is not any specific recommended ad group.|**string**|
|<a name="adimpressionshare"></a>AdImpressionShare|Ad impression share is the number of impressions you've received divided by the total number of searches for the location and network you're targeting that matched the keyword exactly in the last calendar month.|**double**|
|<a name="competition"></a>Competition|Determined by the number of advertisers bidding on this keyword, relative to all other keywords across Bing Ads.|[CompetitionLevel](competitionlevel.md)|
|<a name="keyword"></a>Keyword|The suggested keyword.|**string**|
|<a name="monthlysearchcounts"></a>MonthlySearchCounts|The number of times this keyword was used as a search term for each month within the date range and targeting settings you?ve selected.<br/><br/>By default the size of the list is 12 and the last 12 months of available data are returned. The search counts are sorted in order starting with the most recent month's data at <code>MonthlySeachCounts[0]</code>.<br/><br/> It can take up to 72 hours for the previous calendar month?s data to be available. For example, if you request keyword ideas on August 1st, 2nd or 3rd, and July?s data is not ready, the response will be based on June?s data. If you do not include the [DateRangeSearchParameter](../ad-insight-service/daterangesearchparameter.md) in the [GetKeywordIdeas](../ad-insight-service/getkeywordideas.md) request, then you will not be able to confirm whether the first list item is data for the previous month, or the month prior. If the date range is specified and the most recent month's data is not yet available, then [GetKeywordIdeas](../ad-insight-service/getkeywordideas.md) will return an error. |**long**|
|<a name="relevance"></a>Relevance|The keyword relevance score.|**double**|
|<a name="source"></a>Source|The source or seed for the keyword.|[SourceType](sourcetype.md)|
|<a name="suggestedbid"></a>SuggestedBid|The suggested minimum bid for this keyword. We create this suggestion using the location and network criterion you included, along with the average cost-per-click (CPC) advertisers are paying for this keyword. This amount is only an estimate and your actual CPC may vary.|**double**|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity  

## Used By
[GetKeywordIdeas](getkeywordideas.md)  
