---
title: KeywordEstimator Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Contains a keyword estimators with your keyword level filter criteria for traffic estimates.
---
# KeywordEstimator Data Object - Ad Insight
Contains a keyword estimators with your keyword level filter criteria for traffic estimates.

## Syntax
```xml
<xs:complexType name="KeywordEstimator" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Keyword" nillable="true" type="q6:Keyword" xmlns:q6="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Common" />
    <xs:element minOccurs="0" name="MaxCpc" nillable="true" type="xs:double" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keyword"></a>Keyword|The keyword used for traffic estimates.<br/><br/>You can request estimates for Phrase and Broad match types.|[Keyword](keyword.md)|
|<a name="maxcpc"></a>MaxCpc|The maximum cost per click filter criteria for the keyword.<br/><br/>You can set the default maximum CPC for all of the ad group's keywords using the *MaxCpc* element of the [AdGroupEstimator](adgroupestimator.md) object. Use the keyword estimator if you want to override the max CPC for a specific keyword.|**double**|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity  

## Used By
[AdGroupEstimator](adgroupestimator.md)  
