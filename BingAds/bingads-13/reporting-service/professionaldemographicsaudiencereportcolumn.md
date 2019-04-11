---
title: ProfessionalDemographicsAudienceReportColumn Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the attributes and performance statistics columns that you can include in the ProfessionalDemographicsAudienceReportRequest.
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# ProfessionalDemographicsAudienceReportColumn Value Set - Reporting
Defines the attributes and performance statistics columns that you can include in the [ProfessionalDemographicsAudienceReportRequest](professionaldemographicsaudiencereportrequest.md).

The attribute columns that you include in a report can affect how the statistics are aggregated. In other words the number of rows increase by a factor of the unique attributes. For more information, see [Columns that Group the Data](../guides/reports.md#columnsdata).

For a list of columns that you must include, please see the [Required Columns](#requiredcolumns) section below.

To see how far back hourly, daily, weekly, monthly, yearly and summary aggregated data can be retrieved for a report, see [Report Data Retention Time Periods](../guides/report-data-retention-time-periods.md).

## Syntax
```xml
<xs:simpleType name="ProfessionalDemographicsAudienceReportColumn" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="AccountName" />
    <xs:enumeration value="AccountNumber" />
    <xs:enumeration value="AccountId" />
    <xs:enumeration value="TimePeriod" />
    <xs:enumeration value="CampaignName" />
    <xs:enumeration value="CampaignId" />
    <xs:enumeration value="AdGroupName" />
    <xs:enumeration value="AdGroupId" />
    <xs:enumeration value="CompanyName" />
    <xs:enumeration value="IndustryName" />
    <xs:enumeration value="JobFunctionName" />
    <xs:enumeration value="AdDistribution" />
    <xs:enumeration value="Impressions" />
    <xs:enumeration value="Clicks" />
    <xs:enumeration value="Spend" />
    <xs:enumeration value="Conversions" />
    <xs:enumeration value="Language" />
    <xs:enumeration value="Assists" />
    <xs:enumeration value="Revenue" />
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
|<a name="addistribution"></a>AdDistribution|The network where you want your ads to show.|
|<a name="adgroupid"></a>AdGroupId|The Bing Ads assigned identifier of an ad group.|
|<a name="adgroupname"></a>AdGroupName|The ad group name.|
|<a name="adgroupstatus"></a>AdGroupStatus|The ad group status.|
|<a name="assists"></a>Assists|The number of times an entity (an account, campaign, ad group, or keyword, for example) contributed to a conversion that is associated with a different entity.<br/>A report on this data shows you how often one keyword assists a conversion on another keyword. This helps you identify which campaigns are dependent on assists for their conversion value.|
|<a name="campaignid"></a>CampaignId|The Bing Ads assigned identifier of a campaign.|
|<a name="campaignname"></a>CampaignName|The campaign name.|
|<a name="campaignstatus"></a>CampaignStatus|The campaign status.|
|<a name="clicks"></a>Clicks|Clicks are what you pay for.<br/>Clicks typically include a customer clicking an ad on a search results page or on a website on the search network. Clicks can also come from other sources (for example, spiders, robots, and test servers).<br/>You pay for clicks on standard-quality clicks, not on low-quality or invalid clicks.|
|<a name="companyname"></a>CompanyName|The name of the company (according to LinkedIn) of the person who viewed the ad.|
|<a name="conversions"></a>Conversions|A conversion is a click that results in a sale or another measure of success. Conversions are measured by adding a small bit of code to your website pages so that a visitor's progress through your site can be tracked.<br/>Knowing how people interact with your website can give you valuable feedback on improving your website's organization and content.|
|<a name="impressions"></a>Impressions|The number of times an ad has been displayed on search results pages or other sites on the Audience Network.<br/>Regardless of whether you are driving customers to your website, tracking conversions, or just trying to get your message out, you want to track the number of times your ad is shown.<br/>Run the share of voice report to get an estimate of how many more impressions you could be getting.|
|<a name="industryname"></a>IndustryName|The name of the industry (according to LinkedIn) of the person who viewed the ad.|
|<a name="jobfunctionname"></a>JobFunctionName|The name of the job function (according to LinkedIn) of the person who viewed the ad.|
|<a name="language"></a>Language|This is the language of the country the ad is served in.|
|<a name="revenue"></a>Revenue|The revenue optionally reported by the advertiser as a result of conversions.<br/><br/>Available for accounts that are setup to use analytics with Bing Ads Universal Event Tracking. For more information, see the [Track sales and other conversions](https://go.microsoft.com/fwlink/?LinkID=624771) help topic.|
|<a name="spend"></a>Spend|The sum of your cost-per-click (CPC) charges for your ads and keywords.<br/>Spend helps you keep track of your budget.|
|<a name="timeperiod"></a>TimePeriod|The time period of each report row. You may not include this column if the *Aggregation* element of the request object is set to Summary. If you include the *TimePeriod* column, the column label in the downloaded report depends on the aggregation level that you specify in the report request. For more information, see [Time Period Column](../guides/reports.md#timeperiod).|

## <a name="remarks"></a>Remarks
### <a name="requiredcolumns"></a>Required Columns
The report must include the following columns, and one or more of the performance statistics columns. For more information, see [Report Attributes and Performance Statistics](../guides/report-attributes-performance-statistics.md).

> [!NOTE]
> The TimePeriod column is required for all aggregation types except Summary.

|Column|
|----------|
|AccountName|
|AdGroupName|
|CompanyName|
|IndustryName|
|JobFunctionName|
|TimePeriod|

## Requirements
Service: [ReportingService.svc v13](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v13/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v13  

## Used By
[ProfessionalDemographicsAudienceReportRequest](professionaldemographicsaudiencereportrequest.md)  
