---
title: AdGroupBidLandscapeInput Data Object
ms.service: bing-ads-ad-insight
ms.topic: article
author: eric-urban
ms.author: eur
---
# AdGroupBidLandscapeInput Data Object
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
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity  

## Used By
[GetBidLandscapeByAdGroupIds](getbidlandscapebyadgroupids.md)  
