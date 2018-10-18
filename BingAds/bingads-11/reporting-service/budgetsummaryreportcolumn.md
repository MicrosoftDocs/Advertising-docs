---
title: BudgetSummaryReportColumn Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the attributes and performance statistics columns that you can include in the BudgetSummaryReportRequest.
---
# BudgetSummaryReportColumn Value Set - Reporting
Defines the attributes and performance statistics columns that you can include in the [BudgetSummaryReportRequest](budgetsummaryreportrequest.md).

The attribute columns that you include in a report can affect how the statistics are aggregated. In other words the number of rows increase by a factor of the unique attributes. For more information, see [Columns that Group the Data](../guides/reports.md#columnsdata).

For a list of columns that you must include, please see the [Required Columns](#requiredcolumns) section below.

To see how far back hourly, daily, weekly, monthly, yearly and summary aggregated data can be retrieved for a report, see [Report Data Retention Time Periods](../guides/report-data-retention-time-periods.md).

## Syntax
```xml
<xs:simpleType name="BudgetSummaryReportColumn" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="AccountName" />
    <xs:enumeration value="AccountNumber" />
    <xs:enumeration value="AccountId" />
    <xs:enumeration value="CampaignName" />
    <xs:enumeration value="CampaignId" />
    <xs:enumeration value="Date" />
    <xs:enumeration value="CurrencyCode" />
    <xs:enumeration value="MonthlyBudget" />
    <xs:enumeration value="DailySpend" />
    <xs:enumeration value="MonthToDateSpend" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="accountid"></a>AccountId|The Bing Ads assigned identifier of an account.|
|<a name="accountname"></a>AccountName|The account name.|
|<a name="accountnumber"></a>AccountNumber|The Bing Ads assigned number of an account.|
|<a name="campaignid"></a>CampaignId|The Bing Ads assigned identifier of a campaign.|
|<a name="campaignname"></a>CampaignName|The campaign name.|
|<a name="currencycode"></a>CurrencyCode|The account currency type. For possible values, see [Currencies](../guides/currencies.md).|
|<a name="dailyspend"></a>DailySpend|The average amount of campaign budget spent per day.|
|<a name="date"></a>Date|The date for the downloaded report records. The date will be in the time zone of the campaign|
|<a name="monthlybudget"></a>MonthlyBudget|The average amount of campaign budget spent during a calendar month.|
|<a name="monthtodatespend"></a>MonthToDateSpend|The amount of money spent to date for the month.|

## <a name="remarks"></a>Remarks
### <a name="requiredcolumns"></a>Required Columns
The report must include the following columns, and one or more of the performance statistics columns. For more information, see [Report Attributes and Performance Statistics](../guides/report-attributes-performance-statistics.md).

|Column|
|----------|
|AccountName|
|AccountNumber|
|CampaignName|
|CurrencyCode|
|Date|

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v11  

## Used By
[BudgetSummaryReportRequest](budgetsummaryreportrequest.md)  
