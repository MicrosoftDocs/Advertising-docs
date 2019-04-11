---
title: AccountPerformanceReportColumn Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the attributes and performance statistics columns that you can include in the AccountPerformanceReportRequest.
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# AccountPerformanceReportColumn Value Set - Reporting
Defines the attributes and performance statistics columns that you can include in the [AccountPerformanceReportRequest](accountperformancereportrequest.md).

The attribute columns that you include in a report can affect how the statistics are aggregated. In other words the number of rows increase by a factor of the unique attributes. For more information, see [Columns that Group the Data](../guides/reports.md#columnsdata).

For a list of columns that you must include, please see the [Required Columns](#requiredcolumns) section below.

To see how far back hourly, daily, weekly, monthly, yearly and summary aggregated data can be retrieved for a report, see [Report Data Retention Time Periods](../guides/report-data-retention-time-periods.md).

## Syntax
```xml
<xs:simpleType name="AccountPerformanceReportColumn" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="AccountName" />
    <xs:enumeration value="AccountNumber" />
    <xs:enumeration value="AccountId" />
    <xs:enumeration value="TimePeriod" />
    <xs:enumeration value="CurrencyCode" />
    <xs:enumeration value="AdDistribution" />
    <xs:enumeration value="Impressions" />
    <xs:enumeration value="Clicks" />
    <xs:enumeration value="Ctr" />
    <xs:enumeration value="AverageCpc" />
    <xs:enumeration value="Spend" />
    <xs:enumeration value="AveragePosition" />
    <xs:enumeration value="Conversions" />
    <xs:enumeration value="ConversionRate" />
    <xs:enumeration value="CostPerConversion" />
    <xs:enumeration value="LowQualityClicks" />
    <xs:enumeration value="LowQualityClicksPercent" />
    <xs:enumeration value="LowQualityImpressions" />
    <xs:enumeration value="LowQualityImpressionsPercent" />
    <xs:enumeration value="LowQualityConversions" />
    <xs:enumeration value="LowQualityConversionRate" />
    <xs:enumeration value="DeviceType" />
    <xs:enumeration value="DeviceOS" />
    <xs:enumeration value="ImpressionSharePercent" />
    <xs:enumeration value="ImpressionLostToBudgetPercent" />
    <xs:enumeration value="ImpressionLostToRankAggPercent" />
    <xs:enumeration value="PhoneImpressions" />
    <xs:enumeration value="PhoneCalls" />
    <xs:enumeration value="Ptr" />
    <xs:enumeration value="Network" />
    <xs:enumeration value="TopVsOther" />
    <xs:enumeration value="BidMatchType" />
    <xs:enumeration value="DeliveredMatchType" />
    <xs:enumeration value="Assists" />
    <xs:enumeration value="Revenue" />
    <xs:enumeration value="ReturnOnAdSpend" />
    <xs:enumeration value="CostPerAssist" />
    <xs:enumeration value="RevenuePerConversion" />
    <xs:enumeration value="RevenuePerAssist" />
    <xs:enumeration value="AccountStatus" />
    <xs:enumeration value="LowQualityGeneralClicks" />
    <xs:enumeration value="LowQualitySophisticatedClicks" />
    <xs:enumeration value="ExactMatchImpressionSharePercent" />
    <xs:enumeration value="CustomerId" />
    <xs:enumeration value="CustomerName" />
    <xs:enumeration value="ClickSharePercent" />
    <xs:enumeration value="AbsoluteTopImpressionSharePercent" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="absolutetopimpressionsharepercent"></a>AbsoluteTopImpressionSharePercent|The number of times your ad is shown in the top position as a percentage of the total available impressions in the market you were targeting.<br/><br/>Reports on impression highlight information about how many impressions you're missing in the top slot and why. You can use this data to inform you about making changes to get more impressions, increase the likelihood of more clicks on those ads, and as a result, increase the likelihood of more sales.<br/><br/>If you include this column, then you may not include restricted attributes such as [TopVsOther](#topvsother) in the same report request. Likewise if you include any of the restricted attribute columns, then you must exclude this column. For more information, see [Column Restrictions](../guides/reports.md#columnrestrictions).|
|<a name="accountid"></a>AccountId|The Bing Ads assigned identifier of an account.|
|<a name="accountname"></a>AccountName|The account name.|
|<a name="accountnumber"></a>AccountNumber|The Bing Ads assigned number of an account.|
|<a name="accountstatus"></a>AccountStatus|The account status.|
|<a name="addistribution"></a>AdDistribution|The network where you want your ads to show.|
|<a name="assists"></a>Assists|The number of conversions from other ads within the same account that were preceded by one or more clicks from this ad. An ad is considered to have assisted the conversion if it was clicked before the most recently clicked ad that was credited with the conversion. Additionally, the click corresponding to the assist must occur  within the conversion period of the goal.|
|<a name="averagecpc"></a>AverageCpc|The average cost per click (CPC). The total cost of all clicks on an ad divided by the number of clicks. This is the average amount you're actually charged each time your ad is clicked. For example, if you paid a total of 48.35 for 300 clicks, your average CPC is 0.16. The formula for calculating the average CPC is *(Spend /Clicks)*.|
|<a name="averageposition"></a>AveragePosition|The average position of the ad on a webpage.|
|<a name="bidmatchtype"></a>BidMatchType|The keyword bid match type. This can be different from the *DeliveredMatchType* column, for example if you bid on a broad match and the search term was an exact match. For more information, see [Budget and Bid Strategies](../guides/budget-bid-strategies.md). The possible values are *Broad*, *Exact*, *Phrase*, and *Unknown*.|
|<a name="clicks"></a>Clicks|Clicks are what you pay for. Clicks typically include a customer clicking an ad on a search results page or on a website on the search network. Clicks can also come from other sources (for example, spiders, robots, and test servers). For more information, see [Bing Ads click measurement: description of methodology](https://advertise.bingads.microsoft.com/resources/policies/bing-ads-click-measurement-description-of-methodology).|
|<a name="clicksharepercent"></a>ClickSharePercent|The percentage of clicks that went to your ads. It is the share of the prospective customer's mindshare and buying intent you captured. You can use this performance metric to see where your growth opportunites are.<br/><br/>For example, your click share percent is 30% if 10 ads were clicked, and three of the 10 ads were yours.<br/><br/>If you include this column, then you may not include restricted attributes such as [TopVsOther](#topvsother) in the same report request. Likewise if you include any of the restricted attribute columns, then you must exclude this column. For more information, see [Column Restrictions](../guides/reports.md#columnrestrictions).|
|<a name="conversionrate"></a>ConversionRate|The conversion rate as a percentage. The number of conversions, divided by the total number of clicks. For example, if the ads in your campaign got 300 clicks and four conversions, the conversion rate is 1.33 (%). The formula for calculating the conversion rate is *(Conversions / Clicks) x 100*.|
|<a name="conversions"></a>Conversions|The number of conversions. A conversion is the completion of an action by a customer after viewing your ad. The action could be purchasing your product, registering for your webinar, joining an organization, or whatever you consider your goal and best measure of the ad's success.|
|<a name="costperassist"></a>CostPerAssist|The cost per assist. The formula for calculating the cost per assist is *(Spend / Assists)*.|
|<a name="costperconversion"></a>CostPerConversion|The cost per conversion. The formula for calculating the cost per conversion is *(Spend / Conversions)*. Only ads in campaigns that enable conversion tracking contribute to the conversion number, so unless all campaigns in the account enable conversion tracking, the number will not be accurate.|
|<a name="ctr"></a>Ctr|The click-through rate (CTR) is the number of times an ad was clicked, divided by the number of times the ad was shown (impressions). For example, if your ads got 50 clicks given 2,348 impressions, your CTR is 2.13 (%). The formula for calculating CTR is *(Clicks / Impressions) x 100*.|
|<a name="currencycode"></a>CurrencyCode|The account currency type. For possible values, see [Currencies](../guides/currencies.md).|
|<a name="customerid"></a>CustomerId|The Bing Ads assigned identifier of a customer.|
|<a name="customername"></a>CustomerName|The customer name.|
|<a name="deliveredmatchtype"></a>DeliveredMatchType|The match type used to deliver an ad. This can be different from the *BidMatchType* column, for example if you bid on a broad match and the search term was an exact match. For more information, see [Budget and Bid Strategies](../guides/budget-bid-strategies.md). The possible values are *Broad*, *Exact*, *Phrase*, and *Unknown*.|
|<a name="deviceos"></a>DeviceOS|The operating system of the device reported in the *DeviceType* column. The possible values include *Android*, *Blackberry*, *iOS*, *Other*, *Unknown*, and *Windows*. If the operating system of the device cannot be determined or is not one of the operating systems that you can target, the value in this column will be *Unknown*.|
|<a name="devicetype"></a>DeviceType|The device name attribute of a device OS target bid. The type of device which showed ads. The possible values include *Computer*, *Smartphone*, *Tablet*, and *Unknown*.|
|<a name="exactmatchimpressionsharepercent"></a>ExactMatchImpressionSharePercent|The estimated percentage of impressions that your account received for searches that exactly matched your keyword, out of the total available exact match impressions you were eligible to receive.<br/><br/>Reports on exact match impression share highlight how your keywords perform only on those searches that exactly match your keywords. Use this data together with impression share to diagnose your non-exact match keywords, and make changes to be more competitive and gain more impressions.|
|<a name="impressionlosttobudgetpercent"></a>ImpressionLostToBudgetPercent|The estimated percentage of impressions your ad did not receive due to issues with your daily or monthly budget. The value of this column is empty if the data is not available. If you try to include this column with *Hourly* or *HourOfDay* aggregation the service will return code *2053*. If you include this column, then you may not include restricted attributes such as [TopVsOther](#topvsother) in the same report request. Likewise if you include any of the restricted attribute columns, then you must exclude this column. For more information, see [Column Restrictions](../guides/reports.md#columnrestrictions). Data for this column is typically updated 14-18 hours after the UTC day ends. For Bing Shopping campaigns, this data is only available with the campaign and ad group performance reports.|
|<a name="impressionlosttorankaggpercent"></a>ImpressionLostToRankAggPercent|The estimated percentage of impressions your ad did not receive due to issues with your ad ranking. The value of this column is empty if the data is not available. If you try to include this column with *Hourly* or *HourOfDay* aggregation the service will return code *2053*. If you include this column, then you may not include restricted attributes such as [TopVsOther](#topvsother) in the same report request. Likewise if you include any of the restricted attribute columns, then you must exclude this column. For more information, see [Column Restrictions](../guides/reports.md#columnrestrictions). Data for this column is typically updated 14-18 hours after the UTC day ends. For Bing Shopping campaigns, this data is not available.|
|<a name="impressions"></a>Impressions|The number of times an ad has been displayed on search results pages. Without impressions there are no clicks or conversions.|
|<a name="impressionsharepercent"></a>ImpressionSharePercent|The estimated percentage of impressions, out of the total available impressions in the market you were targeting. The value of this column is empty if the data is not available. For example, out of estimated 59,000 impressions that occurred on this day in your targeted market, you got only about 2,300, or 3%. If you try to include this column with *Hourly* or *HourOfDay* aggregation the service will return code *2053*. If you include this column, then you may not include restricted attributes such as [TopVsOther](#topvsother) in the same report request. Likewise if you include any of the restricted attribute columns, then you must exclude this column. For more information, see [Column Restrictions](../guides/reports.md#columnrestrictions). Data for this column is typically updated 14-18 hours after the UTC day ends. For Bing Shopping campaigns, this data is only available with the campaign and ad group performance reports.|
|<a name="lowqualityclicks"></a>LowQualityClicks|Clicks that exhibit a low likelihood of commercial intent. You are not billed for these clicks. For more information, see [Bing Ads click measurement: description of methodology](https://advertise.bingads.microsoft.com/resources/policies/bing-ads-click-measurement-description-of-methodology).|
|<a name="lowqualityclickspercent"></a>LowQualityClicksPercent|The low-quality clicks as a percentage. The formula for calculating the low quality clicks percentage is *(LowQualityClicks / Clicks) x 100*.|
|<a name="lowqualityconversionrate"></a>LowQualityConversionRate|The low-quality conversion rate as a percentage. The formula for calculating the conversion rate is *(LowQualityConversions / LowQualityClicks) x 100*.|
|<a name="lowqualityconversions"></a>LowQualityConversions|The number of conversions that originate from low-quality clicks.|
|<a name="lowqualitygeneralclicks"></a>LowQualityGeneralClicks|Clicks that are filtered by general methods, such as blacklists and activity-based detection, and that exhibit a low likelihood of commercial intent. You are not billed for these clicks. For more information, see [Bing Ads click measurement: description of methodology](https://advertise.bingads.microsoft.com/resources/policies/bing-ads-click-measurement-description-of-methodology).|
|<a name="lowqualityimpressions"></a>LowQualityImpressions|The number of impressions that result from low-quality keyword searches.|
|<a name="lowqualityimpressionspercent"></a>LowQualityImpressionsPercent|The low-quality impressions as a percentage. The formula for calculating the percentage is *(LowQualityImpressions / Impressions) x 100*.|
|<a name="lowqualitysophisticatedclicks"></a>LowQualitySophisticatedClicks|Invalid clicks that use sophisticated means to appear valid. You are not billed for these clicks. For more information, see [Bing Ads click measurement: description of methodology](https://advertise.bingads.microsoft.com/resources/policies/bing-ads-click-measurement-description-of-methodology).|
|<a name="network"></a>Network|The combined search advertising marketplace made up of Bing, AOL, Yahoo, and partner sites. Use this data to make the best decision on network selection for your ad groups. The possible values include AOL search, Audience, Bing and Yahoo! search, Content, and Syndicated search partners.|
|<a name="phonecalls"></a>PhoneCalls|The number of total calls to the tracked phone number that showed with your ad.|
|<a name="phoneimpressions"></a>PhoneImpressions|The number of times your tracked number was shown on all devices.|
|<a name="ptr"></a>Ptr|The phone-through rate (Ptr). The formula for calculating the Ptr is *(PhoneCalls / PhoneImpressions) x 100*.|
|<a name="returnonadspend"></a>ReturnOnAdSpend|The return on ad spend (ROAS). The formula for calculating the ROAS is *(Revenue / Spend)*.|
|<a name="revenue"></a>Revenue|The revenue optionally reported by the advertiser as a result of conversions.<br/><br/>Available for accounts that are setup to use analytics with Bing Ads Universal Event Tracking. For more information, see the [Track sales and other conversions](https://go.microsoft.com/fwlink/?LinkID=624771) help topic.|
|<a name="revenueperassist"></a>RevenuePerAssist|The revenue per assist. The formula for calculating the revenue per assist is *(Revenue / Assists)*.|
|<a name="revenueperconversion"></a>RevenuePerConversion|The revenue per conversion. The formula for calculating the revenue per conversion is *(Revenue / Conversions)*.|
|<a name="spend"></a>Spend|The cost per click (CPC) summed for each click.|
|<a name="timeperiod"></a>TimePeriod|The time period of each report row. You may not include this column if the *Aggregation* element of the request object is set to Summary. For more information, see [Time Period Column](../guides/reports.md#timeperiod).|
|<a name="topvsother"></a>TopVsOther|The report will include a column that indicates whether the ad impression appeared in a top position or elsewhere. The possible values include AOL search - Top, AOL search - Other, Audience network, Bing and Yahoo! search - Top, Bing and Yahoo! search - Other, Syndicated search partners - Top, Syndicated search partners - Other, Content network, and Unknown.|

## <a name="remarks"></a>Remarks
### <a name="requiredcolumns"></a>Required Columns
The report must include the following columns, and one or more of the performance statistics columns. For more information, see [Report Attributes and Performance Statistics](../guides/report-attributes-performance-statistics.md).

> [!NOTE]
> The TimePeriod column is required for all aggregation types except Summary.

|Column|
|----------|
|TimePeriod|

## Requirements
Service: [ReportingService.svc v13](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v13/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v13  

## Used By
[AccountPerformanceReportRequest](accountperformancereportrequest.md)  
