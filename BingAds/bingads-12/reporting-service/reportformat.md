---
title: ReportFormat Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the file formats that you can use for a report.
---
# ReportFormat Value Set - Reporting

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

Defines the file formats that you can use for a report.

## Syntax
```xml
<xs:simpleType name="ReportFormat" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Csv" />
    <xs:enumeration value="Tsv" />
    <xs:enumeration value="Xml" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="csv"></a>Csv|The report format will be comma-separated values (.csv).|
|<a name="tsv"></a>Tsv|The report format will be tab-separated values (.tsv).|
|<a name="xml"></a>Xml|The report format will be XML (.xml).|

## Requirements
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v11  

## Used By
[ReportRequest](reportrequest.md)  
