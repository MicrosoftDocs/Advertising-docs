---
title: SearchVolumeSearchParameter Data Object
ms.service: bing-ads-ad-insight
ms.topic: article
author: eric-urban
ms.author: eur
---
# SearchVolumeSearchParameter Data Object
The search volume search parameter filter that you can include when requesting keyword ideas.

If you do not include the search volume search parameter when calling [GetKeywordIdeas](../ad-insight/getkeywordideas.md), then keyword ideas will be returned regardless of search volume.

## Syntax
```xml
<xs:complexType name="SearchVolumeSearchParameter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:SearchParameter">
      <xs:sequence>
        <xs:element minOccurs="0" name="Maximum" nillable="true" type="xs:long" />
        <xs:element minOccurs="0" name="Minimum" nillable="true" type="xs:long" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="maximum"></a>Maximum|The maximum search volume that you want for keyword ideas.|**long**|
|<a name="minimum"></a>Minimum|The minimum search volume that you want for keyword ideas.|**long**|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.SearchParameters  

