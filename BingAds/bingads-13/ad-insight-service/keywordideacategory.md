---
title: KeywordIdeaCategory Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains a keyword idea category.
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# KeywordIdeaCategory Data Object - Ad Insight
Defines an object that contains a keyword idea category.

You can use the category identifier in the [CategorySearchParameter](categorysearchparameter.md) when calling [GetKeywordIdeas](getkeywordideas.md).

## Syntax
```xml
<xs:complexType name="KeywordIdeaCategory" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="CategoryId" type="xs:long" />
    <xs:element minOccurs="0" name="CategoryName" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="categoryid"></a>CategoryId|The Bing Ads identifier of the keyword idea category.|**long**|
|<a name="categoryname"></a>CategoryName|The name of the keyword idea category.|**string**|

## Requirements
Service: [AdInsightService.svc v13](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v13/AdInsightService.svc)  
Namespace: https\://bingads.microsoft.com/AdInsight/v13  

## Used By
[GetKeywordIdeaCategories](getkeywordideacategories.md)  
