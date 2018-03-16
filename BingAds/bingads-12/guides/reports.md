---
title: "Reports"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Track finances and measure ad performance to optimize your budget or campaign settings.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# Reports
The Reporting service contains the operations that you use to submit report requests and poll for their status. The reports provide detailed statistics about Bing Ads accounts, campaigns, and ad groups. The information can help you track finances, measure ad performance, and adjust settings to optimize your budget or campaign. For example, you can use the keyword performance report to see which keywords are performing well and those that are not.

## Reporting Service Overview
When submitting a report request, you choose the [Report Attributes and Performance Statistics](report-attributes-performance-statistics.md) to determine the contents of the report. For example, you may want to include impressions, clicks, and click-through rate. The report uses the column names as the column headers. The report includes the columns in the same order that you include them in the *Columns* element of the report request. For information about how columns affect data output, see [Columns that Group the Data](#columnsdata) below. For information about restrictions on column combinations in the same report request, see [Column Restrictions](#columnrestrictions) below.

You will also specify the report parameters that restrict or limit the returned data set. For example, you can set the aggregation level to group the data by day or month; specify the time period of the data to include in the report by using specific dates or predefined date ranges, such as today or the last seven days; specify the scope of the data by identifying the accounts, campaigns, and ad groups to include in the report; and set filter criteria to filter the report data. For information about time periods that you can specify for each aggregation value, see [Aggregation and Time](#aggregation-time) below.

For a list of reports that you can request, see [Report Types](report-types.md). For a complete list of report parameters that you can set, see each report request object and the [ReportRequest](../reporting-service/reportrequest.md) base object.

For information about how to request and download a report, see [Request and Download a Report](request-download-report.md)When the report completes successfully, you can download the report from the URL that the service returns. The report file is compressed, so you must unzip the file to read the report. There is no limit to the number of reports that the system can store; however, the length of time that the reports are stored is undefined. The service does not check for duplicate report requests.

For information about how the campaign's time zone affects the time period that you specify, see [Time Zones in Reporting](#reptimezones) below.

For information about when the books are closed for reporting, see [Determining When the Books Close](#booksclose) below.

## <a name="reportschema"></a>Report File Schema

```csv
"Report Name: My Keyword Performance Report"
"Report Time: 7/7/2017"
"Time Zone: (GMT-08:00) Pacific Time (US & Canada); Tijuana"
"Last Completed Available Day: 7/8/2017 10:15:00 PM (GMT)"
"Last Completed Available Hour: 7/8/2017 10:15:00 PM (GMT)"
"Report Aggregation: Summary"
"Report Filter: "
"Potential Incomplete Data: true"
"Rows: 5"

"AccountId","CampaignId","Keyword","KeywordId","DeviceType","Clicks"
"YourAccountId","YourCampaignId","red shoes","123","Computer","35"
"YourAccountId","YourCampaignId","red shoes","123","Smartphone","50"
"YourAccountId","YourCampaignId","shoes delivered","234","Computer","1"
"YourAccountId","YourCampaignId","shoe sale","345","Computer","80"
"YourAccountId","YourCampaignId","shoe sale","345","Smartphone","5"

"@2017 Microsoft Corporation. All rights reserved. "
```

## <a name="columnsdata"></a>Columns that Group the Data
The attribute columns that you include in a report affects the values within the statistics columns as well as the number or rows. For example, if you request a summary report that includes only *AccountId*, *CampaignId*, *Keyword*, *KeywordId*, and *Clicks*, the clicks column will contain the number of clicks for the keyword regardless of other attributes such as device, match type, and network. 

```csv
"Report Name: My Keyword Performance Report"
"Report Time: 7/7/2017"
"Time Zone: (GMT-08:00) Pacific Time (US & Canada); Tijuana"
"Last Completed Available Day: 7/8/2017 2:55:00 PM (GMT)"
"Last Completed Available Hour: 7/8/2017 2:55:00 PM (GMT)"
"Report Aggregation: Summary"
"Report Filter: "
"Potential Incomplete Data: true"
"Rows: 3"

"AccountId","CampaignId","Keyword","KeywordId","Clicks"
"YourAccountId","YourCampaignId","red shoes","123","95"
"YourAccountId","YourCampaignId","shoes delivered","234","1"
"YourAccountId","YourCampaignId","shoe sale","345","98"

"@2017 Microsoft Corporation. All rights reserved. "
```


If you then include the *DeviceType* column, the report will contain a row for each unique combination of keyword and device type values, and the value in the clicks column for each row is broken down accordingly. 

```csv
"Report Name: My Keyword Performance Report"
"Report Time: 7/7/2017"
"Time Zone: (GMT-08:00) Pacific Time (US & Canada); Tijuana"
"Last Completed Available Day: 7/8/2017 2:55:00 PM (GMT)"
"Last Completed Available Hour: 7/8/2017 2:55:00 PM (GMT)"
"Report Aggregation: Summary"
"Report Filter: "
"Potential Incomplete Data: true"
"Rows: 7"

"AccountId","CampaignId","Keyword","KeywordId","DeviceType","Clicks"
"YourAccountId","YourCampaignId","red shoes","123","Computer","35"
"YourAccountId","YourCampaignId","red shoes","123","Smartphone","50"
"YourAccountId","YourCampaignId","red shoes","123","Tablet","10"
"YourAccountId","YourCampaignId","shoes delivered","234","Computer","1"
"YourAccountId","YourCampaignId","shoe sale","345","Computer","80"
"YourAccountId","YourCampaignId","shoe sale","345","Smartphone","5"
"YourAccountId","YourCampaignId","shoe sale","345","Tablet","13"

"@2017 Microsoft Corporation. All rights reserved. "
```

For more information about each type of available columns, see [Report Attributes and Performance Statistics](report-attributes-performance-statistics.md).

The *TimePeriod* attribute is required for most reports, so you should also consider that specifying a more granular aggregation period, for example monthly in the report request's *Aggregation* element, would further break down the click data by month. For example, the report would then contain a row for each unique combination of keyword, device, and month. The row is included only for months that contain clicks.

## <a name="columnrestrictions"></a>Column Restrictions
For reports that include impression share performance statistics columns you cannot include constrained attributes in the same report request. If you include any of the impression share performance statistics columns, then you must exclude all of the below attribute columns. Likewise, if you include any of the below attribute columns, then you must exclude all of the impression share performance statistics columns.

The following attribute and impression share performance statistics columns are mutually exclusive when submitting the [AccountPerformanceReportRequest](../reporting-service/accountperformancereportrequest.md) and [AdGroupPerformanceReportRequest](../reporting-service/adgroupperformancereportrequest.md).

|Attributes|Impression Share Performance Statistics|
|--------------|-------------------------------------------|
|BidMatchType<br /><br />DeviceOS<br /><br />TopVsOther|ExactMatchImpressionSharePercent<br /><br />ImpressionLostToAdRelevancePercent<br /><br />ImpressionLostToBidPercent<br /><br />ImpressionLostToBudgetPercent<br /><br />ImpressionLostToExpectedCtrPercent<br /><br />ImpressionLostToRankPercent<br /><br />ImpressionSharePercent|

The following attribute and impression share performance statistics columns are mutually exclusive when submitting the [CampaignPerformanceReportRequest](../reporting-service/campaignperformancereportrequest.md).

|Attributes|Impression Share Performance Statistics|
|--------------|-------------------------------------------|
|BidMatchType<br /><br />BudgetAssociationStatus<br /><br />BudgetName<br /><br />BudgetStatus<br /><br />DeviceOS<br /><br />TopVsOther|ExactMatchImpressionSharePercent<br /><br />ImpressionLostToAdRelevancePercent<br /><br />ImpressionLostToBidPercent<br /><br />ImpressionLostToBudgetPercent<br /><br />ImpressionLostToExpectedCtrPercent<br /><br />ImpressionLostToRankPercent<br /><br />ImpressionSharePercent|

The following attribute and impression share performance statistics columns are mutually exclusive when submitting the [ProductDimensionPerformanceReportRequest](../reporting-service/productdimensionperformancereportrequest.md).

|Attributes|Impression Share Performance Statistics|
|--------------|-------------------------------------------|
|AdDistribution<br /><br />AdId<br /><br />AdStatus<br /><br />ClickType<br /><br />Language<br /><br />LocalStoreCode<br /><br />Network<br /><br />TopVsOther|BenchmarkBid<br /><br />BenchmarkCtr<br /><br />ImpressionLostToBudgetPercent<br /><br />ImpressionLostToRankPercent<br /><br />ImpressionSharePercent|
	
The following attribute and impression share performance statistics columns are mutually exclusive when submitting the [ProductPartitionPerformanceReportRequest](../reporting-service/productpartitionperformancereportrequest.md).

|Attributes|Impression Share Performance Statistics|
|--------------|-------------------------------------------|
|AdDistribution<br /><br />AdId<br /><br />AdStatus<br /><br />BidMatchType<br /><br />ClickType<br /><br />DeliveredMatchType<br /><br />Language<br /><br />LocalStoreCode<br /><br />Network<br /><br />TopVsOther|BenchmarkBid<br /><br />BenchmarkCtr<br /><br />ImpressionLostToBudgetPercent<br /><br />ImpressionLostToRankPercent<br /><br />ImpressionSharePercent|

## <a name="timeperiod"></a>TimePeriod Column
If you include the *TimePeriod* column, then the format of the values in the downloaded report will vary depending on the aggregation level that you specify in the report request. For example, if the aggregation level is Daily, each field in TimePeriod column will contain the day formatted as *yyyy-mm-dd*.

|Aggregation|Description|
|---------------|---------------|
|Daily|Each row of the report identifies the month, day, and year when the transaction occurred. The report data will be aggregated by each day. The time period will be formatted as *yyyy-mm-dd*.|
|DayOfWeek|Each row of the report identifies the day of the week when the transaction occurred. The report data will be aggregated by each of the seven days in a week. The possible data values are *1* - *7* where *1* represents Sunday and *7* represents Saturday. If the report time spans multiple weeks, then the performance data across all weeks for a given day of the week will be aggregated in one row. For example if *Campaign A* has 5 impressions every Monday (day 2) throughout each of the 3 weeks included in the report time range, then the report will include one row with a *2* in the TimePeriod column and the impressions in that row totaling 15.|
|Hourly|Each row of the report identifies the hour when the transaction occurred. The report data will be aggregated by each hour of the day.<br/><br/>The time period will be formatted with the date and hour (int value) delimited by a semicolon e.g., *yyyy-mm-dd;hour*. The possible values for the hour component are *0* - *23*. If the report time spans multiple days, then the performance data for a given hour will be provided separately across multiple rows i.e. the report will include one row for each unique day and hour. For example if *Campaign A* has 5 impressions during *Hour* 7 on each of the 3 days included in the report time range, then the report will include three rows each with 5 impressions for *Hour* 7.|
|HourOfDay|Each row of the report identifies the hour of the day when the transaction occurred. The report data will be aggregated by each of the 24 hours across all days. The possible values are *0* - *23*. If the report time spans multiple days, then the performance data across all days for a given hour will be aggregated in one row. For example if *Campaign A* has 5 impressions during hour *7* on each of the 3 days included in the report time range, then the report will include one row with impressions for *HourOfDay* totaling 15.|
|Monthly|Each row of the report identifies the month when the transaction occurred. The report data will be aggregated by each month. The time period that contains the first day of the month will be formatted as *yyyy-mm-dd*.|
|Weekly|Each row of the report identifies the week when the transaction occurred. The report data will be aggregated by each week. The time period that contains the date of the Sunday for each week will be formatted as *yyyy-mm-dd*.|
|Yearly|Each row of the report identifies the year when the transaction occurred. The report data will be aggregated by each year. The time period that contains the year will be formatted as *yyyy*.|

## <a name="aggregation-time"></a>Aggregation and Time
For most report requests you must set the *Aggregation* and *Time* elements. The following are the time periods that you can specify for each aggregation value.

|Aggregation Value|Time Periods|
|---------------------|----------------|
|Daily|Today<br /><br />Yesterday<br /><br />LastSevenDays<br /><br />ThisMonth<br /><br />LastMonth<br /><br />Custom date range|
|DayOfWeek|Today<br /><br />Yesterday<br /><br />LastSevenDays<br /><br />ThisMonth<br /><br />LastMonth<br /><br />LastThreeMonths<br /><br />LastSixMonths|
|Hourly|Today<br /><br />Yesterday<br /><br />Custom date range|
|HourOfDay|Today<br /><br />Yesterday<br /><br />LastSevenDays<br /><br />ThisMonth<br /><br />LastMonth<br /><br />LastThreeMonths<br /><br />LastSixMonths|
|Monthly|ThisMonth<br /><br />LastMonth<br /><br />LastThreeMonths<br /><br />LastSixMonths<br /><br />ThisYear<br /><br />LastYear<br /><br />Custom date range|
|Summary|Today<br /><br />Yesterday<br /><br />LastSevenDays<br /><br />ThisMonth<br /><br />LastMonth<br /><br />Custom date range|
|Weekly|ThisWeek<br /><br />LastWeek<br /><br />LastFourWeeks<br /><br />ThisMonth<br /><br />LastMonth<br /><br />ThisYear<br /><br />LastYear<br /><br />Custom date range|
|Yearly|ThisYear<br /><br />LastYear<br /><br />Custom date range|

## <a name="zeroimpressions"></a>Zero Impressions
The report data can include rows with zero impressions if the impression occurred before the requested time period and then a subsequent action such as click, conversion, or phone call occurs during the requested time period. Likewise even within the requested time period if you download a daily report for performance last week, it is possible that all of the impressions occurred on Sunday and then clicks or other performance occurred e.g. Monday or Tuesday. The report data for Monday or Tuesday might have clicks with zero impressions. You can use the [Bulk Service](../bulk-service/bulk-service-reference.md) or [Campaign Management Service](../campaign-management-service/campaign-management-service-reference.md) to get all entities in your account, regardless of whether or not they have any associated performance data.

## <a name="reptimezones"></a>Time Zones in Reporting
When you create a report request, specify the date range time period based on the time zone of the campaign. The report data is stored in the time zone of the campaign (taking into account daylight saving time for those time zones that support daylight saving time). For example, if the time zone of the campaign is Pacific Time and a click occurs at noon Eastern Time, the time of the click is recorded as 9:00 AM. If you request a report for the campaign using hourly aggregation, the report data will include a click that occurred at 9:00 AM (the report data is not adjusted based on the local time zone of the user). 

If your report request specifies multiple campaigns in different time zones, the timezone picked is the time zone that is closest to PDT as you are facing towards the west. Likewise, if the report request spans multiple accounts (for example, an account performance report), the data is reported using the westernmost timezone relative to PDT. 

## <a name="booksclose"></a>Determining When the Books Close
When a user clicks an ad, it can take up to two hours for the system to process the click (3 hours for conversions) and make it available for reporting. When all data for the previous day have been processed and made available for reporting, this state is referred to as *Books Closed*. If you schedule a report that requires the previous full day of data, you should consider the two-to-three hour rolling window and the time zone of the campaign before making your request. For example, if the time zone of the campaign is set to Pacific Time (UTC-08:00), consider running the report at 4:00 AM Pacific Time (three hours for the rolling window plus a one-hour buffer). For time zone related details, see [Time Zones in Reporting](#reptimezones) above.

> [!NOTE]
> Data is generally considered complete with books closed after 3 hours. In some exception cases due to invalid traffic, there could be unexpected adjustments that might take a week or more to resolve.
> 
> For example, if an advertiser complaint identifies invalid click activity that escaped the automated filtration system, the Traffic Quality and support teams will process a credit to the advertiser's account, and will partner with internal teams to determine whether they can update automated systems in order to improve detection in the future. For more information, please see [Traffic Quality Center](https://advertise.bingads.microsoft.com/en-us/resources/policies/traffic-quality).

If you request a report that includes campaigns that span multiple time zones, the data is considered complete only after all of the click data is processed for the campaign that has the time zone that is closest to PDT as you are facing towards the west. For example, say you request a report that includes Campaign A (which specifies the PST time zone), and Campaign B (which specifies the EST time zone), the data is not complete until all of the click data for Campaign A has processed for the specified time period.

Each report request includes the *ReturnOnlyCompleteData* element that you can set to specify whether you want the service to generate the report only if all the data has been processed and is available based on the aggregation, scope, and time period values that you specify. If **true**, the request fails if the system has not finished processing all the data based on your criteria. However, if **false**, the request succeeds but the report will contain only the data that the system has finished processing at the time of the request, and there is no indication as to whether the data is complete. The default value is **false**.

## See Also
[Report Attributes and Performance Statistics](report-attributes-performance-statistics.md)  
[Report Types](report-types.md)  
[Request and Download a Report](request-download-report.md)  
[Bing Ads Web Service Addresses](web-service-addresses.md)  

