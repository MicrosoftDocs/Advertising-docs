---
title: DSACategoryPerformanceReportColumn Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the attributes and performance statistics columns that you can include in the DSACategoryPerformanceReportRequest.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# DSACategoryPerformanceReportColumn Value Set - Reporting
Defines the attributes and performance statistics columns that you can include in the [DSACategoryPerformanceReportRequest](dsacategoryperformancereportrequest.md).

The attribute columns that you include in a report can affect how the statistics are aggregated. In other words the number of rows increase by a factor of the unique attributes. For more information, see [Columns that Group the Data](../guides/reports.md#columnsdata).

For a list of columns that you must include, please see the [Required Columns](#requiredcolumns) section below.

To see how far back hourly, daily, weekly, monthly, yearly and summary aggregated data can be retrieved for a report, see [Report Data Retention Time Periods](../guides/report-data-retention-time-periods.md).

## Syntax
```xml
<xs:simpleType name="DSACategoryPerformanceReportColumn" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="TimePeriod" />
    <xs:enumeration value="AccountId" />
    <xs:enumeration value="AccountName" />
    <xs:enumeration value="AccountNumber" />
    <xs:enumeration value="AccountStatus" />
    <xs:enumeration value="CampaignId" />
    <xs:enumeration value="CampaignName" />
    <xs:enumeration value="CampaignStatus" />
    <xs:enumeration value="AdGroupId" />
    <xs:enumeration value="AdGroupName" />
    <xs:enumeration value="AdGroupStatus" />
    <xs:enumeration value="AdId" />
    <xs:enumeration value="AdStatus" />
    <xs:enumeration value="Category0" />
    <xs:enumeration value="Category1" />
    <xs:enumeration value="Category2" />
    <xs:enumeration value="AdDistribution" />
    <xs:enumeration value="Language" />
    <xs:enumeration value="Network" />
    <xs:enumeration value="TopVsOther" />
    <xs:enumeration value="DeviceType" />
    <xs:enumeration value="DeviceOS" />
    <xs:enumeration value="Impressions" />
    <xs:enumeration value="Clicks" />
    <xs:enumeration value="Ctr" />
    <xs:enumeration value="AverageCpc" />
    <xs:enumeration value="Spend" />
    <xs:enumeration value="AveragePosition" />
    <xs:enumeration value="Conversions" />
    <xs:enumeration value="ConversionRate" />
    <xs:enumeration value="CostPerConversion" />
    <xs:enumeration value="Assists" />
    <xs:enumeration value="Revenue" />
    <xs:enumeration value="ReturnOnAdSpend" />
    <xs:enumeration value="CostPerAssist" />
    <xs:enumeration value="RevenuePerConversion" />
    <xs:enumeration value="RevenuePerAssist" />
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
|<a name="adid"></a>AdId|The Bing Ads assigned identifier of an ad.|
|<a name="adstatus"></a>AdStatus|The ad status.|
|<a name="assists"></a>Assists|The number of conversions from other ads within the same account that were preceded by one or more clicks from this ad.An ad is considered to have assisted the conversion if it was clicked before the most recently clicked ad that was credited with the conversion. Additionally, the click corresponding to the assist must occur  within the conversion period of the goal.|
|<a name="averagecpc"></a>AverageCpc|The average cost per click (CPC). The total cost of all clicks on an ad divided by the number of clicks. This is the average amount you're actually charged each time your ad is clicked. For example, if you paid a total of 48.35 for 300 clicks, your average CPC is 0.16.The formula for calculating the average CPC is *(Spend /Clicks)*.|
|<a name="averageposition"></a>AveragePosition|The average position of the ad on a webpage.|
|<a name="campaignid"></a>CampaignId|The Bing Ads assigned identifier of a campaign.|
|<a name="campaignname"></a>CampaignName|The campaign name.|
|<a name="campaignstatus"></a>CampaignStatus|The campaign status.|
|<a name="category0"></a>Category0|The top level category that Bing matched to your website. For example if the category is *US/CA/SFO*, the *Category0* value will be *US*.|
|<a name="category1"></a>Category1|The mid level category that Bing matched to your website. For example if the category is *US/CA/SFO*, the *Category1* value will be *CA*.|
|<a name="category2"></a>Category2|The low level category that Bing matched to your website. For example if the category is *US/CA/SFO*, the *Category2* value will be *SFO*.|
|<a name="clicks"></a>Clicks|Clicks are what you pay for. Clicks typically include a customer clicking an ad on a search results page or on a website on the search network. Clicks can also come from other sources (for example, spiders, robots, and test servers). For more information, see [Bing Ads click measurement: description of methodology](https://advertise.bingads.microsoft.com/resources/policies/bing-ads-click-measurement-description-of-methodology).|
|<a name="conversionrate"></a>ConversionRate|The conversion rate as a percentage. The number of conversions, divided by the total number of clicks. For example, if the ads in your campaign got 300 clicks and four conversions, the conversion rate is 1.33 (%).The formula for calculating the conversion rate is *(Conversions / Clicks) x 100*.|
|<a name="conversions"></a>Conversions|The number of conversions. A conversion is the completion of an action by a customer after viewing your ad. The action could be purchasing your product, registering for your webinar, joining an organization, or whatever you consider your goal and best measure of the ad's success.|
|<a name="costperassist"></a>CostPerAssist|The cost per assist. The formula for calculating the cost per assist is *(Spend / Assists)*.|
|<a name="costperconversion"></a>CostPerConversion|The cost per conversion. The formula for calculating the cost per conversion is *(Spend / Conversions)*.Only ads in campaigns that enable conversion tracking contribute to the conversion number, so unless all campaigns in the account enable conversion tracking, the number will not be accurate.|
|<a name="ctr"></a>Ctr|The click-through rate (CTR) is the number of times an ad was clicked, divided by the number of times the ad was shown (impressions). For example, if your ads got 50 clicks given 2,348 impressions, your CTR is 2.13 (%).The formula for calculating CTR is *(Clicks / Impressions) x 100*.|
|<a name="deviceos"></a>DeviceOS|The operating system of the device reported in the *DeviceType* column.The possible values include *Android*, *Blackberry*, *iOS*, *Other*, *Unknown*, and *Windows*.If the operating system of the device cannot be determined or is not one of the operating systems that you can target, the value in this column will be *Unknown*.|
|<a name="devicetype"></a>DeviceType|The device name attribute of a device OS target bid. The type of device which showed ads.The possible values include *Computer*, *Smartphone*, *Tablet*, and *Unknown*.|
|<a name="impressions"></a>Impressions|The number of times an ad has been displayed on search results pages. Without impressions there are no clicks or conversions.|
|<a name="language"></a>Language|The language of the country the ad is served in.<br/><br/>For possible values, see the Language column of [Ad Languages](../guides/ad-languages.md#adlanguage). The language display name will be provided in the report e.g. *English*.|
|<a name="network"></a>Network|The current network setting of an ad group. The possible values include AOL search, Bing and Yahoo! search, Content, and Syndicated search partners.|
|<a name="returnonadspend"></a>ReturnOnAdSpend|The return on ad spend (ROAS).The formula for calculating the ROAS is *(Revenue / Spend)*.|
|<a name="revenue"></a>Revenue|The revenue optionally reported by the advertiser as a result of conversions. Corresponds to the optional *revenue* parameter of a Bing Ads campaign analytics tracking script.|
|<a name="revenueperassist"></a>RevenuePerAssist|The revenue per assist.The formula for calculating the revenue per assist is *(Revenue / Assists)*.|
|<a name="revenueperconversion"></a>RevenuePerConversion|The revenue per conversion.The formula for calculating the revenue per conversion is *(Revenue / Conversions)*.|
|<a name="spend"></a>Spend|The cost per click (CPC) summed for each click.|
|<a name="timeperiod"></a>TimePeriod|The time period of each report row. You may not include this column if the *Aggregation* element of the request object is set to Summary. For more information, see [Time Period Column](../guides/reports.md#timeperiod).|
|<a name="topvsother"></a>TopVsOther|The report will include a column that indicates whether the ad impression appeared in a top position or elsewhere. The possible values include AOL search - Top, AOL search - Other, Bing and Yahoo! search - Top, Bing and Yahoo! search - Other, Syndicated search partners - Top, Syndicated search partners - Other, Content network, and Unknown.|

## <a name="remarks"></a>Remarks
### <a name="requiredcolumns"></a>Required Columns
The report must include the following columns, and one or more of the performance statistics columns. For more information, see [Report Attributes and Performance Statistics](../guides/report-attributes-performance-statistics.md).

> [!NOTE]
> The TimePeriod column is required for all aggregation types except Summary.

|Column|
|----------|
|Category0|
|Category1|
|Category2|
|TimePeriod|

## Requirements
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v12/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v12  

## Used By
[DSACategoryPerformanceReportRequest](dsacategoryperformancereportrequest.md)  
