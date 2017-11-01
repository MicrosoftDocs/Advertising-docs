---
title: CompetitionSearchParameter Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: "article"
ms.date: 11/01/2017
author: eric-urban
ms.author: eur
description: The competition search parameter filter that you can include when requesting keyword ideas.
---
# CompetitionSearchParameter Data Object - Ad Insight
The competition search parameter filter that you can include when requesting keyword ideas.

If you do not include the competition search parameter when calling [GetKeywordIdeas](../ad-insight-service/getkeywordideas.md), then keyword ideas will be returned for all competition levels.

## Syntax
```xml
<xs:complexType name="CompetitionSearchParameter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:SearchParameter">
      <xs:sequence>
        <xs:element minOccurs="0" name="CompetitionLevels" nillable="true" type="q8:ArrayOfCompetitionLevel" xmlns:q8="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Common" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="competitionlevels"></a>CompetitionLevels|The competition levels that you want for the returned keyword ideas.<br/><br/>Competition levels are defined by the number of advertisers bidding on this keyword, relative to all other keywords across Bing Ads. Possible values are *Low*, *Medium*, and *High*.|[CompetitionLevel](competitionlevel.md) array|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.SearchParameters  

