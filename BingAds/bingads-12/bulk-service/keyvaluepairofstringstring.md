---
title: KeyValuePairOfstringstring Data Object - Bulk
ms.service: bing-ads-bulk-service
ms.topic: article
author: eric-urban
ms.author: eur
description: The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.
---
# KeyValuePairOfstringstring Data Object - Bulk
The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.

## Syntax
```xml
<xs:complexType name="KeyValuePairOfstringstring" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:annotation>
    <xs:appinfo>
      <GenericType Name="KeyValuePairOf{0}{1}{#}" Namespace="http://schemas.datacontract.org/2004/07/System.Collections.Generic" xmlns="http://schemas.microsoft.com/2003/10/Serialization/">
        <GenericParameter Name="string" Namespace="http://www.w3.org/2001/XMLSchema" />
        <GenericParameter Name="string" Namespace="http://www.w3.org/2001/XMLSchema" />
      </GenericType>
      <IsValueType xmlns="http://schemas.microsoft.com/2003/10/Serialization/">true</IsValueType>
    </xs:appinfo>
  </xs:annotation>
  <xs:sequence>
    <xs:element name="key" nillable="true" type="xs:string" />
    <xs:element name="value" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="key"></a>key|The name of the setting.|**string**|
|<a name="value"></a>value|The value of the setting.|**string**|

## Requirements
Service: [BulkService.svc v11](https://bulk.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/BulkService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/System.Collections.Generic  

## Used By
[BatchError](batcherror.md)  
[GetBulkDownloadStatus](getbulkdownloadstatus.md)  
[GetBulkUploadStatus](getbulkuploadstatus.md)  
