---
title: GeographicPerformanceReportRequest Data Object - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a geographic performance report request.
---
# GeographicPerformanceReportRequest Data Object - Reporting
Defines a geographic performance report request. Use this report to see where your traffic is coming from: the physical location of the people searching for your ad or the locations people are searching for. You can then validate whether your location targeting strategy is successful and identify opportunities to improve.

You can request impressions, clicks, spend, and average cost-per-click for each ad group, organized into columns that show the location used to serve ads.

To request a report of this type, pass this object to the [SubmitGenerateReport](submitgeneratereport.md) operation.

## Syntax
```xml
<xs:complexType name="GeographicPerformanceReportRequest" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:ReportRequest">
      <xs:sequence>
        <xs:element name="Aggregation" type="tns:ReportAggregation" />
        <xs:element name="Columns" nillable="true" type="tns:ArrayOfGeographicPerformanceReportColumn" />
        <xs:element minOccurs="0" name="Filter" nillable="true" type="tns:GeographicPerformanceReportFilter" />
        <xs:element name="Scope" nillable="true" type="tns:AccountThroughAdGroupReportScope" />
        <xs:element name="Time" nillable="true" type="tns:ReportTime" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="aggregation"></a>Aggregation|The type of aggregation to use to aggregate the report data. For example, you can aggregate the report data by day or week, or request a summary report.<br/><br/>The default is Summary.<br/><br/>The *Time* element specifies the time period to use for the aggregation.|[ReportAggregation](reportaggregation.md)|
|<a name="columns"></a>Columns|The list of attributes and performance statistics to include in the report. The report will include the columns in the order that you specify them.|[GeographicPerformanceReportColumn](geographicperformancereportcolumn.md) array|
|<a name="filter"></a>Filter|The filter information to use to filter the report data.|[GeographicPerformanceReportFilter](geographicperformancereportfilter.md)|
|<a name="scope"></a>Scope|The entity scope of the report.<br/><br/>Use this element to limit the report data to specific accounts, ad groups, or campaigns.|[AccountThroughAdGroupReportScope](accountthroughadgroupreportscope.md)|
|<a name="time"></a>Time|The time period to use for the report. You can specify a custom date range or select a predefined date range, for example, Today or ThisWeek.<br/><br/>For a list of the time periods that you can specify for each aggregation type, see [Aggregation and Time](../guides/reports.md#aggregation-time).<br/><br/>You can set the time zone within the [ReportTime](reporttime.md) object, which helps you accurately scope data for the requested time period.<br/><br/>If you do not choose a time zone, the Reporting service uses PacificTimeUSCanadaTijuana by default.|[ReportTime](reporttime.md)|

The [GeographicPerformanceReportRequest](geographicperformancereportrequest.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsreportrequest"></a>Inherited Elements from ReportRequest
The [GeographicPerformanceReportRequest](geographicperformancereportrequest.md) object derives from the [ReportRequest](reportrequest.md) object, and inherits the following elements. The descriptions below are specific to [GeographicPerformanceReportRequest](geographicperformancereportrequest.md), and might not apply to other objects that inherit the same elements from the [ReportRequest](reportrequest.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="excludecolumnheaders"></a>ExcludeColumnHeaders|Determines whether or not the downloaded report should contain header descriptions for each column. The report column header matches the requested column name e.g. *Impressions* and *Clicks*.<br/><br/>Set this property *true* if you want the report column headers excluded from the downloaded report. The default value is *false*.|**boolean**|
|<a name="excludereportfooter"></a>ExcludeReportFooter|Determines whether or not the downloaded report should contain footer metadata such as Microsoft copyright (*@2018 Microsoft Corporation. All rights reserved.*). <br/><br/>Set this property *true* if you want the report footer metadata excluded from the downloaded report. The default value is *false*.|**boolean**|
|<a name="excludereportheader"></a>ExcludeReportHeader|Determines whether or not the downloaded report should contain header metadata such as report name, date range, and aggregation.<br/><br/>Set this property *true* if you want the report header metadata excluded from the downloaded report. The default value is *false*.|**boolean**|
|<a name="format"></a>Format|The format of the report data. For example, you can request the data in comma-separated values (Csv) format or tab-separated values (Tsv) format.<br/><br/>The default value is Csv.<br/><br/>All downloaded files are ZIP compressed.|[ReportFormat](reportformat.md)|
|<a name="reportname"></a>ReportName|The name of the report. The name is included in the report header. If you do not specify a report name, the system generates a name in the form, ReportType-ReportDateTime.<br/><br/>The maximum length of the report name is 200.|**string**|
|<a name="returnonlycompletedata"></a>ReturnOnlyCompleteData|Determines whether or not the service must ensure that all the data has been processed and is available.<br/><br/>If set to *true* and if the system has not finished processing all the data based on the requested [Aggregation](#aggregation), [Scope](#scope), and [Time](#time), the service returns error code NoCompleteDataAvaliable (2004). Otherwise by default the request can succeed, there is no indication as to whether the data is complete, and the report will contain only the data that the system has finished processing at the time of the request.<br/><br/>Please note that because today is still in progress and data is not complete, you cannot set this element to *true* if the [Time](#time) period (whether custom or predefined date) includes today's date. For more information, see [Time Zones in Reporting](../guides/reports.md#reptimezones).|**boolean**|

## Requirements
Service: [ReportingService.svc v13](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v13/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v13  

