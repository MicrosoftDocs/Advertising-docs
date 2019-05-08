---
title: DeviceSearchParameter Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: The device search parameter filter that you can include when requesting keyword ideas.
---
# DeviceSearchParameter Data Object - Ad Insight
The device search parameter filter that you can include when requesting keyword ideas.

If you do not include the device search parameter when calling [GetKeywordIdeas](getkeywordideas.md), then keyword ideas will be returned for all devices.

## Syntax
```xml
<xs:complexType name="DeviceSearchParameter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:SearchParameter">
      <xs:sequence>
        <xs:element minOccurs="0" name="Device" nillable="true" type="tns:DeviceCriterion" />
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
Service: [AdInsightService.svc v13](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v13/AdInsightService.svc)  
Namespace: https\://bingads.microsoft.com/AdInsight/v13  

