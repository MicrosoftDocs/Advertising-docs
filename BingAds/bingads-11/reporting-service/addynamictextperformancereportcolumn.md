---
title: AdDynamicTextPerformanceReportColumn Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the attributes and performance statistics columns that you can include in the AdDynamicTextPerformanceReportRequest Data Object.
---
# AdDynamicTextPerformanceReportColumn Value Set - Reporting
Defines the attributes and performance statistics columns that you can include in the [AdDynamicTextPerformanceReportRequest Data Object](../reporting-service/addynamictextperformancereportrequest.md).

The attribute columns that you include in a report can affect how the statistics are aggregated. In other words the number of rows increase by a factor of the unique attributes. For more information, see [Columns that Group the Data](~/guides/reports.md#columnsdata).

For a list of columns that you must include, please see the [Required Columns](#requiredcolumns) section below.

To see how far back hourly, daily, weekly, monthly, yearly and summary aggregated data can be retrieved for a report, see [Report Data Retention Time Periods](~/guides/report-data-retention-time-periods.md).

## Syntax
```xml
<xs:simpleType name="AdDynamicTextPerformanceReportColumn" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="AccountName" />
    <xs:enumeration value="AccountId" />
    <xs:enumeration value="AccountNumber" />
    <xs:enumeration value="TimePeriod" />
    <xs:enumeration value="AdGroupName" />
    <xs:enumeration value="AdGroupId" />
    <xs:enumeration value="Keyword" />
    <xs:enumeration value="AdId" />
    <xs:enumeration value="AdTitle" />
    <xs:enumeration value="AdType" />
    <xs:enumeration value="DestinationUrl" />
    <xs:enumeration value="Param1" />
    <xs:enumeration value="Param2" />
    <xs:enumeration value="Param3" />
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
    <xs:enumeration value="DeviceType" />
    <xs:enumeration value="Language" />
    <xs:enumeration value="AccountStatus" />
    <xs:enumeration value="AdGroupStatus" />
    <xs:enumeration value="AdStatus" />
    <xs:enumeration value="KeywordStatus" />
    <xs:enumeration value="TitlePart1" />
    <xs:enumeration value="TitlePart2" />
    <xs:enumeration value="Path1" />
    <xs:enumeration value="Path2" />
    <xs:enumeration value="FinalURL" />
    <xs:enumeration value="FinalMobileURL" />
    <xs:enumeration value="FinalAppURL" />
    <xs:enumeration value="AdDescription" />
    <xs:enumeration value="AdLabels" />
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
|<a name="addescription"></a>AdDescription|The text attribute of an ad.|
|<a name="addistribution"></a>AdDistribution|The ad distribution attribute of an ad group.|
|<a name="adgroupid"></a>AdGroupId|The Bing Ads assigned identifier of an ad group.|
|<a name="adgroupname"></a>AdGroupName|The ad group name.|
|<a name="adgroupstatus"></a>AdGroupStatus|The ad group status.|
|<a name="adid"></a>AdId|The Bing Ads assigned identifier of an ad.|
|<a name="adlabels"></a>AdLabels|The labels applied to the ad.<br/><br/>Labels are delimited by a semicolon (;) in the report download.|
|<a name="adstatus"></a>AdStatus|The ad status.|
|<a name="adtitle"></a>AdTitle|The ad title.|
|<a name="adtype"></a>AdType|The ad type.|
|<a name="averagecpc"></a>AverageCpc|The average cost per click (CPC). The total cost of all clicks on an ad divided by the number of clicks. This is the average amount you're actually charged each time your ad is clicked. For example, if you paid a total of 48.35 for 300 clicks, your average CPC is 0.16.The formula for calculating the average CPC is *(Spend /Clicks)*.|
|<a name="averageposition"></a>AveragePosition|The average position of the ad on a webpage.|
|<a name="clicks"></a>Clicks|Clicks are what you pay for. Clicks typically include a customer clicking an ad on a search results page or on a website on the search network. Clicks can also come from other sources (for example, spiders, robots, and test servers). For more information, see [Bing Ads click measurement: description of methodology](https://advertise.bingads.microsoft.com/resources/policies/bing-ads-click-measurement-description-of-methodology).|
|<a name="conversionrate"></a>ConversionRate|The conversion rate as a percentage. The number of conversions, divided by the total number of clicks. For example, if the ads in your campaign got 300 clicks and four conversions, the conversion rate is 1.33 (%).The formula for calculating the conversion rate is *(Conversions / Clicks) x 100*.|
|<a name="conversions"></a>Conversions|The number of conversions. A conversion is the completion of an action by a customer after viewing your ad. The action could be purchasing your product, registering for your webinar, joining an organization, or whatever you consider your goal and best measure of the ad's success.|
|<a name="costperconversion"></a>CostPerConversion|The cost per conversion. The formula for calculating the cost per conversion is *(Spend / Conversions)*.Only ads in campaigns that enable conversion tracking contribute to the conversion number, so unless all campaigns in the account enable conversion tracking, the number will not be accurate.|
|<a name="ctr"></a>Ctr|The click-through rate (CTR) is the number of times an ad was clicked, divided by the number of times the ad was shown (impressions). For example, if your ads got 50 clicks given 2,348 impressions, your CTR is 2.13 (%).The formula for calculating CTR is *(Clicks / Impressions) x 100*.|
|<a name="currencycode"></a>CurrencyCode|The account currency type.For possible values, see [Currencies](~/guides/currencies.md).|
|<a name="destinationurl"></a>DestinationUrl|The destination URL attribute of the ad, keyword, or ad group criterion.If the destination URL contains dynamic text substitution parameters (for example, {param1}), the report will contain the URL after substitution occurs.|
|<a name="devicetype"></a>DeviceType|The device name attribute of a device OS target bid. The type of device which showed ads.The possible values include *Computer*, *Smartphone*, *Tablet*, and *Unknown*.|
|<a name="finalappurl"></a>FinalAppURL|Reserved for future use.|
|<a name="finalmobileurl"></a>FinalMobileURL|The Final Mobile URL of the ad, keyword, or criterion.<br /><br />Only the first URL in the list is reported. If the URL contains dynamic text substitution parameters (for example, {param1}), the report will contain the URL before substitution.|
|<a name="finalurl"></a>FinalURL|The Final URL of the ad, keyword, or criterion.<br /><br />Only the first URL in the list is reported. If the URL contains dynamic text substitution parameters (for example, {param1}), the report will contain the URL before substitution.|
|<a name="impressions"></a>Impressions|The number of times an ad has been displayed on search results pages. Without impressions there are no clicks or conversions.|
|<a name="keyword"></a>Keyword|The keyword text.|
|<a name="keywordstatus"></a>KeywordStatus|The keyword status.|
|<a name="language"></a>Language|The language of the country the ad is served in.<br/><br/>For possible values, see the Language column of [Ad Languages](~/guides/ad-languages.md#adlanguage). The language display name will be provided in the report e.g. *English*.|
|<a name="param1"></a>Param1|The first dynamic substitution parameter (Param1) of a keyword or biddable ad group criterion.|
|<a name="param2"></a>Param2|The second dynamic substitution parameter (Param2) of a keyword or biddable ad group criterion.|
|<a name="param3"></a>Param3|The third dynamic substitution parameter (Param3) of a keyword or biddable ad group criterion.|
|<a name="path1"></a>Path1|The path 1 attribute of an ad.|
|<a name="path2"></a>Path2|The path 2 attribute of an ad.|
|<a name="spend"></a>Spend|The cost per click (CPC) summed for each click.|
|<a name="timeperiod"></a>TimePeriod|The time period of each report row. You may not include this column if the *Aggregation* element of the request object is set to Summary. If you include the *TimePeriod* column, the column label in the downloaded report depends on the aggregation level that you specify in the report request. For more information, see [Time Period Column](~/guides/reports.md#timeperiod).|
|<a name="titlepart1"></a>TitlePart1|The title part 1 attribute of an ad.|
|<a name="titlepart2"></a>TitlePart2|The title part 2 attribute of an ad.|

## <a name="remarks"></a>Remarks
### <a name="requiredcolumns"></a>Required Columns
The report must include the following columns, and one or more of the performance statistics columns. For more information, see [Report Attributes and Performance Statistics](~/guides/report-attributes-performance-statistics.md).

> [!NOTE]
> The TimePeriod column is required for all aggregation types except Summary.

|Column|
|----------|
|AdTitle|
|DestinationUrl|
|Param1|
|Param2|
|Param3|
|TimePeriod|

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v11  

## Used By
[AdDynamicTextPerformanceReportRequest](addynamictextperformancereportrequest.md)  
