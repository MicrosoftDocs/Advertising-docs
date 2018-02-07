---
title: LocationSearchParameter Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: The location search parameter filter that you can include when requesting keyword ideas.
---
# LocationSearchParameter Data Object - Ad Insight

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

The location search parameter filter that you can include when requesting keyword ideas.

If you do not include the location search parameter when calling [GetKeywordIdeas](../ad-insight-service/getkeywordideas.md), then keyword ideas will be returned for all locations.

## Syntax
```xml
<xs:complexType name="LocationSearchParameter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:SearchParameter">
      <xs:sequence>
        <xs:element minOccurs="0" name="Locations" nillable="true" type="q4:ArrayOfLocationCriterion" xmlns:q4="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Criterions" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="locations"></a>Locations|The location criterion list for the returned keyword ideas.|[LocationCriterion](locationcriterion.md) array|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.SearchParameters  

