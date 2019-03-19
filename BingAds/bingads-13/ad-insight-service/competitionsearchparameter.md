---
title: CompetitionSearchParameter Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: The competition search parameter filter that you can include when requesting keyword ideas.
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# CompetitionSearchParameter Data Object - Ad Insight
The competition search parameter filter that you can include when requesting keyword ideas.

If you do not include the competition search parameter when calling [GetKeywordIdeas](getkeywordideas.md), then keyword ideas will be returned for all competition levels.

## Syntax
```xml
<xs:complexType name="CompetitionSearchParameter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:SearchParameter">
      <xs:sequence>
        <xs:element minOccurs="0" name="CompetitionLevels" nillable="true" type="tns:ArrayOfCompetitionLevel" />
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
Service: [AdInsightService.svc v13](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v13/AdInsightService.svc)  
Namespace: https\://bingads.microsoft.com/AdInsight/v13  

