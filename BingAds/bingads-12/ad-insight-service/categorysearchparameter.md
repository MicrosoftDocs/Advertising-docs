---
title: CategorySearchParameter Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: The keyword category search parameter that you can use as a seed for new keyword ideas.
---
# CategorySearchParameter Data Object - Ad Insight

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

The keyword category search parameter that you can use as a seed for new keyword ideas.

## Syntax
```xml
<xs:complexType name="CategorySearchParameter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:SearchParameter">
      <xs:sequence>
        <xs:element minOccurs="0" name="CategoryId" type="xs:long" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="categoryid"></a>CategoryId|The Bing Ads identifier for the keyword category.<br/><br/>To get a list of keyword category identifiers, use the [GetKeywordIdeaCategories](/bingads/ad-insight-service/getkeywordideacategories.md) service operation.|**long**|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.SearchParameters  

