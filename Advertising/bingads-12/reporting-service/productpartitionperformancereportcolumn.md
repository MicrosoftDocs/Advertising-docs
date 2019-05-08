---
title: ProductPartitionPerformanceReportColumn Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the attributes and performance statistics columns that you can include in the ProductPartitionPerformanceReportRequest.
---
# ProductPartitionPerformanceReportColumn Value Set - Reporting
Defines the attributes and performance statistics columns that you can include in the [ProductPartitionPerformanceReportRequest](productpartitionperformancereportrequest.md).

The attribute columns that you include in a report can affect how the statistics are aggregated. In other words the number of rows increase by a factor of the unique attributes. For more information, see [Columns that Group the Data](../guides/reports.md#columnsdata).

For a list of columns that you must include, please see the [Required Columns](#requiredcolumns) section below.

To see how far back hourly, daily, weekly, monthly, yearly and summary aggregated data can be retrieved for a report, see [Report Data Retention Time Periods](../guides/report-data-retention-time-periods.md).

## Syntax
```xml
<xs:simpleType name="ProductPartitionPerformanceReportColumn" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="AccountName" />
    <xs:enumeration value="AccountNumber" />
    <xs:enumeration value="AccountId" />
    <xs:enumeration value="TimePeriod" />
    <xs:enumeration value="CampaignName" />
    <xs:enumeration value="CampaignId" />
    <xs:enumeration value="AdGroupName" />
    <xs:enumeration value="AdGroupId" />
    <xs:enumeration value="ProductGroup" />
    <xs:enumeration value="AdGroupCriterionId" />
    <xs:enumeration value="PartitionType" />
    <xs:enumeration value="AdId" />
    <xs:enumeration value="CurrentMaxCpc" />
    <xs:enumeration value="CurrencyCode" />
    <xs:enumeration value="DeliveredMatchType" />
    <xs:enumeration value="BidMatchType" />
    <xs:enumeration value="Impressions" />
    <xs:enumeration value="Clicks" />
    <xs:enumeration value="Ctr" />
    <xs:enumeration value="AverageCpc" />
    <xs:enumeration value="Spend" />
    <xs:enumeration value="Conversions" />
    <xs:enumeration value="ConversionRate" />
    <xs:enumeration value="CostPerConversion" />
    <xs:enumeration value="DeviceType" />
    <xs:enumeration value="Language" />
    <xs:enumeration value="CampaignStatus" />
    <xs:enumeration value="AccountStatus" />
    <xs:enumeration value="AdGroupStatus" />
    <xs:enumeration value="DestinationUrl" />
    <xs:enumeration value="Network" />
    <xs:enumeration value="TopVsOther" />
    <xs:enumeration value="Assists" />
    <xs:enumeration value="Revenue" />
    <xs:enumeration value="CostPerAssist" />
    <xs:enumeration value="RevenuePerConversion" />
    <xs:enumeration value="RevenuePerAssist" />
    <xs:enumeration value="OfferLanguage" />
    <xs:enumeration value="CountryOfSale" />
    <xs:enumeration value="AdStatus" />
    <xs:enumeration value="TrackingTemplate" />
    <xs:enumeration value="CustomParameters" />
    <xs:enumeration value="ImpressionSharePercent" />
    <xs:enumeration value="ImpressionLostToBudgetPercent" />
    <xs:enumeration value="ImpressionLostToRankPercent" />
    <xs:enumeration value="BenchmarkBid" />
    <xs:enumeration value="BenchmarkCtr" />
    <xs:enumeration value="AdDistribution" />
    <xs:enumeration value="ClickTypeId" />
    <xs:enumeration value="TotalClicksOnAdElements" />
    <xs:enumeration value="ClickType" />
    <xs:enumeration value="ReturnOnAdSpend" />
    <xs:enumeration value="BidStrategyType" />
    <xs:enumeration value="LocalStoreCode" />
    <xs:enumeration value="AssistedImpressions" />
    <xs:enumeration value="AssistedClicks" />
    <xs:enumeration value="ClickSharePercent" />
    <xs:enumeration value="AbsoluteTopImpressionSharePercent" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="absolutetopimpressionsharepercent"></a>AbsoluteTopImpressionSharePercent|The number of times your ad is shown in the top position as a percentage of the total available impressions in the market you were targeting.<br/><br/>Reports on impression highlight information about how many impressions you're missing in the top slot and why. You can use this data to inform you about making changes to get more impressions, increase the likelihood of more clicks on those ads, and as a result, increase the likelihood of more sales.<br/><br/>If you include this column, then you may not include restricted attributes such as [TopVsOther](#topvsother) in the same report request. Likewise if you include any of the restricted attribute columns, then you must exclude this column. For more information, see [Column Restrictions](../guides/reports.md#columnrestrictions).|
|<a name="accountid"></a>AccountId|The Microsoft Advertising assigned identifier of an account.|
|<a name="accountname"></a>AccountName|The account name.|
|<a name="accountnumber"></a>AccountNumber|The Microsoft Advertising assigned number of an account.|
|<a name="accountstatus"></a>AccountStatus|The account status.|
|<a name="addistribution"></a>AdDistribution|The network where you want your ads to show.|
|<a name="adgroupcriterionid"></a>AdGroupCriterionId|The Microsoft Advertising assigned identifier of an ad group criterion, or product group in the context of a Microsoft Shopping campaign.|
|<a name="adgroupid"></a>AdGroupId|The Microsoft Advertising assigned identifier of an ad group.|
|<a name="adgroupname"></a>AdGroupName|The ad group name.|
|<a name="adgroupstatus"></a>AdGroupStatus|The ad group status.|
|<a name="adid"></a>AdId|The Microsoft Advertising assigned identifier of an ad.|
|<a name="adstatus"></a>AdStatus|The ad status.|
|<a name="assistedclicks"></a>AssistedClicks|Clicks on your ads that have received co-bids from your manufacturer partners. Clicks are what you pay for.<br/><br/>Clicks typically include a customer clicking an ad on a search results page or on a website on the search network. Clicks can also come from other sources (for example, spiders, robots, and test servers).<br/><br/>This performance statistic is only applicable for cooperative shopping campaigns.|
|<a name="assistedimpressions"></a>AssistedImpressions|The number of times an ad that is being co-bid by your manufacturer partners has been displayed on search results pages or other sites on the Microsoft Advertising Network.<br/><br/>This performance statistic is only applicable for cooperative shopping campaigns.|
|<a name="assists"></a>Assists|The number of conversions from other ads within the same account that were preceded by one or more clicks from this ad. An ad is considered to have assisted the conversion if it was clicked before the most recently clicked ad that was credited with the conversion. Additionally, the click corresponding to the assist must occur  within the conversion period of the goal.|
|<a name="averagecpc"></a>AverageCpc|The average cost per click (CPC). The total cost of all clicks on an ad divided by the number of clicks. This is the average amount you're actually charged each time your ad is clicked. For example, if you paid a total of 48.35 for 300 clicks, your average CPC is 0.16. The formula for calculating the average CPC is *(Spend /Clicks)*.|
|<a name="benchmarkbid"></a>BenchmarkBid|Shows you how much other advertisers are bidding on average on similar products as your current target. Use this information as a benchmark to compare your bidding strategy for a product group against that of other advertisers advertising similar products. If the benchmark bid is significantly higher than your bid, you might consider raising your bid.|
|<a name="benchmarkctr"></a>BenchmarkCtr|Shows you how other product ads for similar products are performing on average based on how often people who see the ad end up clicking on it. If the benchmark CTR is significantly higher than the CTR for your product group, you might consider raising your bid for that product group, or improving the product information, particularly product images and titles.|
|<a name="bidmatchtype"></a>BidMatchType|The keyword bid match type. This can be different from the *DeliveredMatchType* column, for example if you bid on a broad match and the search term was an exact match. For more information, see [Budget and Bid Strategies](../guides/budget-bid-strategies.md). The possible values are *Broad*, *Exact*, *Phrase*, and *Unknown*.|
|<a name="bidstrategytype"></a>BidStrategyType|The bid strategy type. Possible values include *EnhancedCpc* and *ManualCpc*. If the InheritFromParent strategy type is used, the report will include the inherited bid strategy type e.g. one of the supported values listed above.|
|<a name="campaignid"></a>CampaignId|The Microsoft Advertising assigned identifier of a campaign.|
|<a name="campaignname"></a>CampaignName|The campaign name.|
|<a name="campaignstatus"></a>CampaignStatus|The campaign status.|
|<a name="clicks"></a>Clicks|Clicks are what you pay for. Clicks typically include a customer clicking an ad on a search results page or on a website on the search network. Clicks can also come from other sources (for example, spiders, robots, and test servers). For more information, see [Microsoft Advertising click measurement: description of methodology](https://about.ads.microsoft.com/en-us/resources/policies/microsoft-advertising-click-measurement-description-of-methodology).|
|<a name="clicksharepercent"></a>ClickSharePercent|The percentage of clicks that went to your ads. It is the share of the prospective customer's mindshare and buying intent you captured. You can use this performance metric to see where your growth opportunites are.<br/><br/>For example, your click share percent is 30% if 10 ads were clicked, and three of the 10 ads were yours.<br/><br/>If you include this column, then you may not include restricted attributes such as [TopVsOther](#topvsother) in the same report request. Likewise if you include any of the restricted attribute columns, then you must exclude this column. For more information, see [Column Restrictions](../guides/reports.md#columnrestrictions).|
|<a name="clicktype"></a>ClickType|Click type refers to each component of an ad that a customer can click. The possible click types are ad title, image, phone number, driving directions, sitelink, and review.|
|<a name="clicktypeid"></a>ClickTypeId|The click type ID.|
|<a name="conversionrate"></a>ConversionRate|The conversion rate as a percentage. The number of conversions, divided by the total number of clicks. For example, if the ads in your campaign got 300 clicks and four conversions, the conversion rate is 1.33 (%). The formula for calculating the conversion rate is *(Conversions / Clicks) x 100*.|
|<a name="conversions"></a>Conversions|The number of conversions. A conversion is the completion of an action by a customer after viewing your ad. The action could be purchasing your product, registering for your webinar, joining an organization, or whatever you consider your goal and best measure of the ad's success.|
|<a name="costperassist"></a>CostPerAssist|The cost per assist. The formula for calculating the cost per assist is *(Spend / Assists)*.|
|<a name="costperconversion"></a>CostPerConversion|The cost per conversion. The formula for calculating the cost per conversion is *(Spend / Conversions)*. Only ads in campaigns that enable conversion tracking contribute to the conversion number, so unless all campaigns in the account enable conversion tracking, the number will not be accurate.|
|<a name="countryofsale"></a>CountryOfSale|The report will include a column that contains the country of sale for the product catalog.|
|<a name="ctr"></a>Ctr|The click-through rate (CTR) is the number of times an ad was clicked, divided by the number of times the ad was shown (impressions). For example, if your ads got 50 clicks given 2,348 impressions, your CTR is 2.13 (%). The formula for calculating CTR is *(Clicks / Impressions) x 100*.|
|<a name="currencycode"></a>CurrencyCode|The account currency type. For possible values, see [Currencies](../guides/currencies.md).|
|<a name="currentmaxcpc"></a>CurrentMaxCpc|The maximum cost per click bid that was in effect at the time the report was generated. It is not a moving historical bid throughout the report time period.|
|<a name="customparameters"></a>CustomParameters|The current custom parameter set of the criterion.<br/><br/>Each custom parameter is a key and value pair. The list of custom parameters is semicolon-delimited and each key is enclosed by braces and a leading underscore, for example *{_key1}=value1;{_key2}=value2*.|
|<a name="deliveredmatchtype"></a>DeliveredMatchType|The match type used to deliver an ad. This can be different from the *BidMatchType* column, for example if you bid on a broad match and the search term was an exact match. For more information, see [Budget and Bid Strategies](../guides/budget-bid-strategies.md). The possible values are *Broad*, *Exact*, *Phrase*, and *Unknown*.|
|<a name="destinationurl"></a>DestinationUrl|The destination URL attribute of the ad, keyword, or ad group criterion. If the destination URL contains dynamic text substitution parameters (for example, {param1}), the report will contain the URL after substitution occurs.|
|<a name="devicetype"></a>DeviceType|The device name attribute of a device OS target bid. The type of device which showed ads. The possible values include *Computer*, *Smartphone*, *Tablet*, and *Unknown*.|
|<a name="impressionlosttobudgetpercent"></a>ImpressionLostToBudgetPercent|The estimated percentage of impressions your ad did not receive due to issues with your daily or monthly budget. The value of this column is empty if the data is not available. If you try to include this column with *Hourly* or *HourOfDay* aggregation the service will return code *2053*. If you include this column, then you may not include restricted attributes such as [TopVsOther](#topvsother) in the same report request. Likewise if you include any of the restricted attribute columns, then you must exclude this column. For more information, see [Column Restrictions](../guides/reports.md#columnrestrictions). Data for this column is typically updated 14-18 hours after the UTC day ends. For Microsoft Shopping Campaigns, this data is only available with the campaign and ad group performance reports.|
|<a name="impressionlosttorankpercent"></a>ImpressionLostToRankPercent|The estimated percentage of impressions your ad did not receive due to issues with your ad ranking. The value of this column is empty if the data is not available. If you try to include this column with *Hourly* or *HourOfDay* aggregation the service will return code *2053*. If you include this column, then you may not include restricted attributes such as [TopVsOther](#topvsother) in the same report request. Likewise if you include any of the restricted attribute columns, then you must exclude this column. For more information, see [Column Restrictions](../guides/reports.md#columnrestrictions). Data for this column is typically updated 14-18 hours after the UTC day ends. For Microsoft Shopping Campaigns, this data is not available.|
|<a name="impressions"></a>Impressions|The number of times an ad has been displayed on search results pages. Without impressions there are no clicks or conversions.|
|<a name="impressionsharepercent"></a>ImpressionSharePercent|The estimated percentage of impressions, out of the total available impressions in the market you were targeting. The value of this column is empty if the data is not available. For example, out of estimated 59,000 impressions that occurred on this day in your targeted market, you got only about 2,300, or 3%. If you try to include this column with *Hourly* or *HourOfDay* aggregation the service will return code *2053*. If you include this column, then you may not include restricted attributes such as [TopVsOther](#topvsother) in the same report request. Likewise if you include any of the restricted attribute columns, then you must exclude this column. For more information, see [Column Restrictions](../guides/reports.md#columnrestrictions). Data for this column is typically updated 14-18 hours after the UTC day ends. For Microsoft Shopping Campaigns, this data is only available with the campaign and ad group performance reports.|
|<a name="language"></a>Language|The language of the country the ad is served in.<br/><br/>For possible values, see the Language column of [Ad Languages](../guides/ad-languages.md#adlanguage). The language display name will be provided in the report e.g. *English*.|
|<a name="localstorecode"></a>LocalStoreCode|An alphanumeric identifier defined by the merchant to uniquely identify each local store. |
|<a name="network"></a>Network|The combined search advertising marketplace made up of Bing, AOL, Yahoo, and partner sites. Use this data to make the best decision on network selection for your ad groups. The possible values include AOL search, Audience, Bing and Yahoo! search, Content, and Syndicated search partners.|
|<a name="offerlanguage"></a>OfferLanguage|The report will include a column that contains the language for the product offer. For possible values see [Ad Languages](../guides/ad-languages.md). The language display name will be provided in the report e.g. *English*.|
|<a name="partitiontype"></a>PartitionType|The product partition type.|
|<a name="productgroup"></a>ProductGroup|The forward slash ("/") delimited list of product conditions, reported as Operand = Attribute. The attribute values are not surrounded by "" (double quotes). The category level is appended to the attribute values if applicable e.g., "(1st Level)", "(2nd Level)", etcetera. Here is an example: * \ Category=Animals & Pet Supplies(1st Level) \ Category=Pet Supplies(2nd Level) \ Category=Bird Supplies(3rd Level). The "*" (single asterisk) refers to a product group that matches everything else besides the other filters for the product group.|
|<a name="returnonadspend"></a>ReturnOnAdSpend|The return on ad spend (ROAS). The formula for calculating the ROAS is *(Revenue / Spend)*.|
|<a name="revenue"></a>Revenue|The revenue optionally reported by the advertiser as a result of conversions.<br/><br/>Available for accounts that are setup to use analytics with Microsoft Advertising Universal Event Tracking. For more information, see the [Track sales and other conversions](https://go.microsoft.com/fwlink/?LinkID=624771) help topic.|
|<a name="revenueperassist"></a>RevenuePerAssist|The revenue per assist. The formula for calculating the revenue per assist is *(Revenue / Assists)*.|
|<a name="revenueperconversion"></a>RevenuePerConversion|The revenue per conversion. The formula for calculating the revenue per conversion is *(Revenue / Conversions)*.|
|<a name="spend"></a>Spend|The cost per click (CPC) summed for each click.|
|<a name="timeperiod"></a>TimePeriod|The time period of each report row. You may not include this column if the *Aggregation* element of the request object is set to Summary. For more information, see [Time Period Column](../guides/reports.md#timeperiod).|
|<a name="topvsother"></a>TopVsOther|The report will include a column that indicates whether the ad impression appeared in a top position or elsewhere. The possible values include AOL search - Top, AOL search - Other, Audience network, Bing and Yahoo! search - Top, Bing and Yahoo! search - Other, Syndicated search partners - Top, Syndicated search partners - Other, Content network, and Unknown.|
|<a name="totalclicksonadelements"></a>TotalClicksOnAdElements|The number of clicks when this ad element was present in the ad copy, whether this or another ad element was clicked on.|
|<a name="trackingtemplate"></a>TrackingTemplate|The current tracking template of the criterion.|

## <a name="remarks"></a>Remarks
### <a name="requiredcolumns"></a>Required Columns
The report must include the following columns, and one or more of the performance statistics columns. For more information, see [Report Attributes and Performance Statistics](../guides/report-attributes-performance-statistics.md).

> [!NOTE]
> The TimePeriod column is required for all aggregation types except Summary.

|Column|
|----------|
|PartitionType|
|ProductGroup|
|TimePeriod|

## Requirements
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v12/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v12  

## Used By
[ProductPartitionPerformanceReportRequest](productpartitionperformancereportrequest.md)  
