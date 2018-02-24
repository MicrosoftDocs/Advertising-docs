---
title: ExcludeAccountKeywordsSearchParameter Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: The exclude account keywords search parameter filter that you can include when requesting keyword ideas.
---
# ExcludeAccountKeywordsSearchParameter Data Object - Ad Insight
The exclude account keywords search parameter filter that you can include when requesting keyword ideas.

If you do not include the exclude account keywords search parameter when calling [GetKeywordIdeas](/bingads/ad-insight-service/getkeywordideas.md), then keyword ideas will be returned whether or not they already exist in your account.

## Syntax
```xml
<xs:complexType name="ExcludeAccountKeywordsSearchParameter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:SearchParameter">
      <xs:sequence>
        <xs:element minOccurs="0" name="ExcludeAccountKeywords" type="xs:boolean" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="excludeaccountkeywords"></a>ExcludeAccountKeywords|Determines whether or not to exclude existing account keywords from the returned keyword ideas.<br/><br/>By default your existing account keywords will be included with the keyword idea data e.g., suggested bid. If you set the element *True* then the keyword ideas will not include any keywords for the same match type that already exist in your account.|**boolean**|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.SearchParameters  

