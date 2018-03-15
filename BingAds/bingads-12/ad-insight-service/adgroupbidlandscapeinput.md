---
title: AdGroupBidLandscapeInput Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains the requested bid landscape type for the corresponding ad group identifier.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# AdGroupBidLandscapeInput Data Object - Ad Insight
Defines an object that contains the requested bid landscape type for the corresponding ad group identifier.

## Syntax
```xml
<xs:complexType name="AdGroupBidLandscapeInput" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AdGroupBidLandscapeType" type="tns:AdGroupBidLandscapeType" />
    <xs:element minOccurs="0" name="AdGroupId" type="xs:long" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupbidlandscapetype"></a>AdGroupBidLandscapeType|Determines whether all or a subset of an ad group's existing keywords should be used to determine the bid landscape.<br /><br />If not specified in a request, the default value is Uniform.|[AdGroupBidLandscapeType](adgroupbidlandscapetype.md)|
|<a name="adgroupid"></a>AdGroupId|The ad group identifier.|**long**|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity  

## Used By
[GetBidLandscapeByAdGroupIds](getbidlandscapebyadgroupids.md)  
