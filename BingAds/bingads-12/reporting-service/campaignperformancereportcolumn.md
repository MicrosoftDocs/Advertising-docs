---
title: CampaignPerformanceReportColumn Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the attributes and performance statistics columns that you can include in the CampaignPerformanceReportRequest.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# CampaignPerformanceReportColumn Value Set - Reporting
Defines the attributes and performance statistics columns that you can include in the [CampaignPerformanceReportRequest](campaignperformancereportrequest.md).

The attribute columns that you include in a report can affect how the statistics are aggregated. In other words the number of rows increase by a factor of the unique attributes. For more information, see [Columns that Group the Data](../guides/reports.md#columnsdata).

For a list of columns that you must include, please see the [Required Columns](#requiredcolumns) section below.

To see how far back hourly, daily, weekly, monthly, yearly and summary aggregated data can be retrieved for a report, see [Report Data Retention Time Periods](../guides/report-data-retention-time-periods.md).

## Syntax
```xml
<xs:simpleType name="CampaignPerformanceReportColumn" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="AccountName" />
    <xs:enumeration value="AccountNumber" />
    <xs:enumeration value="AccountId" />
    <xs:enumeration value="TimePeriod" />
    <xs:enumeration value="Status" />
    <xs:enumeration value="CampaignName" />
    <xs:enumeration value="CampaignId" />
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
    <xs:enumeration value="ImpressionLostToRankPercent" />
    <xs:enumeration value="QualityScore" />
    <xs:enumeration value="ExpectedCtr" />
    <xs:enumeration value="AdRelevance" />
    <xs:enumeration value="LandingPageExperience" />
    <xs:enumeration value="HistoricQualityScore" />
    <xs:enumeration value="HistoricExpectedCtr" />
    <xs:enumeration value="HistoricAdRelevance" />
    <xs:enumeration value="HistoricLandingPageExperience" />
    <xs:enumeration value="ImpressionLostToBidPercent" />
    <xs:enumeration value="ImpressionLostToAdRelevancePercent" />
    <xs:enumeration value="ImpressionLostToExpectedCtrPercent" />
    <xs:enumeration value="PhoneImpressions" />
    <xs:enumeration value="PhoneCalls" />
    <xs:enumeration value="ManualCalls" />
    <xs:enumeration value="ClickCalls" />
    <xs:enumeration value="Ptr" />
    <xs:enumeration value="AverageCpp" />
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
    <xs:enumeration value="TrackingTemplate" />
    <xs:enumeration value="CustomParameters" />
    <xs:enumeration value="AccountStatus" />
    <xs:enumeration value="BudgetName" />
    <xs:enumeration value="BudgetStatus" />
    <xs:enumeration value="BudgetAssociationStatus" />
    <xs:enumeration value="LowQualityGeneralClicks" />
    <xs:enumeration value="LowQualitySophisticatedClicks" />
    <xs:enumeration value="CampaignLabels" />
    <xs:enumeration value="ExactMatchImpressionSharePercent" />
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
|<a name="adrelevance"></a>AdRelevance|How closely related your ads is to the customer's search query or other input. It tells you how relevant your ad and landing page are to potential customers.A score of 3 is Above Average; a score of 2 is Average; and a score of 1 is considered Below Average.If you specify a time period that spans multiple days, the score will be the same for each day in the time period, and the value is the most recent calculated score. Data for this column is typically updated 14-18 hours after the UTC day ends.|
|<a name="assists"></a>Assists|The number of conversions from other ads within the same account that were preceded by one or more clicks from this ad.An ad is considered to have assisted the conversion if it was clicked before the most recently clicked ad that was credited with the conversion. Additionally, the click corresponding to the assist must occur  within the conversion period of the goal.|
|<a name="averagecpc"></a>AverageCpc|The average cost per click (CPC). The total cost of all clicks on an ad divided by the number of clicks. This is the average amount you're actually charged each time your ad is clicked. For example, if you paid a total of 48.35 for 300 clicks, your average CPC is 0.16.The formula for calculating the average CPC is *(Spend /Clicks)*.|
|<a name="averagecpp"></a>AverageCpp|The average cost per phone call (CPP). This column is applicable solely for manual calls, and does not include clicks-to-call data.|
|<a name="averageposition"></a>AveragePosition|The average position of the ad on a webpage.|
|<a name="bidmatchtype"></a>BidMatchType|The keyword bid match type. This can be different from the *DeliveredMatchType* column, for example if you bid on a broad match and the search term was an exact match. For more information, see [Budget and Bid Strategies](../guides/budget-bid-strategies.md).The possible values are *Broad*, *Exact*, *Phrase*, and *Unknown*.|
|<a name="budgetassociationstatus"></a>BudgetAssociationStatus|Indicates whether or not the campaign is currently spending from the budget mentioned in the *BudgetName* column. The possible values are *Current* and *Ended*.|
|<a name="budgetname"></a>BudgetName|The name of the budget. <br/><br/> This column will be empty for unshared budgets.|
|<a name="budgetstatus"></a>BudgetStatus|The budget status. The possible values are *Active* and *Deleted*.<br/><br/> This column will be empty for unshared budgets.|
|<a name="campaignid"></a>CampaignId|The Bing Ads assigned identifier of a campaign.|
|<a name="campaignlabels"></a>CampaignLabels|The labels applied to the campaign.<br/><br/>Labels are delimited by a semicolon (;) in the report download.|
|<a name="campaignname"></a>CampaignName|The campaign name.|
|<a name="clickcalls"></a>ClickCalls|The number of phone calls initiated by clicks.|
|<a name="clicks"></a>Clicks|Clicks are what you pay for. Clicks typically include a customer clicking an ad on a search results page or on a website on the search network. Clicks can also come from other sources (for example, spiders, robots, and test servers). For more information, see [Bing Ads click measurement: description of methodology](https://advertise.bingads.microsoft.com/resources/policies/bing-ads-click-measurement-description-of-methodology).|
|<a name="conversionrate"></a>ConversionRate|The conversion rate as a percentage. The number of conversions, divided by the total number of clicks. For example, if the ads in your campaign got 300 clicks and four conversions, the conversion rate is 1.33 (%).The formula for calculating the conversion rate is *(Conversions / Clicks) x 100*.|
|<a name="conversions"></a>Conversions|The number of conversions. A conversion is the completion of an action by a customer after viewing your ad. The action could be purchasing your product, registering for your webinar, joining an organization, or whatever you consider your goal and best measure of the ad's success.|
|<a name="costperassist"></a>CostPerAssist|The cost per assist. The formula for calculating the cost per assist is *(Spend / Assists)*.|
|<a name="costperconversion"></a>CostPerConversion|The cost per conversion. The formula for calculating the cost per conversion is *(Spend / Conversions)*.Only ads in campaigns that enable conversion tracking contribute to the conversion number, so unless all campaigns in the account enable conversion tracking, the number will not be accurate.|
|<a name="ctr"></a>Ctr|The click-through rate (CTR) is the number of times an ad was clicked, divided by the number of times the ad was shown (impressions). For example, if your ads got 50 clicks given 2,348 impressions, your CTR is 2.13 (%).The formula for calculating CTR is *(Clicks / Impressions) x 100*.|
|<a name="currencycode"></a>CurrencyCode|The account currency type.For possible values, see [Currencies](../guides/currencies.md).|
|<a name="customparameters"></a>CustomParameters|The current set of custom parameters for the campaign.<br /><br />Each custom parameter is a key and value pair. The list of custom parameters is semicolon-delimited and each key is enclosed by braces and a leading underscore, for example *{_key1}=value1;{_key2}=value2*.|
|<a name="deliveredmatchtype"></a>DeliveredMatchType|The match type used to deliver an ad. This can be different from the *BidMatchType* column, for example if you bid on a broad match and the search term was an exact match. For more information, see [Budget and Bid Strategies](../guides/budget-bid-strategies.md).The possible values are *Broad*, *Exact*, *Phrase*, and *Unknown*.|
|<a name="deviceos"></a>DeviceOS|The operating system of the device reported in the *DeviceType* column.The possible values include *Android*, *Blackberry*, *iOS*, *Other*, *Unknown*, and *Windows*.If the operating system of the device cannot be determined or is not one of the operating systems that you can target, the value in this column will be *Unknown*.|
|<a name="devicetype"></a>DeviceType|The device name attribute of a device OS target bid. The type of device which showed ads.The possible values include *Computer*, *Smartphone*, *Tablet*, and *Unknown*.|
|<a name="exactmatchimpressionsharepercent"></a>ExactMatchImpressionSharePercent|The estimated percentage of impressions that your campaign received for searches that exactly matched your keyword, out of the total available exact match impressions you were eligible to receive.<br/><br/>Reports on exact match impression share highlight how your keywords perform only on those searches that exactly match your keywords. Use this data together with impression share to diagnose your non-exact match keywords, and make changes to be more competitive and gain more impressions.|
|<a name="expectedctr"></a>ExpectedCtr|How well your keyword competes against other keywords targeting the same traffic. Ads that are relevant to searchers' queries or other input are more likely to have a higher click-through rate. This metric tells you if a keyword is underperforming and causing a loss in impression share, so you can make keyword changes or remove ads altogether.A score of 3 is Above Average; a score of 2 is Average; and a score of 1 is considered Below Average.If you specify a time period that spans multiple days, the score will be the same for each day in the time period, and the value is the most recent calculated score. Data for this column is typically updated 14-18 hours after the UTC day ends.|
|<a name="historicadrelevance"></a>HistoricAdRelevance|Historic average of ad relevance scores back as far as 18 months from the current date. This score may vary from the score in the *AdRelevance* column, which is the current score and same value for each day in the time period.|
|<a name="historicexpectedctr"></a>HistoricExpectedCtr|Historic average of expected click-through rate scores going back as far as 18 months from the current date. This score may vary from the score in the *ExpectedCtr* column, which is the current score and same value for each day in the time period.The score for each row is the score that was calculated for expected CTR on that date. For example, if you specify a time period that spans three days, the historic expected CTR score for day one will be the expected CTR score calculated on day one, the historic expected CTR score for day two will be the expected CTR score calculated on day two, and so on.You may include this column only with Daily aggregation.|
|<a name="historiclandingpageexperience"></a>HistoricLandingPageExperience|Historic average of landing page experience scores back as far as 18 months from the current date. This score may vary from the score in the *LandingPageExperience* column, which is the current score and same value for each day in the time period.|
|<a name="historicqualityscore"></a>HistoricQualityScore|The historic quality score of the keyword. The historic quality score for each row is the value that was calculated for quality score on that date.Use the historic quality score to find out how the quality score may have changed over time. For example, if you specify a time period that spans three days, the historic quality score for day one will be the quality score calculated on day one, the historic quality score for day two will be the quality score calculated on day two, and so on.This score may vary from the score in the *QualityScore* column, which will be the same value for each day in the time period.You may include this column only with Daily aggregation.|
|<a name="impressionlosttoadrelevancepercent"></a>ImpressionLostToAdRelevancePercent|The percentage of impression share lost due to low ad relevance. The value of this column is empty if the data is not available. If you try to include this column with *Hourly* or *HourOfDay* aggregation the service will return code *2053*.  For reports that include impression share performance statistics columns you should not include restricted attributes such as *DeviceOS* in the same report request. Likewise if you include any of the restricted attribute columns, you should exclude all of the impression share performance statistics columns. For more information, see [Column Restrictions](../guides/reports.md#columnrestrictions). Data for this column is typically updated 14-18 hours after the UTC day ends. For Bing Shopping campaigns, this data is not available.|
|<a name="impressionlosttobidpercent"></a>ImpressionLostToBidPercent|The percentage of time your ads would have been displayed to users, but were not because your bid was too low or your bid and quality score was below minimum thresholds, which prevented you from entering the auction. The value of this column is empty if the data is not available. If you try to include this column with *Hourly* or *HourOfDay* aggregation the service will return code *2053*.  For reports that include impression share performance statistics columns you should not include restricted attributes such as *DeviceOS* in the same report request. Likewise if you include any of the restricted attribute columns, you should exclude all of the impression share performance statistics columns. For more information, see [Column Restrictions](../guides/reports.md#columnrestrictions). Data for this column is typically updated 14-18 hours after the UTC day ends. For Bing Shopping campaigns, this data is only available with the campaign and ad group performance reports.|
|<a name="impressionlosttobudgetpercent"></a>ImpressionLostToBudgetPercent|The estimated percentage of impressions your ad did not receive due to issues with your daily or monthly budget. The value of this column is empty if the data is not available. If you try to include this column with *Hourly* or *HourOfDay* aggregation the service will return code *2053*.  For reports that include impression share performance statistics columns you should not include restricted attributes such as *DeviceOS* in the same report request. Likewise if you include any of the restricted attribute columns, you should exclude all of the impression share performance statistics columns. For more information, see [Column Restrictions](../guides/reports.md#columnrestrictions). Data for this column is typically updated 14-18 hours after the UTC day ends. For Bing Shopping campaigns, this data is only available with the campaign and ad group performance reports.|
|<a name="impressionlosttoexpectedctrpercent"></a>ImpressionLostToExpectedCtrPercent|The percentage of impression share lost due to low expected click-through rate. If this is high, figure out what you can do to increase your CTR. The value of this column is empty if the data is not available. If you try to include this column with *Hourly* or *HourOfDay* aggregation the service will return code *2053*.  For reports that include impression share performance statistics columns you should not include restricted attributes such as *DeviceOS* in the same report request. Likewise if you include any of the restricted attribute columns, you should exclude all of the impression share performance statistics columns. For more information, see [Column Restrictions](../guides/reports.md#columnrestrictions). Data for this column is typically updated 14-18 hours after the UTC day ends. For Bing Shopping campaigns, this data is not available.|
|<a name="impressionlosttorankpercent"></a>ImpressionLostToRankPercent|The estimated percentage of impressions your ad did not receive due to issues with your ad ranking. The value of this column is empty if the data is not available. If you try to include this column with *Hourly* or *HourOfDay* aggregation the service will return code *2053*.  For reports that include impression share performance statistics columns you should not include restricted attributes such as *DeviceOS* in the same report request. Likewise if you include any of the restricted attribute columns, you should exclude all of the impression share performance statistics columns. For more information, see [Column Restrictions](../guides/reports.md#columnrestrictions). Data for this column is typically updated 14-18 hours after the UTC day ends. For Bing Shopping campaigns, this data is not available.|
|<a name="impressions"></a>Impressions|The number of times an ad has been displayed on search results pages. Without impressions there are no clicks or conversions.|
|<a name="impressionsharepercent"></a>ImpressionSharePercent|The estimated percentage of impressions, out of the total available impressions in the market you were targeting. The value of this column is empty if the data is not available.Example: Out of estimated 59,000 impressions that occurred on this day in your targeted market, you got only about 2,300, or 3%. If you try to include this column with *Hourly* or *HourOfDay* aggregation the service will return code *2053*.  For reports that include impression share performance statistics columns you should not include restricted attributes such as *DeviceOS* in the same report request. Likewise if you include any of the restricted attribute columns, you should exclude all of the impression share performance statistics columns. For more information, see [Column Restrictions](../guides/reports.md#columnrestrictions). Data for this column is typically updated 14-18 hours after the UTC day ends. For Bing Shopping campaigns, this data is only available with the campaign and ad group performance reports.|
|<a name="landingpageexperience"></a>LandingPageExperience|An aggregate quality assessment of all landing pages on your site. The landing page experience score measures whether your landing page is likely to provide a good experience to customers who click your ad and land on your website.A score of 3 is Above Average; a score of 2 is Average; and a score of 1 is considered Below Average.If you specify a time period that spans multiple days, the score will be the same for each day in the time period, and the value is the most recent calculated score. Data for this column is typically updated 14-18 hours after the UTC day ends.|
|<a name="lowqualityclicks"></a>LowQualityClicks|Clicks that exhibit a low likelihood of commercial intent. You are not billed for these clicks. For more information, see [Bing Ads click measurement: description of methodology](https://advertise.bingads.microsoft.com/resources/policies/bing-ads-click-measurement-description-of-methodology).|
|<a name="lowqualityclickspercent"></a>LowQualityClicksPercent|The low-quality clicks as a percentage.The formula for calculating the low quality clicks percentage is *(LowQualityClicks / Clicks) x 100*.|
|<a name="lowqualityconversionrate"></a>LowQualityConversionRate|The low-quality conversion rate as a percentage.The formula for calculating the conversion rate is *(LowQualityConversions / LowQualityClicks) x 100*.|
|<a name="lowqualityconversions"></a>LowQualityConversions|The number of conversions that originate from low-quality clicks.|
|<a name="lowqualitygeneralclicks"></a>LowQualityGeneralClicks|Clicks that are filtered by general methods, such as blacklists and activity-based detection, and that exhibit a low likelihood of commercial intent. You are not billed for these clicks. For more information, see [Bing Ads click measurement: description of methodology](https://advertise.bingads.microsoft.com/resources/policies/bing-ads-click-measurement-description-of-methodology).|
|<a name="lowqualityimpressions"></a>LowQualityImpressions|The number of impressions that result from low-quality keyword searches.|
|<a name="lowqualityimpressionspercent"></a>LowQualityImpressionsPercent|The low-quality impressions as a percentage.The formula for calculating the percentage is *(LowQualityImpressions / Impressions) x 100*.|
|<a name="lowqualitysophisticatedclicks"></a>LowQualitySophisticatedClicks|Invalid clicks that use sophisticated means to appear valid. You are not billed for these clicks. For more information, see [Bing Ads click measurement: description of methodology](https://advertise.bingads.microsoft.com/resources/policies/bing-ads-click-measurement-description-of-methodology).|
|<a name="manualcalls"></a>ManualCalls|The number of calls dialed manually from any device to the tracked phone number. This column is applicable solely for manual calls, and does not include clicks-to-call data.|
|<a name="network"></a>Network|The current network setting of an ad group. The possible values include AOL search, Bing and Yahoo! search, Content, and Syndicated search partners.|
|<a name="phonecalls"></a>PhoneCalls|The number of total calls to the tracked phone number that showed with your ad.The formula for calculating the phone calls is *ManualCalls + ClickCalls*.|
|<a name="phoneimpressions"></a>PhoneImpressions|The number of times your tracked number was shown on all devices.|
|<a name="ptr"></a>Ptr|The phone-through rate (Ptr).The formula for calculating the Ptr is *(PhoneCalls / PhoneImpressions) x 100*.|
|<a name="qualityscore"></a>QualityScore|The numeric score shows you how competitive your ads are in the marketplace by measuring how relevant your keywords and landing pages are to customers' search terms. The quality score is calculated by Bing Ads using the *ExpectedCtr*, *AdRelevance*, and *LandingPageExperience* sub scores. If available, the quality score can range from a low of 1 to a high of 10.Quality score is based on the last rolling 30 days for the owned and operated search traffic. A quality score can be assigned without any impressions, in the case where a keyword bid did not win any auctions. Traffic for syndicated networks do not affect quality score. The value in the report will be blank if the score was not computed. This can occur if there have been no impressions for the keyword for 30 days or more. Quality score is typically updated 14-18 hours after the UTC day ends. Keywords in all time zones will be assigned a quality score for the corresponding UTC day.If you run the report multiple times in a day, the quality score values could change from report to report based on when you run the report relative to when the scores are calculated.If you specify a time period that spans multiple days, the quality score is the current and most recently calculated score and will be reported as the same for each day in the time period. Use the historic quality score to find out how quality score may have changed over time. Historical quality score is a daily snapshot of the rolling quality score.  For more information on historic quality score, see the *HistoricQualityScore* column.|
|<a name="returnonadspend"></a>ReturnOnAdSpend|The return on ad spend (ROAS).The formula for calculating the ROAS is *(Revenue / Spend)*.|
|<a name="revenue"></a>Revenue|The revenue optionally reported by the advertiser as a result of conversions. Corresponds to the optional *revenue* parameter of a Bing Ads campaign analytics tracking script.|
|<a name="revenueperassist"></a>RevenuePerAssist|The revenue per assist.The formula for calculating the revenue per assist is *(Revenue / Assists)*.|
|<a name="revenueperconversion"></a>RevenuePerConversion|The revenue per conversion.The formula for calculating the revenue per conversion is *(Revenue / Conversions)*.|
|<a name="spend"></a>Spend|The cost per click (CPC) summed for each click.|
|<a name="status"></a>Status|The current entity  status.|
|<a name="timeperiod"></a>TimePeriod|The time period of each report row. You may not include this column if the *Aggregation* element of the request object is set to Summary. For more information, see [Time Period Column](../guides/reports.md#timeperiod).|
|<a name="topvsother"></a>TopVsOther|The report will include a column that indicates whether the ad impression appeared in a top position or elsewhere. The possible values include AOL search - Top, AOL search - Other, Bing and Yahoo! search - Top, Bing and Yahoo! search - Other, Syndicated search partners - Top, Syndicated search partners - Other, Content network, and Unknown.|
|<a name="trackingtemplate"></a>TrackingTemplate|The current tracking template for the campaign.|

## <a name="remarks"></a>Remarks
### <a name="requiredcolumns"></a>Required Columns
The report must include the following columns, and one or more of the performance statistics columns. For more information, see [Report Attributes and Performance Statistics](../guides/report-attributes-performance-statistics.md).

> [!NOTE]
> The TimePeriod column is required for all aggregation types except Summary.

|Column|
|----------|
|TimePeriod|

## Requirements
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v12/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v12  

## Used By
[CampaignPerformanceReportRequest](campaignperformancereportrequest.md)  
