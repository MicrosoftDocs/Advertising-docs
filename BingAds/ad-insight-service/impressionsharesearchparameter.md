---
title: ImpressionShareSearchParameter Data Object
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: The impression share search parameter filter that you can include when requesting keyword ideas.
---
# ImpressionShareSearchParameter Data Object
The impression share search parameter filter that you can include when requesting keyword ideas.

If you do not include the impression share search parameter when calling [GetKeywordIdeas](../ad-insight-service/getkeywordideas.md), then keyword ideas will be returned regardless of impression share.

## Syntax
```xml
<xs:complexType name="ImpressionShareSearchParameter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:SearchParameter">
      <xs:sequence>
        <xs:element minOccurs="0" name="Maximum" nillable="true" type="xs:double" />
        <xs:element minOccurs="0" name="Minimum" nillable="true" type="xs:double" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="maximum"></a>Maximum|The maximum impression share that you want for keyword ideas.|**double**|
|<a name="minimum"></a>Minimum|The minimum impression share that you want for keyword ideas.|**double**|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.SearchParameters  

