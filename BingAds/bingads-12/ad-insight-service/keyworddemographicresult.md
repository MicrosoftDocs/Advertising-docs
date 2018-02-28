---
title: KeywordDemographicResult Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains the keyword and percentage of users by age and gender (if known) who searched for the specified keyword.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# KeywordDemographicResult Data Object - Ad Insight
Defines an object that contains the keyword and percentage of users by age and gender (if known) who searched for the specified keyword.

## Syntax
```xml
<xs:complexType name="KeywordDemographicResult" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Keyword" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="KeywordDemographics" nillable="true" type="tns:ArrayOfKeywordDemographic" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keyword"></a>Keyword|The keyword.|**string**|
|<a name="keyworddemographics"></a>KeywordDemographics|An array of [KeywordDemographic](../ad-insight-service/keyworddemographic.md) data objects that contains the percentage of users by age and gender (if known) that searched for the keyword on the device.|[KeywordDemographic](keyworddemographic.md) array|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity  

## Used By
[GetKeywordDemographics](getkeyworddemographics.md)  
