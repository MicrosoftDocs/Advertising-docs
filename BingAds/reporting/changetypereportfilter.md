---
title: ChangeTypeReportFilter Value Set
ms.service: bing-ads-reporting
ms.topic: article
author: eric-urban
ms.author: eur
---
# ChangeTypeReportFilter Value Set
Defines the types of changes to entities by which you can filter the report data. These values are also used as column values in the `HowChanged` column of the campaign change history report. For more information, see [SearchCampaignChangeHistoryReportColumn](../reporting/searchcampaignchangehistoryreportcolumn.md).

## Syntax
```xml
<xs:simpleType name="ChangeTypeReportFilter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="Added" />
        <xs:enumeration value="Deleted" />
        <xs:enumeration value="Changed" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="added"></a>Added|The report will include data for entities that have been added.|
|<a name="changed"></a>Changed|The report will include data for elements of entities whose values have been updated.|
|<a name="deleted"></a>Deleted|The report will include data for entities that have been deleted.|

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https://bingads.microsoft.com/Reporting/v11  

## Used By
[SearchCampaignChangeHistoryReportFilter](searchcampaignchangehistoryreportfilter.md)  
