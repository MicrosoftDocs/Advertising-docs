---
title: DSAAutoTargetPerformanceReportColumn Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the attributes and performance statistics columns that you can include in the DSAAutoTargetPerformanceReportRequest.
---
# DSAAutoTargetPerformanceReportColumn Value Set - Reporting
Defines the attributes and performance statistics columns that you can include in the [DSAAutoTargetPerformanceReportRequest](../reporting-service/dsaautotargetperformancereportrequest.md).

The attribute columns that you include in a report can affect how the statistics are aggregated. In other words the number of rows increase by a factor of the unique attributes. For more information, see [Columns that Group the Data](/bingads/guides/reports.md#columnsdata).

For a list of columns that you must include, please see the [Required Columns](#requiredcolumns) section below.

To see how far back hourly, daily, weekly, monthly, yearly and summary aggregated data can be retrieved for a report, see [Report Data Retention Time Periods](/bingads/guides/report-data-retention-time-periods.md).

## Syntax
```xml
<xs:simpleType name="DSAAutoTargetPerformanceReportColumn" xmlns:xs="http://www.w3.org/2001/XMLSchema">
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
    <xs:enumeration value="AdDistribution" />
    <xs:enumeration value="Language" />
    <xs:enumeration value="Network" />
    <xs:enumeration value="TopVsOther" />
    <xs:enumeration value="DeviceType" />
    <xs:enumeration value="DeviceOS" />
    <xs:enumeration value="BidStrategyType" />
    <xs:enumeration value="TrackingTemplate" />
    <xs:enumeration value="CustomParameters" />
    <xs:enumeration value="DynamicAdTargetId" />
    <xs:enumeration value="DynamicAdTarget" />
    <xs:enumeration value="DynamicAdTargetStatus" />
    <xs:enumeration value="WebsiteCoverage" />
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
|<a name="assists"></a>Assists|The number of conversions from other ads within the same account that were preceded by one or more clicks from this ad.An ad is considered to have assisted the conversion if it was clicked before the most recently clicked ad that was credited with the conversion. Additionally, the click corresponding to the assist must occur  within the conversion period of the goal.|
|<a name="averagecpc"></a>AverageCpc|The average cost per click (CPC). The total cost of all clicks on an ad divided by the number of clicks. This is the average amount you're actually charged each time your ad is clicked. For example, if you paid a total of 48.35 for 300 clicks, your average CPC is 0.16.The formula for calculating the average CPC is *(Spend /Clicks)*.|
|<a name="averageposition"></a>AveragePosition|The average position of the ad on a webpage.|
|<a name="bidstrategytype"></a>BidStrategyType|The bid strategy type. Possible values include *EnhancedCpc*, *ManualCpc*, *MaxClicks*, *MaxConversions*, and *TargetCpa*. If the *InheritFromParent* strategy type is used, the report will include the inherited bid strategy type e.g. one of the supported values listed above.|
|<a name="campaignid"></a>CampaignId|The Bing Ads assigned identifier of a campaign.|
|<a name="campaignname"></a>CampaignName|The campaign name.|
|<a name="campaignstatus"></a>CampaignStatus|The campaign status.|
|<a name="clicks"></a>Clicks|Clicks are what you pay for. Clicks typically include a customer clicking an ad on a search results page or on a website on the search network. Clicks can also come from other sources (for example, spiders, robots, and test servers). For more information, see [Bing Ads click measurement: description of methodology](https://advertise.bingads.microsoft.com/resources/policies/bing-ads-click-measurement-description-of-methodology).|
|<a name="conversionrate"></a>ConversionRate|The conversion rate as a percentage. The number of conversions, divided by the total number of clicks. For example, if the ads in your campaign got 300 clicks and four conversions, the conversion rate is 1.33 (%).The formula for calculating the conversion rate is *(Conversions / Clicks) x 100*.|
|<a name="conversions"></a>Conversions|The number of conversions. A conversion is the completion of an action by a customer after viewing your ad. The action could be purchasing your product, registering for your webinar, joining an organization, or whatever you consider your goal and best measure of the ad's success.|
|<a name="costperassist"></a>CostPerAssist|The cost per assist. The formula for calculating the cost per assist is *(Spend / Assists)*.|
|<a name="costperconversion"></a>CostPerConversion|The cost per conversion. The formula for calculating the cost per conversion is *(Spend / Conversions)*.Only ads in campaigns that enable conversion tracking contribute to the conversion number, so unless all campaigns in the account enable conversion tracking, the number will not be accurate.|
|<a name="ctr"></a>Ctr|The click-through rate (CTR) is the number of times an ad was clicked, divided by the number of times the ad was shown (impressions). For example, if your ads got 50 clicks given 2,348 impressions, your CTR is 2.13 (%).The formula for calculating CTR is *(Clicks / Impressions) x 100*.|
|<a name="customparameters"></a>CustomParameters|The current custom parameters of the ad.|
|<a name="deviceos"></a>DeviceOS|The operating system of the device reported in the *DeviceType* column.The possible values include *Android*, *Blackberry*, *iOS*, *Other*, *Unknown*, and *Windows*.If the operating system of the device cannot be determined or is not one of the operating systems that you can target, the value in this column will be *Unknown*.|
|<a name="devicetype"></a>DeviceType|The device name attribute of a device OS target bid. The type of device which showed ads.The possible values include *Computer*, *Smartphone*, *Tablet*, and *Unknown*.|
|<a name="dynamicadtarget"></a>DynamicAdTarget|The dynamic ad target or webpage condition that Bing matched to your website. For example the condition could be returned in the report as *URL contains xyz*.|
|<a name="dynamicadtargetid"></a>DynamicAdTargetId|The Bing Ads assigned identifier of the dynamic ad target, also known in Campaign Management and Bulk API as the ad group criterion ID.|
|<a name="dynamicadtargetstatus"></a>DynamicAdTargetStatus|The current status of the dynamic ad target.|
|<a name="impressions"></a>Impressions|The number of times an ad has been displayed on search results pages. Without impressions there are no clicks or conversions.|
|<a name="language"></a>Language|The ad group language.For possible values see [Ad Languages](/bingads/guides/ad-languages.md). The language display name will be provided in the report e.g. *English*.|
|<a name="network"></a>Network|The current network setting of an ad group. The possible values include AOL search, Bing and Yahoo! search, Content, and Syndicated search partners.|
|<a name="returnonadspend"></a>ReturnOnAdSpend|The return on ad spend (ROAS).The formula for calculating the ROAS is *(Revenue / Spend)*.|
|<a name="revenue"></a>Revenue|The revenue optionally reported by the advertiser as a result of conversions. Corresponds to the optional *revenue* parameter of a Bing Ads campaign analytics tracking script.|
|<a name="revenueperassist"></a>RevenuePerAssist|The revenue per assist.The formula for calculating the revenue per assist is *(Revenue / Assists)*.|
|<a name="revenueperconversion"></a>RevenuePerConversion|The revenue per conversion.The formula for calculating the revenue per conversion is *(Revenue / Conversions)*.|
|<a name="spend"></a>Spend|The cost per click (CPC) summed for each click.|
|<a name="timeperiod"></a>TimePeriod|The time period of each report row. You may not include this column if the *Aggregation* element of the request object is set to Summary. If you include the *TimePeriod* column, the column label in the downloaded report depends on the aggregation level that you specify in the report request. For more information, see [Time Period Column](/bingads/guides/reports.md#timeperiod).|
|<a name="topvsother"></a>TopVsOther|The report will include a column that indicates whether the ad impression appeared in a top position or elsewhere. The possible values include AOL search - Top, AOL search - Other, Bing and Yahoo! search - Top, Bing and Yahoo! search - Other, Syndicated search partners - Top, Syndicated search partners - Other, Content network, and Unknown.|
|<a name="trackingtemplate"></a>TrackingTemplate|The current tracking template of the ad. |
|<a name="websitecoverage"></a>WebsiteCoverage|A score from 0.0 to 1.0 that indicates the percentage of pages in the requested language that belong to a particular domain out of all the pages that Bing has indexed for the same language your website's domain.In other words coverage is the percentage of webpages that match a category and language divided by the total number of webpages using the same language in the domain.For example, if the category *US/CA/SFO* matches 500 english webpages and *US/CA* matches 1,000 english webpages, then the coverage will be 0.50 (50 percent).|

## <a name="remarks"></a>Remarks
### <a name="requiredcolumns"></a>Required Columns
The report must include the following columns, and one or more of the performance statistics columns. For more information, see [Report Attributes and Performance Statistics](/bingads/guides/report-attributes-performance-statistics.md).

> [!NOTE]
> The TimePeriod column is required for all aggregation types except Summary.

|Column|
|----------|
|DynamicAdTargetId|
|TimePeriod|

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v11  

## Used By
[DSAAutoTargetPerformanceReportRequest](dsaautotargetperformancereportrequest.md)  
