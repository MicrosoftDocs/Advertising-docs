---
title: AgeGenderDemographicReportColumn Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the attributes and performance statistics columns that you can include in the AgeGenderDemographicReportRequest.
---
# AgeGenderDemographicReportColumn Value Set - Reporting
Defines the attributes and performance statistics columns that you can include in the [AgeGenderDemographicReportRequest](../reporting-service/agegenderdemographicreportrequest.md).

The attribute columns that you include in a report can affect how the statistics are aggregated. In other words the number of rows increase by a factor of the unique attributes. For more information, see [Columns that Group the Data](~/guides/reports.md#columnsdata).

For a list of columns that you must include, please see the [Required Columns](#requiredcolumns) section below.

To see how far back hourly, daily, weekly, monthly, yearly and summary aggregated data can be retrieved for a report, see [Report Data Retention Time Periods](~/guides/report-data-retention-time-periods.md).

## Syntax
```xml
<xs:simpleType name="AgeGenderDemographicReportColumn" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="AccountName" />
    <xs:enumeration value="AccountNumber" />
    <xs:enumeration value="AccountId" />
    <xs:enumeration value="TimePeriod" />
    <xs:enumeration value="CampaignName" />
    <xs:enumeration value="CampaignId" />
    <xs:enumeration value="AdGroupName" />
    <xs:enumeration value="AdGroupId" />
    <xs:enumeration value="AdDistribution" />
    <xs:enumeration value="AgeGroup" />
    <xs:enumeration value="Gender" />
    <xs:enumeration value="EstimatedImpressionPercent" />
    <xs:enumeration value="EstimatedClickPercent" />
    <xs:enumeration value="EstimatedCtr" />
    <xs:enumeration value="Language" />
    <xs:enumeration value="EstimatedImpressions" />
    <xs:enumeration value="EstimatedClicks" />
    <xs:enumeration value="EstimatedConversions" />
    <xs:enumeration value="EstimatedConversionRate" />
    <xs:enumeration value="AccountStatus" />
    <xs:enumeration value="CampaignStatus" />
    <xs:enumeration value="AdGroupStatus" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="accountid"></a>AccountId|The Bing Ads assigned identifier of an account.|
|<a name="accountname"></a>AccountName|The account name.|
|<a name="accountnumber"></a>AccountNumber|The Bing Ads assigned number of an account.|
|<a name="accountstatus"></a>AccountStatus|The account status.|
|<a name="addistribution"></a>AdDistribution|The ad distribution attribute of an ad group.|
|<a name="adgroupid"></a>AdGroupId|The Bing Ads assigned identifier of an ad group.|
|<a name="adgroupname"></a>AdGroupName|The ad group name.|
|<a name="adgroupstatus"></a>AdGroupStatus|The ad group status.|
|<a name="agegroup"></a>AgeGroup|The age group of the audience who viewed the ad.The possible values are *13-17*, *18-24*, *25-34*, *35-49*, *50-64*, and *65+*.|
|<a name="campaignid"></a>CampaignId|The Bing Ads assigned identifier of a campaign.|
|<a name="campaignname"></a>CampaignName|The campaign name.|
|<a name="campaignstatus"></a>CampaignStatus|The campaign status.|
|<a name="estimatedclickpercent"></a>EstimatedClickPercent|The estimated number of times that an ad could be clicked by a particular age group or gender, divided by the total number of estimated clicks across the ad group (including estimated clicks for unknown age and gender demographics). The value is expressed as a percent from 0 - 100. This value is an estimate because the age and gender is not known for the entire audience.|
|<a name="estimatedclicks"></a>EstimatedClicks|The estimated number of times that an ad could be clicked by a particular age group or gender. This value is an estimate because the age and gender is not known for the entire audience.|
|<a name="estimatedconversionrate"></a>EstimatedConversionRate|The estimated number of the conversions that results in a sale or another measure of success to a particular age group or gender, divided by the estimated number of clicks by a particular age group or gender.  This value is an estimate because the age and gender is not known for the entire audience.|
|<a name="estimatedconversions"></a>EstimatedConversions|The estimated number of conversions, which are the clicks that results in a sale or another measure of success, to a particular age group or gender. Conversions are measured by adding a small bit of code to your website pages so that a visitor's progress through your site can be tracked.  This value is an estimate because the age and gender is not known for the entire audience.|
|<a name="estimatedctr"></a>EstimatedCtr|The estimated click-through rate (Ctr) as a percentage.The formula for calculating the estimated click-through rate is *(estimated clicks / estimated impressions) x 100*. This value is an estimate because the age and gender is not known for the entire audience.|
|<a name="estimatedimpressionpercent"></a>EstimatedImpressionPercent|The estimated number of impressions, or the number of times an ad could be served to a particular age group or gender, divided by the total number of estimated impressions across the ad group (including estimated impressions for unknown age and gender demographics). The value is expressed as a percent from 0 - 100. This value is an estimate because the age and gender is not known for the entire audience.|
|<a name="estimatedimpressions"></a>EstimatedImpressions|The estimated number of times an ad could be served to a particular age group or gender. This value is an estimate because the age and gender is not known for the entire audience.|
|<a name="gender"></a>Gender|The gender of the audience who might have viewed the ad, if known.Possible values are Male and Female.|
|<a name="language"></a>Language|The ad group language.For possible values see [Ad Languages](~/guides/ad-languages.md). The language display name will be provided in the report e.g. *English*.|
|<a name="timeperiod"></a>TimePeriod|The time period of each report row. You may not include this column if the *Aggregation* element of the request object is set to Summary. If you include the *TimePeriod* column, the column label in the downloaded report depends on the aggregation level that you specify in the report request. For more information, see [Time Period Column](~/guides/reports.md#timeperiod).|

## <a name="remarks"></a>Remarks
### <a name="requiredcolumns"></a>Required Columns
The report must include the following columns, and one or more of the performance statistics columns. For more information, see [Report Attributes and Performance Statistics](~/guides/report-attributes-performance-statistics.md).

> [!NOTE]
> The TimePeriod column is required for all aggregation types except Summary.

|Column|
|----------|
|AccountName|
|AdGroupName|
|AgeGroup|
|Gender|
|TimePeriod|

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v11  

## Used By
[AgeGenderDemographicReportRequest](agegenderdemographicreportrequest.md)  
