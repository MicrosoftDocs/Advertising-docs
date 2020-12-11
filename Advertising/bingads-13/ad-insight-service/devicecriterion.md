---
title: DeviceCriterion Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: The device criterion that you can include when requesting keyword ideas or traffic estimates.
---
# DeviceCriterion Data Object - Ad Insight
The device criterion that you can include when requesting keyword ideas or traffic estimates.

## Syntax
```xml
<xs:complexType name="DeviceCriterion" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Criterion">
      <xs:sequence>
        <xs:element minOccurs="0" name="DeviceName" nillable="true" type="xs:string" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [DeviceCriterion](devicecriterion.md) object has the following elements: [DeviceName](#devicename).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="devicename"></a>DeviceName|The device that you want to target.<br/><br/>Possible case-sensitive values are *All*, *Computers*, *Smartphones*, and *Tablets*.|**string**|

## Requirements
Service: [AdInsightService.svc v13](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v13/AdInsightService.svc)  
Namespace: https\://bingads.microsoft.com/AdInsight/v13  

## Used By
[DeviceSearchParameter](devicesearchparameter.md)  
