---
title: DeviceSearchParameter Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: "article"
ms.date: 11/1/2017
author: eric-urban
ms.author: eur
description: The device search parameter filter that you can include when requesting keyword ideas.
---
# DeviceSearchParameter Data Object - Ad Insight
The device search parameter filter that you can include when requesting keyword ideas.

If you do not include the device search parameter when calling [GetKeywordIdeas](../ad-insight-service/getkeywordideas.md), then keyword ideas will be returned for all devices.

## Syntax
```xml
<xs:complexType name="DeviceSearchParameter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:SearchParameter">
      <xs:sequence>
        <xs:element minOccurs="0" name="Device" nillable="true" type="q6:DeviceCriterion" xmlns:q6="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Criterions" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="device"></a>Device|The device criterion for the returned keyword ideas.|[DeviceCriterion](devicecriterion.md)|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.SearchParameters  

