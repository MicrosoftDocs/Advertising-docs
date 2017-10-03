---
title: LanguageCriterion Data Object
ms.service: bing-ads-ad-insight
ms.topic: article
author: eric-urban
ms.author: eur
---
# LanguageCriterion Data Object
The language criterion that you can include when requesting keyword ideas or traffic estimates.

Suggestions are customized for the language you select.

## Syntax
```xml
<xs:complexType name="LanguageCriterion" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Criterion">
      <xs:sequence>
        <xs:element minOccurs="0" name="Language" nillable="true" type="xs:string" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="language"></a>Language|The language that you require.<br/><br/>Possible case-sensitive values are *English*, *French*, and *German*.|**string**|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Criterions  

## Used By
[LanguageSearchParameter](languagesearchparameter.md)  
