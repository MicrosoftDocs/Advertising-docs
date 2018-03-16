---
title: CampaignPerformanceReportRequest Data Object - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a campaign performance report request.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# CampaignPerformanceReportRequest Data Object - Reporting
Defines a campaign performance report request. Use this report to view high-level performance statistics and quality attributes for each campaign or account. This is also a quick way to flag any major campaign or account problems.

You can request impressions, impression share (%), clicks, spend, and average cost per click for each campaign or account. Once downloaded, this data can be sorted by campaign, campaign status, and quality score.

To request a report of this type, pass this object to the [SubmitGenerateReport](submitgeneratereport.md) operation.

## Syntax
```xml
<xs:complexType name="CampaignPerformanceReportRequest" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:ReportRequest">
      <xs:sequence>
        <xs:element name="Aggregation" type="tns:ReportAggregation" />
        <xs:element name="Columns" nillable="true" type="tns:ArrayOfCampaignPerformanceReportColumn" />
        <xs:element minOccurs="0" name="Filter" nillable="true" type="tns:CampaignPerformanceReportFilter" />
        <xs:element name="Scope" nillable="true" type="tns:AccountThroughCampaignReportScope" />
        <xs:element name="Time" nillable="true" type="tns:ReportTime" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="aggregation"></a>Aggregation|The type of aggregation to use to aggregate the report data. For example, you can aggregate the report data by day or week, or request a summary report.<br /><br />The default is Summary.<br /><br />The *Time* element specifies the time period to use for the aggregation.|[ReportAggregation](reportaggregation.md)|
|<a name="columns"></a>Columns|The list of attributes and performance statistics to include in the report. The report will include the columns in the order that you specify them.|[CampaignPerformanceReportColumn](campaignperformancereportcolumn.md) array|
|<a name="filter"></a>Filter|The filter information to use to filter the report data.|[CampaignPerformanceReportFilter](campaignperformancereportfilter.md)|
|<a name="scope"></a>Scope|The scope of the report. Use this element to limit the report to include data for a combination of accounts and campaigns.|[AccountThroughCampaignReportScope](accountthroughcampaignreportscope.md)|
|<a name="time"></a>Time|The time period to use for the report. You can specify a custom date range or select a predefined date range, for example, Today or ThisWeek.<br /><br />For a list of the time periods that you can specify for each aggregation type, see [Aggregation and Time](../guides/reports.md#aggregation-time).<br/><br/>You can set the time zone within the [ReportTime](reporttime.md) object, which helps you accurately scope data for the requested time period.<br/><br/>If you do not choose a time zone, the Reporting service uses PacificTimeUSCanadaTijuana by default.|[ReportTime](reporttime.md)|

The [CampaignPerformanceReportRequest](campaignperformancereportrequest.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsreportrequest"></a>Inherited Elements from ReportRequest
The [CampaignPerformanceReportRequest](campaignperformancereportrequest.md) object derives from the [ReportRequest](reportrequest.md) object, and inherits the following elements. The descriptions below are specific to [CampaignPerformanceReportRequest](campaignperformancereportrequest.md), and might not apply to other objects that inherit the same elements from the [ReportRequest](reportrequest.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="excludecolumnheaders"></a>ExcludeColumnHeaders|Determines whether or not the downloaded report should contain header descriptions for each column. The report column header matches the requested column name e.g. *Impressions* and *Clicks*.<br/><br/>Set this property *true* if you want the report column headers excluded from the downloaded report. The default value is *false*.|**boolean**|
|<a name="excludereportfooter"></a>ExcludeReportFooter|Determines whether or not the downloaded report should contain footer metadata such as Microsoft copyright (*@2017 Microsoft Corporation. All rights reserved.*). <br/><br/>Set this property *true* if you want the report footer metadata excluded from the downloaded report. The default value is *false*.|**boolean**|
|<a name="excludereportheader"></a>ExcludeReportHeader|Determines whether or not the downloaded report should contain header metadata such as report name, date range, and aggregation.<br/><br/>Set this property *true* if you want the report header metadata excluded from the downloaded report. The default value is *false*.|**boolean**|
|<a name="format"></a>Format|The format of the report data. For example, you can request the data in comma-separated values (Csv) format or tab-separated values (Tsv) format.<br /><br />The default value is Csv.<br /><br /> All downloaded files are ZIP compressed.|[ReportFormat](reportformat.md)|
|<a name="language"></a>Language|The language to use to generate the report headers and columns.<br /><br />The default is English.|[ReportLanguage](reportlanguage.md)|
|<a name="reportname"></a>ReportName|The name of the report. The name is included in the report header. If you do not specify a report name, the system generates a name in the form, ReportType-ReportDateTime.<br /><br />The maximum length of the report name is 200.|**string**|
|<a name="returnonlycompletedata"></a>ReturnOnlyCompleteData|Determines whether you want the service to generate the report only if all the data has been processed and is available.<br /><br />If *True*, the request fails if the system has not finished processing all the data based on the aggregation, scope, and time period values that you specify. However, if *False*, the request succeeds but the report will contain only the data that the system has finished processing at the time of the request (there is no indication as to whether the data is complete). The default is *False*.<br /><br /> When a user clicks an ad, it can take from three to four hours for the system to process the click and make it available for reporting. For more information, see [Determining When the Books Close](../guides/reports.md#booksclose).<br /><br />Because you cannot retrieve complete data for today, you must set this element to *False* if the end date of the custom date range specified in the Time element of the derived report object is set to today, or if you specify one of the following predefined time values:<br />- *Today*<br />- *ThisWeek*<br />- *ThisMonth*<br />- *ThisYear*|**boolean**|

## Requirements
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v12/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v12  

