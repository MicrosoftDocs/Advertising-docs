---
title: NetworkType Value Set - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible search networks on which an ad can display.
---
# NetworkType Value Set - Ad Insight

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

Defines the possible search networks on which an ad can display. 

You can specify a network type when calling the [GetKeywordIdeas](../ad-insight-service/getkeywordideas.md) and [GetKeywordTrafficEstimates](../ad-insight-service/getkeywordtrafficestimates.md) operations. For more information about networks and ad distribution, see the [About Ad Distribution](http://help.bingads.microsoft.com/#apex/3/en/50871/0) help article.

## Syntax
```xml
<xs:simpleType name="NetworkType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="OwnedAndOperatedAndSyndicatedSearch" />
    <xs:enumeration value="OwnedAndOperatedOnly">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">2</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="SyndicatedSearchOnly">
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
|<a name="ownedandoperatedandsyndicatedsearch"></a>OwnedAndOperatedAndSyndicatedSearch|Indicates that you want keyword ideas or traffic estimates for ads on owned and operated networks, as well as syndicated search networks.|
|<a name="ownedandoperatedonly"></a>OwnedAndOperatedOnly|Indicates that you want keyword ideas or traffic estimates for ads on only owned and operated networks.<br /><br />Owned and operated networks refer to the Bing?, AOL, and Yahoo search networks.|
|<a name="syndicatedsearchonly"></a>SyndicatedSearchOnly|Indicates that you want keyword ideas or traffic estimates for ads on only syndicated search networks.<br /><br />Syndicated search refers to partner sites that host Bing?, AOL, and Yahoo search.|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V11  

## Used By
[NetworkCriterion](networkcriterion.md)  
