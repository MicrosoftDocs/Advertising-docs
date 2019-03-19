---
title: QuerySearchParameter Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: The query search parameter that you can use as a seed for new keyword ideas.
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# QuerySearchParameter Data Object - Ad Insight
The query search parameter that you can use as a seed for new keyword ideas.

## Syntax
```xml
<xs:complexType name="QuerySearchParameter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:SearchParameter">
      <xs:sequence>
        <xs:element minOccurs="0" name="Queries" nillable="true" type="q22:ArrayOfstring" xmlns:q22="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
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
Service: [AdInsightService.svc v13](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v13/AdInsightService.svc)  
Namespace: https\://bingads.microsoft.com/AdInsight/v13  

