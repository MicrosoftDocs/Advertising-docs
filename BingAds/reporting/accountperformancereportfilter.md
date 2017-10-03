---
title: AccountPerformanceReportFilter Data Object
ms.service: bing-ads-reporting
ms.topic: article
author: eric-urban
ms.author: eur
---
# AccountPerformanceReportFilter Data Object
Defines the criteria to use to filter the account performance report data.

## Syntax
```xml
<xs:complexType name="AccountPerformanceReportFilter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AccountStatus" nillable="true" type="tns:AccountStatusReportFilter" />
    <xs:element minOccurs="0" name="AdDistribution" nillable="true" type="tns:AdDistributionReportFilter" />
    <xs:element minOccurs="0" name="DeviceOS" nillable="true" type="tns:DeviceOSReportFilter" />
    <xs:element minOccurs="0" name="DeviceType" nillable="true" type="tns:DeviceTypeReportFilter" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountstatus"></a>AccountStatus|The report will include data for only the account status. For example, you can use the filter to include data for only active accounts.<br /><br />You can specify one or more account statuses.|[AccountStatusReportFilter](accountstatusreportfilter.md)|
|<a name="addistribution"></a>AdDistribution|The report will include data for only the specified distribution medium. For example, you can use the filter to include data for only search ads.<br /><br />You can specify one or more distribution mediums.|[AdDistributionReportFilter](addistributionreportfilter.md)|
|<a name="deviceos"></a>DeviceOS|The report will include data where the ad is displayed on the specified device operating systems. For example, you may use the filter to include data for only ads displayed on Windows devices.|[DeviceOSReportFilter](deviceosreportfilter.md)|
|<a name="devicetype"></a>DeviceType|The report will include data where the ad is displayed on the specified device types. For example, you may use the filter to include data for only ads displayed on smartphones.<br /><br />You may specify one or more device types.|[DeviceTypeReportFilter](devicetypereportfilter.md)|

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https://bingads.microsoft.com/Reporting/v11  

## Used By
[AccountPerformanceReportRequest](accountperformancereportrequest.md)  
