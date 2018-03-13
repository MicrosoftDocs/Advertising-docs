---
title: AuctionInsightKpi Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an auction insight key performance indicator.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# AuctionInsightKpi Data Object - Ad Insight
Defines an auction insight key performance indicator.

> [!NOTE]
> Reserved for future use.

## Syntax
```xml
<xs:complexType name="AuctionInsightKpi" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Segment" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="ImpressionShare" type="xs:double" />
    <xs:element minOccurs="0" name="OverlapRate" type="xs:double" />
    <xs:element minOccurs="0" name="AveragePosition" type="xs:double" />
    <xs:element minOccurs="0" name="AboveRate" type="xs:double" />
    <xs:element minOccurs="0" name="TopOfPageRate" type="xs:double" />
    <xs:element minOccurs="0" name="OutrankingShare" type="xs:double" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="aboverate"></a>AboveRate|Reserved.|**double**|
|<a name="averageposition"></a>AveragePosition|Reserved.|**double**|
|<a name="impressionshare"></a>ImpressionShare|Reserved.|**double**|
|<a name="outrankingshare"></a>OutrankingShare|Reserved.|**double**|
|<a name="overlaprate"></a>OverlapRate|Reserved.|**double**|
|<a name="segment"></a>Segment|Reserved.|**string**|
|<a name="topofpagerate"></a>TopOfPageRate|Reserved.|**double**|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity  

## Used By
[AuctionInsightEntry](auctioninsightentry.md)  
