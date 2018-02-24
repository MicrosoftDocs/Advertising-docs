---
title: CompetitionLevel Value Set - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Competition levels are defined by the number of advertisers bidding on this keyword, relative to all other keywords across Bing Ads.
---
# CompetitionLevel Value Set - Ad Insight
Competition levels are defined by the number of advertisers bidding on this keyword, relative to all other keywords across Bing Ads. 

You can specify competition levels when calling the [GetKeywordIdeas](../ad-insight-service/getkeywordideas.md) operation.

## Syntax
```xml
<xs:simpleType name="CompetitionLevel" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Low">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Medium">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">2</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="High">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">3</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="high"></a>High|The competition level is high.|
|<a name="low"></a>Low|The competition level is low.|
|<a name="medium"></a>Medium|The competition level is medium.|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V11  

## Used By
[CompetitionSearchParameter](competitionsearchparameter.md)  
[KeywordIdea](keywordidea.md)  
