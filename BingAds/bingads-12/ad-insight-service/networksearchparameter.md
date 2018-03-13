---
title: NetworkSearchParameter Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: The network search parameter filter that you can include when requesting keyword ideas.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# NetworkSearchParameter Data Object - Ad Insight
The network search parameter filter that you can include when requesting keyword ideas.

If you do not include the network search parameter when calling [GetKeywordIdeas](getkeywordideas.md), then keyword ideas will be returned for all networks.

## Syntax
```xml
<xs:complexType name="NetworkSearchParameter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:SearchParameter">
      <xs:sequence>
        <xs:element minOccurs="0" name="Network" nillable="true" type="q5:NetworkCriterion" xmlns:q5="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="network"></a>Network|The network criterion for the returned keyword ideas.|[NetworkCriterion](networkcriterion.md)|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.SearchParameters  

