---
title: "Reporting Data Retention Time Periods"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Reference the data retention time periods for Bing Ads performance data.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# Reporting Data Retention Time Periods
Reporting data is kept for specified periods of time. This topic provides the data retention time periods for Bing Ads performance data. Use this information to see how far back hourly, daily, weekly, monthly, yearly and summary aggregated data can be retrieved for a report.

> [!NOTE]
> Retention periods are not applicable for the [Negative Keyword Conflict Report](../reporting-service/negativekeywordconflictreportrequest.md). The report is generated based on the current keywords and negative keywords.
> 
> It is possible to request and retrieve data outside of the published retention period, however the data outside of the retention period should be considered invalid or incomplete.

Unless otherwise noted, the **Hourly**, **Daily**, **Weekly**, **Monthly**, **Yearly** and **Summary** values are in *months*. For example, the last 6 months of hourly Keyword report data is available.

If the data aggregation is not available for a given report, it will be noted as *Not Applicable* in the table below.

## <a name="performance"></a>Performance

|API Report Name|Bing Ads Web Application Report Name|Hourly|Daily|Weekly|Monthly|Yearly|Summary|
|-------------------|----------------------------------------|----------|---------|----------|-----------|----------|-----------|
|[Account Performance Report](../reporting-service/accountperformancereportrequest.md)|Account|6|36|36|36|36|36|
|[Ad Performance Report](../reporting-service/adperformancereportrequest.md)|Ad|6|36|36|36|36|36|
|[Ad Dynamic Text Performance Report](../reporting-service/addynamictextperformancereportrequest.md)|Ad Dynamic Text|6|36|36|36|36|36|
|[Ad Group Performance Report](../reporting-service/adgroupperformancereportrequest.md)|Ad Group|6|36|36|36|36|36|
|[Audience Performance Report](../reporting-service/audienceperformancereportrequest.md)|Audiences|6|36|36|36|36|36|
|[Campaign Performance Report](../reporting-service/campaignperformancereportrequest.md)|Campaign|6|36|36|36|36|36|
|[Destination Url Performance Report](../reporting-service/destinationurlperformancereportrequest.md)|Destination URL|6|36|36|36|36|36|
|[Keyword Performance Report](../reporting-service/keywordperformancereportrequest.md)|Keyword|6|36|36|36|36|36|
|[Publisher Usage Performance Report](../reporting-service/publisherusageperformancereportrequest.md)|Website URL (publisher)|2|36|36|36|36|36|
|[Search Query Performance Report](../reporting-service/searchqueryperformancereportrequest.md)|Search Term|1|36|36|36|36|36|
|[Share of Voice Report](../reporting-service/shareofvoicereportrequest.md)|Share of Voice|Not Applicable|6|6|6|6|6|

## <a name="adextensions"></a>Ad Extensions

|API Report Name|Bing Ads Web Application Report Name|Hourly|Daily|Weekly|Monthly|Yearly|Summary|
|-------------------|----------------------------------------|----------|---------|----------|-----------|----------|-----------|
|[Ad Extension By Ad Report](../reporting-service/adextensionbyadreportrequest.md)|Ad Extension by Ad|6|36|36|36|36|36|
|[Ad Extension Detail Report](../reporting-service/adextensiondetailreportrequest.md)|Ad Extension by Item|6|36|36|36|36|36|
|[Ad Extension By Keyword Report](../reporting-service/adextensionbykeywordreportrequest.md)|Ad Extension by Keyword|6|36|36|36|36|36|
|[Call Detail Report](../reporting-service/calldetailreportrequest.md)|Call Forwarding Detail|6|6|6|6|6|6|


## <a name="productads"></a>Product Ads

|API Report Name|Bing Ads Web Application Report Name|Hourly|Daily|Weekly|Monthly|Yearly|Summary|
|-------------------|----------------------------------------|----------|---------|----------|-----------|----------|-----------|
|[Product Dimension Performance Report](../reporting-service/productdimensionperformancereportrequest.md)|Product Dimension|6|36|36|36|36|36|
|[Product Partition Performance Report](../reporting-service/productpartitionperformancereportrequest.md)|Product Partition|6|36|36|36|36|36|
|[Product Partition Unit Performance Report](../reporting-service/productpartitionunitperformancereportrequest.md)|Product Partition Unit|6|36|36|36|36|36|
|[Product Search Query Performance Report](../reporting-service/searchqueryperformancereportrequest.md)|Product Search Term|1|36|36|36|36|36|


## <a name="dynamicsearchads"></a>Dynamic Search Ads

|API Report Name|Bing Ads Web Application Report Name|Hourly|Daily|Weekly|Monthly|Yearly|Summary|
|-------------------|----------------------------------------|----------|---------|----------|-----------|----------|-----------|
|[DSA Auto Target Performance Report](../reporting-service/dsaautotargetperformancereportrequest.md)|(Coming soon)|6|36|36|36|36|36|
|[DSA Category Performance Report](../reporting-service/dsacategoryperformancereportrequest.md)|(Coming soon)|6|36|36|36|36|36|
|[DSA Search Query Performance Report](../reporting-service/dsasearchqueryperformancereportrequest.md)|(Coming soon)|1|36|36|36|36|36|

## <a name="changehistory"></a>Change History

|API Report Name|Bing Ads Web Application Report Name|Hourly|Daily|Weekly|Monthly|Yearly|Summary|
|-------------------|----------------------------------------|----------|---------|----------|-----------|----------|-----------|
|[Search Campaign Change History Report](../reporting-service/searchcampaignchangehistoryreportrequest.md)|Campaign Change History|6|6|6|6|6|6|

## <a name="targeting"></a>Targeting

|API Report Name|Bing Ads Web Application Report Name|Hourly|Daily|Weekly|Monthly|Yearly|Summary|
|-------------------|----------------------------------------|----------|---------|----------|-----------|----------|-----------|
|[Age Gender Demographic Report](../reporting-service/agegenderdemographicreportrequest.md)|Age and Gender|6|36|36|36|36|36|
|[Geographic Performance Report](../reporting-service/geographicperformancereportrequest.md)|Geographic|14 **days**|36|36|36|36|36|
|[User Location Report](../reporting-service/userlocationperformancereportrequest.md)|User Location|14 **days**|36|36|36|36|36|

## <a name="analytics"></a>Campaign Analytics

|API Report Name|Bing Ads Web Application Report Name|Hourly|Daily|Weekly|Monthly|Yearly|Summary|
|-------------------|----------------------------------------|----------|---------|----------|-----------|----------|-----------|
|[Conversion Performance Report](../reporting-service/conversionperformancereportrequest.md)|Conversions|6|36|36|36|36|36|
|[Goals And Funnels Report](../reporting-service/goalsandfunnelsreportrequest.md)|Goals|1|36|36|36|36|36|
|Not applicable|Segments|1|36|36|36|36|36|


## <a name="budget"></a>Billing and Budget

|API Report Name|Bing Ads Web Application Report Name|Hourly|Daily|Weekly|Monthly|Yearly|Summary|
|-------------------|----------------------------------------|----------|---------|----------|-----------|----------|-----------|
|[Budget Summary Report](../reporting-service/budgetsummaryreportrequest.md)|Budget|Not Applicable|24|Not Applicable|Not Applicable|Not Applicable|Not Applicable|
|Not applicable|Billing Statement|Not Applicable|Not Applicable|Not Applicable|36|Not Applicable|Not Applicable|
