---
title: DomainCategory Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains a domain category with website coverage.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# DomainCategory Data Object - Ad Insight
Defines an object that contains a domain category with website coverage. 

## Syntax
```xml
<xs:complexType name="DomainCategory" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Bid" type="xs:double" />
    <xs:element minOccurs="0" name="CategoryName" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Coverage" type="xs:double" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="bid"></a>Bid|Reserved for future use.|**double**|
|<a name="categoryname"></a>CategoryName|The category name.<br/><br/>Up to three category levels can be returned, and will be separated by a forward slash ("/"). For example the returned category might be *US/CA/SFO*.|**string**|
|<a name="coverage"></a>Coverage|A score from 0.0 to 1.0 that indicates the percentage of pages in the requested language that belong to a particular domain out of all the pages that Bing has indexed for the same language your website's domain.<br/><br/>In other words coverage is the percentage of webpages that match a category and language divided by the total number of webpages using the same language in the domain.<br/><br/>For example, if the category *US/CA/SFO* matches 500 english webpages and *US/CA* matches 1,000 english webpages, then the coverage will be 0.50 (50 percent).|**double**|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity  

## Used By
[GetDomainCategories](getdomaincategories.md)  
