---
title: AdExtensionDetailReportColumn Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the attributes and performance statistics columns that you can include in the AdExtensionDetailReportRequest.
---
# AdExtensionDetailReportColumn Value Set - Reporting
Defines the attributes and performance statistics columns that you can include in the [AdExtensionDetailReportRequest](adextensiondetailreportrequest.md).

The attribute columns that you include in a report can affect how the statistics are aggregated. In other words the number of rows increase by a factor of the unique attributes. For more information, see [Columns that Group the Data](../guides/reports.md#columnsdata).

For a list of columns that you must include, please see the [Required Columns](#requiredcolumns) section below.

To see how far back hourly, daily, weekly, monthly, yearly and summary aggregated data can be retrieved for a report, see [Report Data Retention Time Periods](../guides/report-data-retention-time-periods.md).

## Syntax
```xml
<xs:simpleType name="AdExtensionDetailReportColumn" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="AccountName" />
    <xs:enumeration value="AccountId" />
    <xs:enumeration value="TimePeriod" />
    <xs:enumeration value="CampaignName" />
    <xs:enumeration value="CampaignId" />
    <xs:enumeration value="AdGroupName" />
    <xs:enumeration value="AdGroupId" />
    <xs:enumeration value="AdTitle" />
    <xs:enumeration value="AdId" />
    <xs:enumeration value="AdExtensionType" />
    <xs:enumeration value="AdExtensionTypeId" />
    <xs:enumeration value="AdExtensionId" />
    <xs:enumeration value="AdExtensionVersion" />
    <xs:enumeration value="AdExtensionPropertyValue" />
    <xs:enumeration value="Impressions" />
    <xs:enumeration value="DeviceType" />
    <xs:enumeration value="DeviceOS" />
    <xs:enumeration value="Clicks" />
    <xs:enumeration value="Ctr" />
    <xs:enumeration value="Conversions" />
    <xs:enumeration value="CostPerConversion" />
    <xs:enumeration value="ConversionRate" />
    <xs:enumeration value="Spend" />
    <xs:enumeration value="AverageCpc" />
    <xs:enumeration value="BidMatchType" />
    <xs:enumeration value="DeliveredMatchType" />
    <xs:enumeration value="Network" />
    <xs:enumeration value="TopVsOther" />
    <xs:enumeration value="Assists" />
    <xs:enumeration value="Revenue" />
    <xs:enumeration value="ReturnOnAdSpend" />
    <xs:enumeration value="CostPerAssist" />
    <xs:enumeration value="RevenuePerConversion" />
    <xs:enumeration value="RevenuePerAssist" />
    <xs:enumeration value="AccountStatus" />
    <xs:enumeration value="CampaignStatus" />
    <xs:enumeration value="AdGroupStatus" />
    <xs:enumeration value="AdStatus" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="accountid"></a>AccountId|The Microsoft Advertising assigned identifier of an account.|
|<a name="accountname"></a>AccountName|The account name.|
|<a name="accountstatus"></a>AccountStatus|The account status.|
|<a name="adextensionid"></a>AdExtensionId|The Microsoft Advertising assigned identifier of an ad extension.|
|<a name="adextensionpropertyvalue"></a>AdExtensionPropertyValue|The human readable ad extension property value. For this report only one property is available for each type of ad extension. The following are the possible property values corresponding to each *AdExtensionTypeId*:<br/><br/>If  the *AdExtensionTypeId* is 10, this *AdExtensionPropertyValue* is the display text of a sitelink ad extension.<br/><br/>If  the *AdExtensionTypeId* is 11, this *AdExtensionPropertyValue* is the company name of a location ad extension.<br/><br/>If  the *AdExtensionTypeId* is 12 or 14, this *AdExtensionPropertyValue* is the phone number of a call ad extension.|
|<a name="adextensiontype"></a>AdExtensionType|The type name that corresponds to the *AdExtensionTypeId* column.|
|<a name="adextensiontypeid"></a>AdExtensionTypeId|The system identifier that corresponds to the *AdExtensionType* column. The supported identifiers are 10, 11, and 12.|
|<a name="adextensionversion"></a>AdExtensionVersion|The version attribute of an ad extension.|
|<a name="adgroupid"></a>AdGroupId|The Microsoft Advertising assigned identifier of an ad group.|
|<a name="adgroupname"></a>AdGroupName|The ad group name.|
|<a name="adgroupstatus"></a>AdGroupStatus|The ad group status.|
|<a name="adid"></a>AdId|The Microsoft Advertising assigned identifier of an ad.|
|<a name="adstatus"></a>AdStatus|The ad status.|
|<a name="adtitle"></a>AdTitle|The ad title.|
|<a name="assists"></a>Assists|The number of conversions from other ads within the same account that were preceded by one or more clicks from this ad. An ad is considered to have assisted the conversion if it was clicked before the most recently clicked ad that was credited with the conversion. Additionally, the click corresponding to the assist must occur  within the conversion period of the goal.|
|<a name="averagecpc"></a>AverageCpc|The average cost per click (CPC). The total cost of all clicks on an ad divided by the number of clicks. This is the average amount you're actually charged each time your ad is clicked. For example, if you paid a total of 48.35 for 300 clicks, your average CPC is 0.16. The formula for calculating the average CPC is *(Spend /Clicks)*.|
|<a name="bidmatchtype"></a>BidMatchType|The keyword bid match type. This can be different from the *DeliveredMatchType* column, for example if you bid on a broad match and the search term was an exact match. For more information, see [Budget and Bid Strategies](../guides/budget-bid-strategies.md). The possible values are *Broad*, *Exact*, *Phrase*, and *Unknown*.|
|<a name="campaignid"></a>CampaignId|The Microsoft Advertising assigned identifier of a campaign.|
|<a name="campaignname"></a>CampaignName|The campaign name.|
|<a name="campaignstatus"></a>CampaignStatus|The campaign status.|
|<a name="clicks"></a>Clicks|Clicks are what you pay for. Clicks typically include a customer clicking an ad on a search results page or on a website on the search network. Clicks can also come from other sources (for example, spiders, robots, and test servers). For more information, see [Microsoft Advertising click measurement: description of methodology](https://about.ads.microsoft.com/en-us/resources/policies/microsoft-advertising-click-measurement-description-of-methodology).|
|<a name="conversionrate"></a>ConversionRate|The conversion rate as a percentage. The number of conversions, divided by the total number of clicks. For example, if the ads in your campaign got 300 clicks and four conversions, the conversion rate is 1.33 (%). The formula for calculating the conversion rate is *(Conversions / Clicks) x 100*.|
|<a name="conversions"></a>Conversions|The number of conversions. A conversion is the completion of an action by a customer after viewing your ad. The action could be purchasing your product, registering for your webinar, joining an organization, or whatever you consider your goal and best measure of the ad's success.|
|<a name="costperassist"></a>CostPerAssist|The cost per assist. The formula for calculating the cost per assist is *(Spend / Assists)*.|
|<a name="costperconversion"></a>CostPerConversion|The cost per conversion. The formula for calculating the cost per conversion is *(Spend / Conversions)*. Only ads in campaigns that enable conversion tracking contribute to the conversion number, so unless all campaigns in the account enable conversion tracking, the number will not be accurate.|
|<a name="ctr"></a>Ctr|The click-through rate (CTR) is the number of times an ad was clicked, divided by the number of times the ad was shown (impressions). For example, if your ads got 50 clicks given 2,348 impressions, your CTR is 2.13 (%). The formula for calculating CTR is *(Clicks / Impressions) x 100*.|
|<a name="deliveredmatchtype"></a>DeliveredMatchType|The match type used to deliver an ad. This can be different from the *BidMatchType* column, for example if you bid on a broad match and the search term was an exact match. For more information, see [Budget and Bid Strategies](../guides/budget-bid-strategies.md). The possible values are *Broad*, *Exact*, *Phrase*, and *Unknown*.|
|<a name="deviceos"></a>DeviceOS|The operating system of the device reported in the *DeviceType* column. The possible values include *Android*, *Blackberry*, *iOS*, *Other*, *Unknown*, and *Windows*. If the operating system of the device cannot be determined or is not one of the operating systems that you can target, the value in this column will be *Unknown*.|
|<a name="devicetype"></a>DeviceType|The device name attribute of a device OS target bid. The type of device which showed ads. The possible values include *Computer*, *Smartphone*, *Tablet*, and *Unknown*.|
|<a name="impressions"></a>Impressions|The number of times an ad has been displayed on search results pages. Without impressions there are no clicks or conversions.|
|<a name="network"></a>Network|The combined search advertising marketplace made up of Bing, AOL, Yahoo, and partner sites. Use this data to make the best decision on network selection for your ad groups. The possible values include AOL search, Audience, Bing and Yahoo! search, Content, and Syndicated search partners.|
|<a name="returnonadspend"></a>ReturnOnAdSpend|The return on ad spend (ROAS). The formula for calculating the ROAS is *(Revenue / Spend)*.|
|<a name="revenue"></a>Revenue|The revenue optionally reported by the advertiser as a result of conversions.<br/><br/>Available for accounts that are setup to use analytics with Microsoft Advertising Universal Event Tracking. For more information, see the [Track sales and other conversions](https://go.microsoft.com/fwlink/?LinkID=624771) help topic.|
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
|AdExtensionId|
|AdExtensionPropertyValue|
|AdExtensionType|
|AdExtensionTypeId|
|Clicks|
|Ctr|
|Impressions|
|TimePeriod|

## Requirements
Service: [ReportingService.svc v13](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v13/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v13  

## Used By
[AdExtensionDetailReportRequest](adextensiondetailreportrequest.md)  
