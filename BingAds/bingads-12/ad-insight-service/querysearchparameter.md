---
title: QuerySearchParameter Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: The query search parameter that you can use as a seed for new keyword ideas.
---
# QuerySearchParameter Data Object - Ad Insight
The query search parameter that you can use as a seed for new keyword ideas.

## Syntax
```xml
<xs:complexType name="QuerySearchParameter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:SearchParameter">
      <xs:sequence>
        <xs:element minOccurs="0" name="Queries" nillable="true" type="q1:ArrayOfstring" xmlns:q1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="queries"></a>Queries|Up to 200 words or phrases that describe what you're advertising.|**string** array|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.SearchParameters  

