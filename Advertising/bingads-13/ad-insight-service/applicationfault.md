---
title: ApplicationFault Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the base object from which all fault detail objects derive.
---
# ApplicationFault Data Object - Ad Insight
Defines the base object from which all fault detail objects derive.

## Syntax
```xml
<xs:complexType name="ApplicationFault" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="TrackingId" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="trackingid"></a>TrackingId|The identifier of the log entry that contains the details of the API call.|**string**|

## Requirements
Service: [AdInsightService.svc v13](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v13/AdInsightService.svc)  
Namespace: https\://adapi.microsoft.com  

