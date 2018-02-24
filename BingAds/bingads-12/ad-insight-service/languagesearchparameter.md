---
title: LanguageSearchParameter Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: The language search parameter filter that you can include when requesting keyword ideas.
---
# LanguageSearchParameter Data Object - Ad Insight
The language search parameter filter that you can include when requesting keyword ideas.

If you do not include the language search parameter when calling [GetKeywordIdeas](../ad-insight-service/getkeywordideas.md), then keyword ideas will be returned for all languages.

## Syntax
```xml
<xs:complexType name="LanguageSearchParameter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:SearchParameter">
      <xs:sequence>
        <xs:element minOccurs="0" name="Languages" nillable="true" type="q7:ArrayOfLanguageCriterion" xmlns:q7="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Criterions" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="languages"></a>Languages|The language criterion list for the returned keyword ideas.|[LanguageCriterion](languagecriterion.md) array|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.SearchParameters  

