---
title: SearchVolumeSearchParameter Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: The search volume search parameter filter that you can include when requesting keyword ideas.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# SearchVolumeSearchParameter Data Object - Ad Insight
The search volume search parameter filter that you can include when requesting keyword ideas.

If you do not include the search volume search parameter when calling [GetKeywordIdeas](getkeywordideas.md), then keyword ideas will be returned regardless of search volume.

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
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.SearchParameters  

