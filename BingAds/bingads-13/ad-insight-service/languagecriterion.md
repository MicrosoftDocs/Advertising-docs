---
title: LanguageCriterion Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: The language criterion that you can include when requesting keyword ideas or traffic estimates.
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# LanguageCriterion Data Object - Ad Insight
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
Service: [AdInsightService.svc v13](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v13/AdInsightService.svc)  
Namespace: https\://bingads.microsoft.com/AdInsight/v13  

## Used By
[LanguageSearchParameter](languagesearchparameter.md)  
