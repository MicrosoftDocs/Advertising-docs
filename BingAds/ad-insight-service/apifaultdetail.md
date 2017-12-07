---
title: ApiFaultDetail Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a fault object that operations return when web service-specific errors occur, such as when the request message contains incomplete or invalid data.
---
# ApiFaultDetail Data Object - Ad Insight
Defines a fault object that operations return when web service-specific errors occur, such as when the request message contains incomplete or invalid data.

## Syntax
```xml
<xs:complexType name="ApiFaultDetail" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="q3:ApplicationFault" xmlns:q3="https://adapi.microsoft.com">
      <xs:sequence>
        <xs:element minOccurs="0" name="BatchErrors" nillable="true" type="q4:ArrayOfBatchError" xmlns:q4="https://bingads.microsoft.com/AdInsight/v11" />
        <xs:element minOccurs="0" name="OperationErrors" nillable="true" type="q5:ArrayOfOperationError" xmlns:q5="https://bingads.microsoft.com/AdInsight/v11" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="batcherrors"></a>BatchErrors|An array of batch errors that identifies the items in the batch of items in the request message that caused the operation to fail. Each object contains the details that explain why the item caused the failure.|[BatchError](batcherror.md) array|
|<a name="operationerrors"></a>OperationErrors|An array of operation errors that contains the reasons that explain why the service operation failed when the error is not related to a specific item in the batch of items.|[OperationError](operationerror.md) array|

The [ApiFaultDetail](apifaultdetail.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsapplicationfault"></a>Inherited Elements from ApplicationFault
The [ApiFaultDetail](apifaultdetail.md) object derives from the [ApplicationFault](applicationfault.md) object, and inherits the following elements. The descriptions below are specific to [ApiFaultDetail](apifaultdetail.md), and might not apply to other objects that inherit the same elements from the [ApplicationFault](applicationfault.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="trackingid"></a>TrackingId|The identifier of the log entry that contains the details of the API call.|**string**|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: ```Microsoft.Advertiser.AdInsight.Api.Service.V11```  

