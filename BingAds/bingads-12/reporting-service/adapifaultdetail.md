---
title: AdApiFaultDetail Data Object - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a fault object that operations return when generic errors occur, such as an authentication error.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# AdApiFaultDetail Data Object - Reporting
Defines a fault object that operations return when generic errors occur, such as an authentication error.

## Syntax
```xml
<xs:complexType name="AdApiFaultDetail" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:ApplicationFault">
      <xs:sequence>
        <xs:element minOccurs="0" name="Errors" nillable="true" type="tns:ArrayOfAdApiError" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="errors"></a>Errors|An array of [AdApiError](adapierror.md) objects that contains the details that explain why the service operation failed.|[AdApiError](adapierror.md) array|

The [AdApiFaultDetail](adapifaultdetail.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsapplicationfault"></a>Inherited Elements from ApplicationFault
The [AdApiFaultDetail](adapifaultdetail.md) object derives from the [ApplicationFault](applicationfault.md) object, and inherits the following elements. The descriptions below are specific to [AdApiFaultDetail](adapifaultdetail.md), and might not apply to other objects that inherit the same elements from the [ApplicationFault](applicationfault.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="trackingid"></a>TrackingId|The identifier of the log entry that contains the details of the API call.|**string**|

## Requirements
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v12/ReportingService.svc)  
Namespace: https\://adapi.microsoft.com  

