---
title: "Bing Ads API Release Notes"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Get information about changes to Bing Ads API Version 13 by month. 
---
# Bing Ads API Release Notes
See below for information about changes to Bing Ads API Version 13 by month. 

## <a name="october2019"></a>October 2019
See below for Bing Ads API updates during this calendar month. 

- [Include View Through Conversions](#includeviewthroughconversions-october2019)  
- [Profile Expansion Enabled](#profileexpansionenabled-october2019)  

### <a name="includeviewthroughconversions-october2019"></a>Include View Through Conversions
View-through conversions are conversions that people make after they have seen your ad, even though they did not click the ad. 

If you are in the feature pilot ([GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) returns 616) this feature is enabled by default, meaning that the values in the "All" conversions columns of your performance reports will include view-through conversions. You can choose to disable it if you don't want to include view-through conversions. 

You can enable or disable the feature for each account via Bulk and Campaign Management API.
- With the Bulk API use the Account record and get or set the [Include View Through Conversions](../bulk-service/account.md#includeviewthroughconversions) field. 
- With the Campaign Management API use the [AccountProperty](../campaign-management-service/accountproperty.md) and call [GetAccountProperties](../campaign-management-service/getaccountproperties.md) or [SetAccountProperties](../campaign-management-service/setaccountproperties.md) as needed.

You can manage the view through conversion window with the Campaign Management API i.e., get or set the ViewThroughConversionWindowInMinutes property of the [DurationGoal](../campaign-management-service/durationgoal.md#viewthroughconversionwindowinminutes), [EventGoal](../campaign-management-service/eventgoal.md#viewthroughconversionwindowinminutes), [PagesViewedPerVisitGoal](../campaign-management-service/pagesviewedpervisitgoal.md#viewthroughconversionwindowinminutes), or [UrlGoal](../campaign-management-service/urlgoal.md#viewthroughconversionwindowinminutes). Be sure to explicitly request [ViewThroughConversionWindowInMinutes](../campaign-management-service/conversiongoaladditionalfield.md#viewthroughconversionwindowinminutes) as an additional field when calling [GetConversionGoalsByIds](../campaign-management-service/getconversiongoalsbyids.md#returnadditionalfields) and [GetConversionGoalsByTagIds](../campaign-management-service/getconversiongoalsbytagids.md#returnadditionalfields). 

> [!NOTE]
> View-through conversions require a [UETTag](../campaign-management-service/uettag.md), so this property is not applicable for the [AppInstallGoal](../campaign-management-service/appinstallgoal.md), [InStoreTransactionGoal](../campaign-management-service/instoretransactiongoal.md), and [OfflineConversionGoal](../campaign-management-service/offlineconversiongoal.md). 

### <a name="profileexpansionenabled-october2019"></a>Profile Expansion Enabled
Determines whether to expand LinkedIn profile targeting across your account to reach additional customers similar to the ones you currently target. 

Enabling profile targeting expansion allows Microsoft Advertising to show your ads to additional customers similar to the ones you currently target. For example, if you target a specific LinkedIn audience segment, we will also target Bing users who don't have a confirmed LinkedIn account but who share the same characteristics as LinkedIn users in that segment. 

You can enable or disable the feature for each account via Bulk and Campaign Management API.
- With the Bulk API use the Account record and get or set the [Profile Expansion Enabled](../bulk-service/account.md#profileexpansionenabled) field. 
- With the Campaign Management API use the [AccountProperty](../campaign-management-service/accountproperty.md) and call [GetAccountProperties](../campaign-management-service/getaccountproperties.md) or [SetAccountProperties](../campaign-management-service/setaccountproperties.md) as needed.

## <a name="september2019"></a>September 2019
See below for Bing Ads API updates during this calendar month. 

- [Experiment Type](#experimenttype-september2019)  
- [Final Url Suffix in Reports](#finalurlsuffix-reporting-september2019)  
- [Product Negative Keyword Report](#productnegativekeyword-reporting-september2019)  
- [Bing Ads API SDK Updates](#sdk-september2019)  

### <a name="experimenttype-september2019"></a>Experiment Type
You can now set the experiment split type via the [ExperimentType](../campaign-management-service/experiment.md#experimenttype) element in the [Experiment](../campaign-management-service/experiment.md) Campaign Management object or via the [Experiment Type](../bulk-service/experiment.md#experimenttype) field in the [Experiment](../bulk-service/experiment.md) Bulk record. 

The experiment split type determines whether to show individual customers ads from the experiment and the original campaign randomly, or only from one or the other.

The possible values include TrafficBased and CookieBased. 

TrafficBased: This is also known as the search-based option. Every time customers search, they are randomly shown either ads from your experiment or ads from your original campaign. This means that individual customers could see ads from both sources if they search multiple times.

CookieBased: When individual customers search, we show ads from either your experiment or your original campaign, and use a cookie to ensure that, going forward, they will only see ads from this source. The cookie-based option has an important trade-off to consider: On one hand, you may get more accurate data, since you're ensuring that an individual customer is only responding to one source or the other. On the other hand, it may take you longer to build up statistically significant comparison data than with the search-based option.  

### <a name="finalurlsuffix-reporting-september2019"></a>Final Url Suffix in Reports
The FinalUrlSuffix column is added to the [AdPerformanceReportColumn](../reporting-service/adperformancereportcolumn.md) value set. The FinalUrlSuffix column is also available via the [AdGroupPerformanceReportColumn](../reporting-service/adgroupperformancereportcolumn.md), [CampaignPerformanceReportColumn](../reporting-service/campaignperformancereportcolumn.md), [DestinationUrlPerformanceReportColumn](../reporting-service/destinationurlperformancereportcolumn.md), and [KeywordPerformanceReportColumn](../reporting-service/keywordperformancereportcolumn.md) value sets.

The final URL suffix is a place in your final URL where you can add parameters that will be attached to the end of your landing page URL.

### <a name="productnegativekeyword-reporting-september2019"></a>Product Negative Keyword Report
The [ProductNegativeKeywordConflictReportRequest](../reporting-service/productnegativekeywordconflictreportrequest.md) is added for Microsoft Shopping Campaigns. Use this report to confirm that negative keywords applied to your Shopping campaigns are not excessively restricting campaign performance. You can request negative keywords and the corresponding products which they're preventing from showing in your Shopping campaigns.

### <a name="sdk-september2019"></a>Bing Ads API SDK Updates
The Bing Ads .NET, Java, Php, and Python SDKs are updated. For details please see release notes for Microsoft Advertising [.NET](https://github.com/BingAds/BingAds-dotNet-SDK/releases/tag/v12.13.5), [Java](https://github.com/BingAds/BingAds-Java-SDK/releases/tag/v12.13.5), [Php](https://github.com/BingAds/BingAds-PHP-SDK/releases/tag/v0.12.13.5), and [Python](https://github.com/BingAds/BingAds-Python-SDK/releases/tag/v12.13.5) SDK version 12.13.5. 

## <a name="august2019"></a>August 2019
See below for Bing Ads API updates during this calendar month. 

- [Audience Association Level in Reports](#associationlevel-reporting-august2019)  
- [Bing Ads API SDK Updates](#sdk-august2019)  

### <a name="associationlevel-reporting-august2019"></a>Audience Association Level in Reports
The AssociationLevel column is added to the [AudiencePerformanceReportColumn](../reporting-service/audienceperformancereportcolumn.md) value set. 

### <a name="sdk-august2019"></a>Bing Ads API SDK Updates
The Bing Ads .NET, Java, Php, and Python SDKs are updated. For details please see release notes for Microsoft Advertising [.NET](https://github.com/BingAds/BingAds-dotNet-SDK/releases/tag/v12.13.4), [Java](https://github.com/BingAds/BingAds-Java-SDK/releases/tag/v12.13.4), [Php](https://github.com/BingAds/BingAds-PHP-SDK/releases/tag/v0.12.13.4), and [Python](https://github.com/BingAds/BingAds-Python-SDK/releases/tag/v12.13.4) SDK version 12.13.4. 

## <a name="july2019"></a>July 2019
See below for Bing Ads API updates during this calendar month. 

- [Include in Conversions](#excludefrombidding-july2019)  
- [Base Campaign Id in Reports](#basecampaignid-reporting-july2019)  
- [Average Position in Reports](#averageposition-reporting-july2019)  
- [Audience Association ID in Reports](#associationid-reporting-july2019)  

### <a name="excludefrombidding-july2019"></a>Include in Conversions
Customers who are enabled for the Include in Conversions feature ([GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) returns 574) can choose to exclude specific conversion goals from conversions report data. 

Data will be excluded from the `Conversions`, `ConversionRate`, `CostPerConversion`, `ReturnOnAdSpend`, `RevenuePerConversion`, and `Revenue` report columns for any conversion goal that has its [ExcludeFromBidding](../campaign-management-service/conversiongoal.md#excludefrombidding) property set as true. Also, if you use an automated bidding bid strategy, setting this property true will result in the goal's conversions no longer factoring into automated bidding calculations.

The `AllConversions`, `AllConversionRate`, `AllCostPerConversion`, `AllReturnOnAdSpend`, `AllRevenuePerConversion`, and `AllRevenue` columns (NEW) will include data for all conversion goals regardless of their [ExcludeFromBidding](../campaign-management-service/conversiongoal.md#excludefrombidding) setting. 

For more information, see the help article [Conversion goals: "Conversions" versus "All conversions"](https://help.ads.microsoft.com/#apex/3/en/56920/-1/en/#ext:reporting).  

After the July service update, the table below summarizes all available conversion related report performance statistics per report type. 

|Reporting Value Set|Available Conversion Columns|
|-----|-----|
|[AccountPerformanceReportColumn](../reporting-service/accountperformancereportcolumn.md)|AllConversions<br/>AllRevenue<br/>AllConversionRate<br/>AllCostPerConversion<br/>AllReturnOnAdSpend<br/>AllRevenuePerConversion<br/>Conversions<br/>Revenue<br/>ConversionRate<br/>CostPerConversion<br/>ReturnOnAdSpend<br/>RevenuePerConversion|
|[AdDynamicTextPerformanceReportColumn](../reporting-service/addynamictextperformancereportcolumn.md)|AllConversions<br/>AllConversionRate<br/>AllCostPerConversion<br/>Conversions<br/>ConversionRate<br/>CostPerConversion|
|[AdExtensionByAdReportColumn](../reporting-service/adextensionbyadreportcolumn.md)|AllConversions<br/>AllRevenue<br/>AllConversionRate<br/>AllCostPerConversion<br/>AllReturnOnAdSpend<br/>AllRevenuePerConversion<br/>Conversions<br/>Revenue<br/>ConversionRate<br/>CostPerConversion<br/>ReturnOnAdSpend<br/>RevenuePerConversion|
|[AdExtensionByKeywordReportColumn](../reporting-service/adextensionbykeywordreportcolumn.md)|AllConversions<br/>AllRevenue<br/>AllConversionRate<br/>AllCostPerConversion<br/>AllReturnOnAdSpend<br/>AllRevenuePerConversion<br/>Conversions<br/>Revenue<br/>ConversionRate<br/>CostPerConversion<br/>ReturnOnAdSpend<br/>RevenuePerConversion|
|[AdExtensionDetailReportColumn](../reporting-service/adextensiondetailreportcolumn.md)|AllConversions<br/>AllRevenue<br/>AllConversionRate<br/>AllCostPerConversion<br/>AllReturnOnAdSpend<br/>AllRevenuePerConversion<br/>Conversions<br/>Revenue<br/>ConversionRate<br/>CostPerConversion<br/>ReturnOnAdSpend<br/>RevenuePerConversion|
|[AdGroupPerformanceReportColumn](../reporting-service/adgroupperformancereportcolumn.md)|AllConversions<br/>AllRevenue<br/>AllConversionRate<br/>AllCostPerConversion<br/>AllReturnOnAdSpend<br/>AllRevenuePerConversion<br/>Conversions<br/>Revenue<br/>ConversionRate<br/>CostPerConversion<br/>ReturnOnAdSpend<br/>RevenuePerConversion|
|[AdPerformanceReportColumn](../reporting-service/adperformancereportcolumn.md)|AllConversions<br/>AllRevenue<br/>AllConversionRate<br/>AllCostPerConversion<br/>AllReturnOnAdSpend<br/>AllRevenuePerConversion<br/>Conversions<br/>Revenue<br/>ConversionRate<br/>CostPerConversion<br/>ReturnOnAdSpend<br/>RevenuePerConversion|
|[AgeGenderAudienceReportColumn](../reporting-service/agegenderaudiencereportcolumn.md)|AllConversions<br/>AllRevenue<br/>Conversions<br/>Revenue|
|[AudiencePerformanceReportColumn](../reporting-service/audienceperformancereportcolumn.md)|AllConversions<br/>AllRevenue<br/>AllConversionRate<br/>AllCostPerConversion<br/>AllReturnOnAdSpend<br/>AllRevenuePerConversion<br/>Conversions<br/>Revenue<br/>ConversionRate<br/>CostPerConversion<br/>ReturnOnAdSpend<br/>RevenuePerConversion|
|[CampaignPerformanceReportColumn](../reporting-service/campaignperformancereportcolumn.md)|AllConversions<br/>AllRevenue<br/>AllConversionRate<br/>AllCostPerConversion<br/>AllReturnOnAdSpend<br/>AllRevenuePerConversion<br/>Conversions<br/>Revenue<br/>ConversionRate<br/>CostPerConversion<br/>ReturnOnAdSpend<br/>RevenuePerConversion|
|[ConversionPerformanceReportColumn](../reporting-service/conversionperformancereportcolumn.md)|AllConversions<br/>AllRevenue<br/>AllConversionRate<br/>AllCostPerConversion<br/>AllReturnOnAdSpend<br/>AllRevenuePerConversion<br/>Conversions<br/>Revenue<br/>ConversionRate<br/>CostPerConversion<br/>ReturnOnAdSpend<br/>RevenuePerConversion|
|[DestinationUrlPerformanceReportColumn](../reporting-service/destinationurlperformancereportcolumn.md)|AllConversions<br/>AllRevenue<br/>AllConversionRate<br/>AllCostPerConversion<br/>AllReturnOnAdSpend<br/>AllRevenuePerConversion<br/>Conversions<br/>Revenue<br/>ConversionRate<br/>CostPerConversion<br/>ReturnOnAdSpend<br/>RevenuePerConversion|
|[DSAAutoTargetPerformanceReportColumn](../reporting-service/dsaautotargetperformancereportcolumn.md)|AllConversions<br/>AllRevenue<br/>AllConversionRate<br/>AllCostPerConversion<br/>AllReturnOnAdSpend<br/>AllRevenuePerConversion<br/>Conversions<br/>Revenue<br/>ConversionRate<br/>CostPerConversion<br/>ReturnOnAdSpend<br/>RevenuePerConversion|
|[DSACategoryPerformanceReportColumn](../reporting-service/dsacategoryperformancereportcolumn.md)|AllConversions<br/>AllRevenue<br/>AllConversionRate<br/>AllCostPerConversion<br/>AllReturnOnAdSpend<br/>AllRevenuePerConversion<br/>Conversions<br/>Revenue<br/>ConversionRate<br/>CostPerConversion<br/>ReturnOnAdSpend<br/>RevenuePerConversion|
|[DSASearchQueryPerformanceReportColumn](../reporting-service/dsasearchqueryperformancereportcolumn.md)|AllConversions<br/>AllRevenue<br/>AllConversionRate<br/>AllCostPerConversion<br/>AllReturnOnAdSpend<br/>AllRevenuePerConversion<br/>Conversions<br/>Revenue<br/>ConversionRate<br/>CostPerConversion<br/>ReturnOnAdSpend<br/>RevenuePerConversion|
|[GeographicPerformanceReportColumn](../reporting-service/geographicperformancereportcolumn.md)|AllConversions<br/>AllRevenue<br/>AllConversionRate<br/>AllCostPerConversion<br/>AllReturnOnAdSpend<br/>AllRevenuePerConversion<br/>Conversions<br/>Revenue<br/>ConversionRate<br/>CostPerConversion<br/>ReturnOnAdSpend<br/>RevenuePerConversion|
|[GoalsAndFunnelsReportColumn](../reporting-service/goalsandfunnelsreportcolumn.md)|AllConversions<br/>AllRevenue<br/>Conversions<br/>Revenue|
|[KeywordPerformanceReportColumn](../reporting-service/keywordperformancereportcolumn.md)|AllConversions<br/>AllRevenue<br/>AllConversionRate<br/>AllCostPerConversion<br/>AllReturnOnAdSpend<br/>AllRevenuePerConversion<br/>Conversions<br/>Revenue<br/>ConversionRate<br/>CostPerConversion<br/>ReturnOnAdSpend<br/>RevenuePerConversion|
|[ProductDimensionPerformanceReportColumn](../reporting-service/productdimensionperformancereportcolumn.md)|AllConversions<br/>AllRevenue<br/>AllConversionRate<br/>AllCostPerConversion<br/>AllReturnOnAdSpend<br/>AllRevenuePerConversion<br/>Conversions<br/>Revenue<br/>ConversionRate<br/>CostPerConversion<br/>ReturnOnAdSpend<br/>RevenuePerConversion|
|[ProductPartitionPerformanceReportColumn](../reporting-service/productpartitionperformancereportcolumn.md)|AllConversions<br/>AllRevenue<br/>AllConversionRate<br/>AllCostPerConversion<br/>AllReturnOnAdSpend<br/>AllRevenuePerConversion<br/>Conversions<br/>Revenue<br/>ConversionRate<br/>CostPerConversion<br/>ReturnOnAdSpend<br/>RevenuePerConversion|
|[ProductPartitionUnitPerformanceReportColumn](../reporting-service/productpartitionunitperformancereportcolumn.md)|AllConversions<br/>AllRevenue<br/>AllConversionRate<br/>AllCostPerConversion<br/>AllReturnOnAdSpend<br/>AllRevenuePerConversion<br/>Conversions<br/>Revenue<br/>ConversionRate<br/>CostPerConversion<br/>ReturnOnAdSpend<br/>RevenuePerConversion|
|[ProductSearchQueryPerformanceReportColumn](../reporting-service/productsearchqueryperformancereportcolumn.md)|AllConversions<br/>AllRevenue<br/>AllConversionRate<br/>AllCostPerConversion<br/>AllRevenuePerConversion<br/>Conversions<br/>Revenue<br/>ConversionRate<br/>CostPerConversion<br/>RevenuePerConversion|
|[ProfessionalDemographicsAudienceReportColumn](../reporting-service/professionaldemographicsaudiencereportcolumn.md)|AllConversions<br/>AllRevenue<br/>Conversions<br/>Revenue|
|[PublisherUsagePerformanceReportColumn](../reporting-service/publisherusageperformancereportcolumn.md)|AllConversions<br/>AllRevenue<br/>AllConversionRate<br/>AllCostPerConversion<br/>AllReturnOnAdSpend<br/>AllRevenuePerConversion<br/>Conversions<br/>Revenue<br/>ConversionRate<br/>CostPerConversion<br/>ReturnOnAdSpend<br/>RevenuePerConversion|
|[SearchQueryPerformanceReportColumn](../reporting-service/searchqueryperformancereportcolumn.md)|AllConversions<br/>AllRevenue<br/>AllConversionRate<br/>AllCostPerConversion<br/>AllReturnOnAdSpend<br/>AllRevenuePerConversion<br/>Conversions<br/>Revenue<br/>ConversionRate<br/>CostPerConversion<br/>ReturnOnAdSpend<br/>RevenuePerConversion|
|[ShareOfVoiceReportColumn](../reporting-service/shareofvoicereportcolumn.md)|AllConversions<br/>AllConversionRate<br/>AllCostPerConversion<br/>Conversions<br/>ConversionRate<br/>CostPerConversion|
|[UserLocationPerformanceReportColumn](../reporting-service/userlocationperformancereportcolumn.md)|AllConversions<br/>AllRevenue<br/>AllConversionRate<br/>AllCostPerConversion<br/>AllReturnOnAdSpend<br/>AllRevenuePerConversion<br/>Conversions<br/>Revenue<br/>ConversionRate<br/>CostPerConversion<br/>ReturnOnAdSpend<br/>RevenuePerConversion|

### <a name="basecampaignid-reporting-july2019"></a>Base Campaign Id in Reports
The BaseCampaignId column is added to the following value sets. 
- [AdGroupPerformanceReportColumn](../reporting-service/adgroupperformancereportcolumn.md)  
- [AdPerformanceReportColumn](../reporting-service/adperformancereportcolumn.md)  
- [AgeGenderAudienceReportColumn](../reporting-service/agegenderaudiencereportcolumn.md)  
- [AudiencePerformanceReportColumn](../reporting-service/audienceperformancereportcolumn.md)  
- [CampaignPerformanceReportColumn](../reporting-service/campaignperformancereportcolumn.md)  
- [GeographicPerformanceReportColumn](../reporting-service/geographicperformancereportcolumn.md)  
- [KeywordPerformanceReportColumn](../reporting-service/keywordperformancereportcolumn.md)  
- [ShareOfVoiceReportColumn](../reporting-service/shareofvoicereportcolumn.md)  

### <a name="averageposition-reporting-july2019"></a>Average Position in Reports
The AveragePosition column is added to the [ProfessionalDemographicsAudienceReportColumn](../reporting-service/professionaldemographicsaudiencereportcolumn.md) value set. 

### <a name="associationid-reporting-july2019"></a>Audience Association ID in Reports
The AssociationId column is added to the [AudiencePerformanceReportColumn](../reporting-service/audienceperformancereportcolumn.md) value set. 

## <a name="june2019"></a>June 2019
See below for Bing Ads API updates during this calendar month. 

- [Bing Ads API SDK Updates](#sdk-june2019)  
- [Final Url Suffix and Custom Parameters Update](#finalurlsuffix-customparameters-june2019)  
- [Monday to Sunday Report Aggregation](#monday-sunday-june2019)  
- [Prominence Metrics](#prominence-metrics-june2019)  
- [Change History Report by Tool](#searchcampaignchangehistoryreportcolumn-june2019)  
- [Feeds via Bulk API](#feeds-june2019)  

### <a name="sdk-june2019"></a>Bing Ads API SDK Updates
The Bing Ads .NET, Java, Php, and Python SDKs are updated. For details please see release notes for Microsoft Advertising [.NET](https://github.com/BingAds/BingAds-dotNet-SDK/releases/tag/v12.13.3), [Java](https://github.com/BingAds/BingAds-Java-SDK/releases/tag/v12.13.3), [Php](https://github.com/BingAds/BingAds-PHP-SDK/releases/tag/v0.12.13.3), and [Python](https://github.com/BingAds/BingAds-Python-SDK/releases/tag/v12.13.3) SDK version 12.13.3. 

### <a name="finalurlsuffix-customparameters-june2019"></a>Final Url Suffix and Custom Parameters Update
Final URL suffix and custom parameter updates are now generally available at the account, campaign, ad group, and keyword level for all customers. Similar updates for ads, ad extensions, and ad group criterions are still only available for pilot customers.  
- Final URL suffix is now available at the account, campaign, ad group, and keyword level for all customers. Final URL suffix is available for ads, ad extensions, and ad group criterions for Phase 2 pilot customers ([GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) returns 566). Later this year the Final URL suffix will be available for ads, ad extensions, and ad group criterions for all customers.  
- The custom parameter limit for all customers has been increased from 3 to 8 for campaigns, ad groups, and keywords. Microsoft Advertising will accept the first 8 custom parameter key and value pairs that you include, and if you include more than 8 custom parameters an error will be returned. For customers in the Custom Parameters Limit Increase Phase 2 pilot ([GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) returns 565) for ads, ad extensions, and ad group criterions, Microsoft Advertising will accept the first 8 custom parameter key and value pairs that you include, and if you include more than 8 custom parameters an error will be returned. During calendar year 2019 the limit for ads, ad extensions, and ad group criterions will be increased from 3 to 8 for all customers.  

### <a name="monday-sunday-june2019"></a>Monday to Sunday Report Aggregation
The Reporting API is updated to support Monday through Sunday weekly aggregation. Previously you could only aggregate weekly from Sunday through Saturday. 

The [WeeklyStartingMonday](../reporting-service/reportaggregation.md#weeklystartingmonday) value is added to the [ReportAggregation](../reporting-service/reportaggregation.md) value set.  

The [ThisWeekStartingMonday](../reporting-service/reporttimeperiod.md#thisweekstartingmonday), [LastWeekStartingMonday](../reporting-service/reporttimeperiod.md#lastweekstartingmonday), and [LastFourWeeksStartingMonday](../reporting-service/reporttimeperiod.md#lastfourweeksstartingmonday) values are added to the [ReportTimePeriod](../reporting-service/reporttimeperiod.md) value set.  

### <a name="prominence-metrics-june2019"></a>Prominence Metrics
With new and improved prominence metrics, you may now take a more holistic view of where your ads are appearing on search results pages. These clearer insights can help you better optimize your bidding strategy. 

The AbsoluteTopImpressionRatePercent, AbsoluteTopImpressionShareLostToBudgetPercent, AbsoluteTopImpressionShareLostToRankPercent, TopImpressionRatePercent, TopImpressionShareLostToBudgetPercent, TopImpressionShareLostToRankPercent, and TopImpressionSharePercent columns are added to the following report column value sets.

- [AccountPerformanceReportColumn](../reporting-service/accountperformancereportcolumn.md)  
- [AdGroupPerformanceReportColumn](../reporting-service/adgroupperformancereportcolumn.md)  
- [CampaignPerformanceReportColumn](../reporting-service/campaignperformancereportcolumn.md)  
- [ShareOfVoiceReportColumn](../reporting-service/shareofvoicereportcolumn.md)  

### <a name="searchcampaignchangehistoryreportcolumn-june2019"></a>Change History Report by Tool
The [Tool](../reporting-service/searchcampaignchangehistoryreportcolumn.md#tool) column is now available with the change history report. You can determine how changes were made to account, campaign or ad attributes e.g., whether via the Web client, Editor, Bulk upload, or Campaign Management API. 

### <a name="feeds-june2019"></a>Feeds via Bulk API
The [Feed](../bulk-service/feed.md) and [Feed Item](../bulk-service/feed-item.md) Bulk records are added to support [Bulk download and upload](bulk-download-upload.md) of both [Ad Customizer Feeds](ad-customizer-feeds.md) and [Page Feeds](page-feeds.md).  

The [Page Feed Ids](../bulk-service/campaign.md#pagefeedids) field is added to the [Campaign](../bulk-service/campaign.md) record for [Page Feeds](page-feeds.md).  

## <a name="may2019"></a>May 2019
See below for Bing Ads API updates during this calendar month. 

- [Assisted Conversions](#assistedconversions-may2019)  
- [Dynamic Search Ads Text Part 2](#textpart2dsa-may2019)  
- [Bing Ads API SDK Updates](#sdk-may2019)  

### <a name="assistedconversions-may2019"></a>Assisted Conversions
Assisted conversions are conversions resulting from the clicks on your ads that have received co-bids from your manufacturer partners. This performance statistic is only available for Sponsored Products in Microsoft Shopping Campaigns. The AssistedConversions column is added to the following report column value sets.

- [ProductDimensionPerformanceReportColumn](../reporting-service/productdimensionperformancereportcolumn.md)  
- [ProductPartitionPerformanceReportColumn](../reporting-service/productpartitionperformancereportcolumn.md)  
- [ProductPartitionUnitPerformanceReportColumn](../reporting-service/productpartitionunitperformancereportcolumn.md)  
- [ProductSearchQueryPerformanceReportColumn](../reporting-service/productsearchqueryperformancereportcolumn.md)  

### <a name="textpart2dsa-may2019"></a>Dynamic Search Ads Text Part 2
Dynamic Search Ads Text Part 2 is available for pilot customers ([GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) returns 600). Later this year it will be available in all customers. 

The [TextPart2](../campaign-management-service/dynamicsearchad.md#textpart2) element is available in the [DynamicSearchAd](../campaign-management-service/dynamicsearchad.md) Campaign Management object. The [Text Part 2](../bulk-service/dynamic-search-ad.md#textpart2) field is available in the [Dynamic Search Ad](../bulk-service/dynamic-search-ad.md#textpart2) Bulk record. 

### <a name="sdk-may2019"></a>Bing Ads API SDK Updates
The Bing Ads .NET, Java, Php, and Python SDKs are updated. For details please see release notes for Microsoft Advertising [.NET](https://github.com/BingAds/BingAds-dotNet-SDK/releases/tag/v12.13.2), [Java](https://github.com/BingAds/BingAds-Java-SDK/releases/tag/v12.13.2), [Php](https://github.com/BingAds/BingAds-PHP-SDK/releases/tag/v0.12.13.2), and [Python](https://github.com/BingAds/BingAds-Python-SDK/releases/tag/v12.13.2) SDK version 12.13.2. 

## <a name="april2019"></a>April 2019
See below for Bing Ads API updates during this calendar month. 

- [New Production OAuth Endpoint](#oauth-april2019)  
- [Bing Ads API SDK Updates](#sdk-april2019)  
- [Version 13 General Availability](#v13-april2019)  

### <a name="oauth-april2019"></a>New Production OAuth Endpoint
The [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) for developers is now available. The Microsoft identity platform endpoint allows both work or school accounts from Azure AD and personal Microsoft accounts (MSA), such as hotmail.com, outlook.com, and msn.com. The [Live Connect](authentication-oauth-live-connect.md) endpoint only allows authentication with personal accounts. 

> [!IMPORTANT]
> Even if your users do not have work or school accounts, and even if you do not use the Bing Ads API SDKs we encourage you to update the authorization URL during calendar year 2019, since the Live Connect endpoint is no longer the recommended approach for Microsoft Advertising users. For details see [Upgrade to the Microsoft identity platform endpoint FAQ](authentication-oauth.md#upgrade-identity-platform-faq) and [Authentication with the Microsoft identity platform endpoint](authentication-oauth-identity-platform.md). 

### <a name="sdk-april2019"></a>Bing Ads API SDK Updates
The Bing Ads .NET, Java, Php, and Python SDKs are updated with support for version 13. For details please see release notes for Microsoft Advertising [.NET](https://github.com/BingAds/BingAds-dotNet-SDK/releases/tag/v12.13.1), [Java](https://github.com/BingAds/BingAds-Java-SDK/releases/tag/v12.13.1), [Php](https://github.com/BingAds/BingAds-PHP-SDK/releases/tag/v0.12.13.1), and [Python](https://github.com/BingAds/BingAds-Python-SDK/releases/tag/v12.13.1) SDK version 12.13.1. 

### <a name="v13-april2019"></a>Version 13 General Availability
Bing Ads API version 13 is now generally available. With the availability of Bing Ads API version 13, version 12 is deprecated and will sunset by October 31, 2019. For more details, see [Migrate to Version 13](migration-guide.md).  

## <a name="march2019"></a>March 2019
See below for Bing Ads API updates during this calendar month. 

- [Version 13 Preview](#v13-march2019)  

### <a name="v13-march2019"></a>Version 13 Preview
Bing Ads API version 13 is available for preview. For more details about migrating from version 12, see [Migrate to Version 13](migration-guide.md). 
