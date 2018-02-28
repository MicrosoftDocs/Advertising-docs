---
title: ReportRequestStatusType Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the status of a report.
---
# ReportRequestStatusType Value Set - Reporting

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

Defines the status of a report.

## Syntax
```xml
<xs:simpleType name="ReportRequestStatusType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Error" />
    <xs:enumeration value="Success" />
    <xs:enumeration value="Pending" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="error"></a>Error|An error occurred while generating the report. You will need to submit your report request again. If the request continues to fail, consider getting the tracking identifier from the response message and contacting support.|
|<a name="pending"></a>Pending|The report is not yet complete.|
|<a name="success"></a>Success|The report was successfully completed.<br /><br />The report can be downloaded from the URL contained in the *ReportDownloadUrl* element of the [ReportRequestStatus](../reporting-service/reportrequeststatus.md) object.|

## Requirements
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v12  

## Used By
[ReportRequestStatus](reportrequeststatus.md)  
