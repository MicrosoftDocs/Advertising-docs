---
title: ResponseMode Value Set - Bulk
ms.service: bing-ads-bulk-service
ms.topic: "article"
ms.date: 11/01/2017
author: eric-urban
ms.author: eur
description: Defines elements to specify whether the bulk service should return upload errors with their corresponding data.
---
# ResponseMode Value Set - Bulk
Defines elements to specify whether the bulk service should return upload errors with their corresponding data.

## Syntax
```xml
<xs:simpleType name="ResponseMode" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="ErrorsOnly" />
    <xs:enumeration value="ErrorsAndResults" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="errorsandresults"></a>ErrorsAndResults|Return errors and results in the bulk upload response file.|
|<a name="errorsonly"></a>ErrorsOnly|Return errors only in the bulk upload response file.|

## Requirements
Service: [BulkService.svc v11](https://bulk.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/BulkService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[GetBulkUploadUrl](getbulkuploadurl.md)  
