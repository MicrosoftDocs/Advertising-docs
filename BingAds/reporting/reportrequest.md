---
title: ReportRequest Data Object
ms.service: bing-ads-reporting
ms.topic: article
author: eric-urban
ms.author: eur
---
# ReportRequest Data Object
Defines the base object for all report requests.

Do not instantiate this object. Instead, you may instantiate one of the report request objects which derives from this object, for example the [CampaignPerformanceReportRequest](../reporting/campaignperformancereportrequest.md). For a list of reports, see the [Report Types](~/guides/report-types.md) guide.

## Syntax
```xml
<xs:complexType name="ReportRequest" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="ExcludeColumnHeaders" nillable="true" type="xs:boolean" />
    <xs:element minOccurs="0" name="ExcludeReportFooter" nillable="true" type="xs:boolean" />
    <xs:element minOccurs="0" name="ExcludeReportHeader" nillable="true" type="xs:boolean" />
    <xs:element minOccurs="0" name="Format" nillable="true" type="tns:ReportFormat" />
    <xs:element minOccurs="0" name="Language" nillable="true" type="tns:ReportLanguage" />
    <xs:element minOccurs="0" name="ReportName" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="ReturnOnlyCompleteData" nillable="true" type="xs:boolean" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="excludecolumnheaders"></a>ExcludeColumnHeaders|Determines whether or not the downloaded report should contain header descriptions for each column. The report column header matches the requested column name e.g. *Impressions* and *Clicks*.<br/><br/>Set this property *true* if you want the report column headers excluded from the downloaded report. The default value is *false*.|**boolean**|
|<a name="excludereportfooter"></a>ExcludeReportFooter|Determines whether or not the downloaded report should contain footer metadata such as Microsoft copyright (*?2017 Microsoft Corporation. All rights reserved.*). <br/><br/>Set this property *true* if you want the report footer metadata excluded from the downloaded report. The default value is *false*.|**boolean**|
|<a name="excludereportheader"></a>ExcludeReportHeader|Determines whether or not the downloaded report should contain header metadata such as report name, date range, and aggregation.<br/><br/>Set this property *true* if you want the report header metadata excluded from the downloaded report. The default value is *false*.|**boolean**|
|<a name="format"></a>Format|The format of the report data. For example, you can request the data in comma-separated values (Csv) format or tab-separated values (Tsv) format.<br /><br />The default value is Csv.<br /><br />**Note**: All downloaded files are ZIP compressed.|[ReportFormat](reportformat.md)|
|<a name="language"></a>Language|The language to use to generate the report headers and columns.<br /><br />The default is English.|[ReportLanguage](reportlanguage.md)|
|<a name="reportname"></a>ReportName|The name of the report. The name is included in the report header. If you do not specify a report name, the system generates a name in the form, ReportType-ReportDateTime.<br /><br />The maximum length of the report name is 200.|**string**|
|<a name="returnonlycompletedata"></a>ReturnOnlyCompleteData|Determines whether you want the service to generate the report only if all the data has been processed and is available.<br /><br />If *True*, the request fails if the system has not finished processing all the data based on the aggregation, scope, and time period values that you specify. However, if *False*, the request succeeds but the report will contain only the data that the system has finished processing at the time of the request (there is no indication as to whether the data is complete). The default is *False*.<br /><br />**Note**: When a user clicks an ad, it can take from three to four hours for the system to process the click and make it available for reporting. For more information, see [Determining When the Books Close](~/guides/reports.md#booksclose).<br /><br />Because you cannot retrieve complete data for today, you must set this element to *False* if the end date of the custom date range specified in the Time element of the derived report object is set to today, or if you specify one of the following predefined time values:<br />- *Today*<br />- *ThisWeek*<br />- *ThisMonth*<br />- *ThisYear*|**boolean**|

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https://bingads.microsoft.com/Reporting/v11  

## Used By
[SubmitGenerateReport](submitgeneratereport.md)  
