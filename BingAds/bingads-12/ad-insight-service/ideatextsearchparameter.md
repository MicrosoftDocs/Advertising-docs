---
title: IdeaTextSearchParameter Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: The idea text search parameter filter that you can include when requesting keyword ideas.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# IdeaTextSearchParameter Data Object - Ad Insight
The idea text search parameter filter that you can include when requesting keyword ideas.

Use these options to refine what keywords are returned when calling [GetKeywordIdeas](getkeywordideas.md). You can limit the keyword ideas to include or exclude specific keywords. 

## Syntax
```xml
<xs:complexType name="IdeaTextSearchParameter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:SearchParameter">
      <xs:sequence>
        <xs:element minOccurs="0" name="Excluded" nillable="true" type="q2:ArrayOfKeyword" xmlns:q2="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Common" />
        <xs:element minOccurs="0" name="Included" nillable="true" type="q3:ArrayOfKeyword" xmlns:q3="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Common" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="excluded"></a>Excluded|The list of keywords that you explicitly want excluded from the list of returned keyword ideas.<br/><br/>The match type of each keyword must be set to Broad.|[Keyword](keyword.md) array|
|<a name="included"></a>Included|The list of keywords that you explicitly want included in the list of returned keyword ideas.<br/><br/>The match type of each keyword must be set to Broad.|[Keyword](keyword.md) array|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.SearchParameters  

