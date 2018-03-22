---
title: "Bing Ads API Release Notes"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Get information about the changes to the Bing Ads services for each month.
---
# Bing Ads API Release Notes
For information about the changes to the Bing Ads services for each month, see the following sections.  

## <a name="march2018"></a>March 2018
For information about this month's changes to Bing Ads services, see the following sections.

-   [Bing Ads Software Development Kit (SDK) Updates](#sdk-march2018)  
-   [Custom Audience Delete](#customaudiencedelete-march2018)  

### <a name="sdk-march2018"></a>Bing Ads Software Development Kit (SDK) Updates
The Bing Ads .NET, Java, PHP, and Python SDKs are updated to support [Microsoft Account authentication in sandbox](sandbox.md#access). Starting with Bing Ads API version 12, only OAuth authentication will be supported. Managed credentials i.e., the *UserName* and *Password* header elements are not supported. 

The Bing Ads Java SDK is updated to Java 1.7. As [announced previously](https://blogs.msdn.microsoft.com/bing_ads_api/2018/02/02/mandatory-upgrade-required-to-tls1-2/) at the end of March, we will disable TLS1.0/1.1 across all Bing Ads interfaces, and leave support for TLS1.2 only. You must upgrade at minimum to Java 1.7 e.g., update 131. 

### <a name="customaudiencedelete-march2018"></a>Custom Audience Delete
Bing Ads API now supports deletion of custom audiences via the [Custom Audience](../bulk-service/custom-audience.md) (Bulk API) and [CustomAudience](../campaign-management-service/customaudience.md) (Campaign Management API).

## <a name="january2018"></a>January 2018
For information about this month's changes to Bing Ads services, see the following sections.

-   [Bing Ads Software Development Kit (SDK) Updates](#sdk-january2018)  
-   [Audience Search Size](#audiencesearchsize-january2018)  

### <a name="sdk-january2018"></a>Bing Ads Software Development Kit (SDK) Updates
The Bing Ads .NET, Java, PHP, and Python SDKs are updated to support [audience search size](https://docs.microsoft.com/en-us/bingads/guides/release-notes#audiencesearchsize-january2018). 

### <a name="audiencesearchsize-january2018"></a>Audience Search Size
You can find out the total number of people who belong to an audience i.e., custom audience, in-market audience, and remarketing list size. This gives you an idea of how many search users you can target.

#### <a name="bulk-v11-audiencesearchsize-january2018"></a>Bulk API Version 11 for Audience Search Size  
You can fetch the audience search size in the *Audience Search Size* column of the [Custom Audience](../bulk-service/custom-audience.md), [In Market Audience](../bulk-service/in-market-audience.md), and [Remarketing List](../bulk-service/remarketing-list.md) Bulk records.

#### <a name="campaign-v11-audiencesearchsize-january2018"></a>Campaign Management API Version 11 for Audience Search Size  
You can fetch the audience search size in the *SearchSize* property of the [CustomAudience](../campaign-management-service/customaudience.md), [InMarketAudience](../campaign-management-service/inmarketaudience.md), and [RemarketingList](../campaign-management-service/remarketinglist.md) objects. The *SearchSize* property is inherited from the [Audience](../campaign-management-service/audience.md) base class.

## <a name="november2017"></a>November 2017
For information about this month's changes to Bing Ads services, see the following sections.

-   [New Reporting Columns for Estimated Bids](#reporting-estimatedbids-november2017)  


### <a name="reporting-estimatedbids-november2017"></a>New Reporting Columns for Estimated Bids
You can now include estimated bid columns in the keyword performance data download. 

The *Mainline1Bid*, *MainlineBid*, and *SidebarBid* columns are added to the [KeywordPerformanceReportColumn](../reporting-service/keywordperformancereportcolumn.md) value set. 

## <a name="october2017"></a>October 2017
For information about this month's changes to Bing Ads services, see the following sections.

-   [New Reporting Column for Exact Match Impression Share](#reporting-exactmatchimpressionshare-october2017)  
-   [New Reporting Columns for Labels](#reporting-labels-october2017)  

### <a name="reporting-exactmatchimpressionshare-october2017"></a>New Reporting Column for Exact Match Impression Share
You can now include the exact match impression share percent in the performance data download. 

The *ExactMatchImpressionSharePercent* column has been added to the [AccountPerformanceReportColumn](../reporting-service/accountperformancereportcolumn.md), [AdGroupPerformanceReportColumn](../reporting-service/adgroupperformancereportcolumn.md), [CampaignPerformanceReportColumn](../reporting-service/campaignperformancereportcolumn.md), and [ShareOfVoiceReportColumn](../reporting-service/shareofvoicereportcolumn.md) value sets. 

### <a name="reporting-labels-october2017"></a>New Reporting Columns for Labels
You can now include campaign, ad group, ad, and keyword labels in the performance data download. 

The *AdLabels* column has been added to the [AdDynamicTextPerformanceReportColumn](../reporting-service/addynamictextperformancereportcolumn.md) and [AdPerformanceReportColumn](../reporting-service/adperformancereportcolumn.md) value sets.  

The *AdGroupLabels* column has been added to the [AdGroupPerformanceReportColumn](../reporting-service/adgroupperformancereportcolumn.md) value set.  

The *CampaignLabels* column has been added to the [CampaignPerformanceReportColumn](../reporting-service/campaignperformancereportcolumn.md) value set.  

The *KeywordLabels* column has been added to the [KeywordPerformanceReportColumn](../reporting-service/keywordperformancereportcolumn.md) and [ShareOfVoiceReportColumn](../reporting-service/shareofvoicereportcolumn.md) value sets.  


## <a name="september2017"></a>September 2017
For information about this month's changes to Bing Ads services, see the following sections.

-   [Bing Ads Software Development Kit (SDK) Updates](#sdk-september2017)  

### <a name="sdk-september2017"></a>Bing Ads Software Development Kit (SDK) Updates
The Bing Ads .NET, Java, PHP, and Python SDKs are updated with support for the following features. Unless otherwise noted the changes only apply to Bing Ads API version 11. Some objects are reserved for future use, so please refer to the service reference documentation for availability details.

* The [Reporting]( release-notes.md#reporting-locations-august2017) service proxies are updated to support new columns for location targeting.  
* For the Bing Ads .NET SDK - Fixed the Bulk download DateTime parser for compatibility with localized time zone settings.  
* For the Bing Ads Java SDK - Added an option to automatically delete the temporary bulk file used by BulkServiceManager for upload and download per the Github community [pull request](https://github.com/BingAds/BingAds-Java-SDK/issues/41). 
* For the Bing Ads Java SDK - Implemented internal retry logic for creating a new service with the wsdl. 

## <a name="august2017"></a>August 2017
For information about this month's changes to Bing Ads services, see the following sections.

-   [Bing Ads Software Development Kit (SDK) Updates](#sdk-august2017)  
-   [Increase in subdomain limit for website exclusions](#negativesites-august2017)  
-   [Geographical Locations File Version 2.0](#geo-locations-august2017)  
-   [New Reporting Columns for Location Targeting](#reporting-locations-august2017)  

### <a name="sdk-august2017"></a>Bing Ads Software Development Kit (SDK) Updates
The Bing Ads .NET, Java, and Python SDKs are updated with support for the following features. Unless otherwise noted the changes only apply to Bing Ads API version 11. Some objects are reserved for future use, so please refer to the service reference documentation for availability details.

* The [Campaign Management]( release-notes.md#inheritedbidstrategytype-july2017) service proxies are updated to support inherited bid strategy type.  
* The [Reporting]( release-notes.md#reporting-bsc-july2017) service proxies are updated to support new columns for Bing Shopping campaigns.
* New version 11 bulk labels objects are added i.e., *BulkLabel*, *BulkCampaignLabel*, *BulkAdGroupLabel*, *BulkKeywordLabel*, *BulkAppInstallAdLabel*, *BulkDynamicSearchAdLabel*, *BulkExpandedTextAdLabel*, *BulkProductAdLabel*, and *BulkTextAdLabel* objects are added to the SDK for reading and writing the corresponding [Bulk file records]( release-notes.md#bulk-v11-labels-july2017).
* A new version 11 bulk offline conversion object is added i.e., the *BulkOfflineConversion* object is added to the SDK for writing and uploading the corresponding [Bulk file record]( release-notes.md#bulk-v11-offline-conversions-july2017).  
* For the Bing Ads .NET SDK - Fixed the mapping for expired ad groups in the *BulkAdGroup* object. Previously if the ad group status in the bulk file was *Expired*, the SDK mapped and returned the value as *Deleted*. Prior to Bing Ads API version 10, expired ad groups were returned with a deleted status by design for backwards compatibility. 


### <a name="negativesites-august2017"></a>Increase in subdomain limit for website exclusions
The limit of subdomains allowed in a website exclusion increased from two to three, based on customer requests. This will enable you to exclude URLs based on two-part top-level domains (TLDs) such as *.co.uk*. The number of allowed subdirectories remains unchanged at two. 

For example, the following are valid URLs,
*  one.two.three.contoso.com/1/2  
*  www.two.three.contoso.com/1/2  
*  one.two.contoso.co.uk/1/2

The following are invalid URLs:
*  one.two.three.contoso.co.uk/1/2 (too many subdomains)  
*  one.two.three.contoso.com/1/2/3 (too many subdirectories)  

For reference documentation, please see [CampaignNegativeSites](../campaign-management-service/campaignnegativesites.md) and [AdGroupNegativeSites](../campaign-management-service/adgroupnegativesites.md).

### <a name="geo-locations-august2017"></a>Geographical Locations File Version 2.0 
The [GetGeoLocationsFileUrl](../campaign-management-service/getgeolocationsfileurl.md) operation now supports version 2.0. County location IDs are only available in version 2.0.

For more details about the contents of each file version, see [Geographical Location Codes](geographical-location-codes.md).

> [!IMPORTANT]
> The locations file Version 1.0 is deprecated in favor of version 2.0. After October 31, 2017 version 1.0 will be sunset and only 2.0 will be supported. 

### <a name="reporting-locations-august2017"></a>New Reporting Columns for Location Targeting
The *County*, *LocationId*, and *PostalCode* columns have been added to the [GeographicPerformanceReportColumn](../reporting-service/geographicperformancereportcolumn.md) value set.

The *County*, *LocationId*, *PostalCode*, *QueryIntentCounty*, *QueryIntentPostalCode*, and *QueryIntentLocationId* columns have been added to the [UserLocationPerformanceReportColumn](../reporting-service/userlocationperformancereportcolumn.md) value set.

## <a name="july2017"></a>July 2017
For information about this month's changes to Bing Ads services, see the following sections.

-   [Keyword Planner](#keyword-planner-july2017)  
-   [Labels](#labels-july2017)  
-   [Offline Conversion Import](#offline-conversions-july2017)  
-   [New Reporting Columns for Bing Shopping Campaigns](#reporting-bsc-july2017)  
-   [Inherited Bid Strategy Type](#inheritedbidstrategytype-july2017)
-   [Bing Ads Software Development Kit (SDK) Updates](#sdk-july2017)  

### <a name="keyword-planner-july2017"></a>Keyword Planner
Support for keyword planner operations is added. The Keyword Planner was already available in the Bing Ads web application, and now support is added for Bing Ads API version 11.

> [!NOTE]
> Keyword Planner features are currently available to customers in the United States, United Kingdom, Canada, Australia, France, and Germany.

Given a list of existing keywords, the [GetKeywordIdeas](../ad-insight-service/getkeywordideas.md) operation suggests new ad groups and keywords based on your existing keywords, website, and product category. You can also request historical statistics for keywords e.g., monthly searches, competition, average CPC, and ad impression share. You can use the returned suggested keyword bids as input to the [GetKeywordTrafficEstimates](../ad-insight-service/getkeywordtrafficestimates.md) operation.

The result is a [KeywordIdea](../ad-insight-service/keywordidea.md) list. Each keyword idea includes historical statistics for keywords e.g., monthly searches, competition, average CPC, and ad impression share. Whereas the Bing Ads web application returns a 12 month average of the historical monthly search counts, each [KeywordIdea](../ad-insight-service/keywordidea.md) includes a list of monthly search counts. You can use each count individually or average them for parity with the Bing Ads web application's calculation.

Once you have already settled on an initial set of keywords, the [GetKeywordTrafficEstimates](../ad-insight-service/getkeywordtrafficestimates.md) operation provides traffic estimates for keywords e.g., average CPC, average position, clicks, CTR, impressions, and total cost. As input you provide the keyword, bid, language, location, and network, with optional campaign budget and negative keyword filters.

The result is a [KeywordEstimate](../ad-insight-service/keywordestimate.md) list for each [AdGroupEstimate](../ad-insight-service/adgroupestimate.md), which are all nested within one [CampaignEstimate](../ad-insight-service/campaignestimate.md). Each keyword estimate includes a minimum and maximum [TrafficEstimate](../ad-insight-service/trafficestimate.md). As previously mentioned, the traffic estimates for keywords include average CPC, average position, clicks, CTR, impressions, and total cost.

For more details see the [Keyword Ideas and Traffic Estimates](keyword-ideas-traffic-estimates.md) technical guide.

### <a name="labels-july2017"></a>Labels
Support for labels is added. Labels let you organize campaigns, ad groups, ads, and keywords into groups based on whatever is important to you. You can then filter and run reports on your labels to get the data that is most meaningful to you.

#### <a name="bulk-v11-labels-july2017"></a>Bulk API Version 11 for Labels  
You can use the following Bulk record types to manage labels with the Bulk API.
-   [Label](../bulk-service/label.md)
-   [Campaign Label](../bulk-service/campaign-label.md)
-   [Ad Group Label](../bulk-service/ad-group-label.md)
-   [Keyword Label](../bulk-service/keyword-label.md)
-   [App Install Ad Label](../bulk-service/app-install-ad-label.md)
-   [Dynamic Search Ad Label](../bulk-service/dynamic-search-ad-label.md)
-   [Expanded Text Ad Label](../bulk-service/expanded-text-ad-label.md)
-   [Product Ad Label](../bulk-service/product-ad-label.md)
-   [Text Ad Label](../bulk-service/text-ad-label.md)

#### <a name="campaign-v11-labels-july2017"></a>Campaign Management API Version 11 for Labels  
You can add, delete, get, and update labels ([Label](../campaign-management-service/label.md) objects) with the corresponding operations.
-  [AddLabels](../campaign-management-service/addlabels.md)  
-  [DeleteLabels](../campaign-management-service/deletelabels.md)  
-  [GetLabelsByIds](../campaign-management-service/getlabelsbyids.md)  
-  [UpdateLabels](../campaign-management-service/updatelabels.md)  

You can set, get, and delete label associations ([LabelAssociation](../campaign-management-service/labelassociation.md) objects) with the corresponding operations.
-  [DeleteLabelAssociations](../campaign-management-service/deletelabelassociations.md)  
-  [GetLabelAssociationsByEntityIds](../campaign-management-service/getlabelassociationsbyentityids.md)  
-  [GetLabelAssociationsByLabelIds](../campaign-management-service/getlabelassociationsbylabelids.md)  
-  [SetLabelAssociations](../campaign-management-service/setlabelassociations.md)  

### <a name="offline-conversions-july2017"></a>Offline Conversion Import
Support for Offline Conversion Import is added. Use offline conversions to track the full impact and benefit of your search ads. It allows you to import offline conversions derived from a search click back into Bing Ads. 

To set up offine conversion tracking, create an offline conversion goal with the [Campaign Management](#campaign-v11-offline-conversions-july2017) service or via the Bing Ads web application, wait two hours, and then send Bing Ads the offline conversion data with either the [Campaign Management](#campaign-v11-offline-conversions-july2017) service or [Bulk](#bulk-v11-offline-conversions-july2017) service.

You must also enable MSCLKID Auto Tagging. Every time you add or update a new [OfflineConversionGoal](../campaign-management-service/offlineconversiongoal.md) via either the Bing Ads web application or Campaign Management API, the MSCLKID Auto Tagging is enabled automatically. You can enable or disable auto tagging using either the [Campaign Management](#campaign-v11-offline-conversions-july2017) service or [Bulk](#bulk-v11-offline-conversions-july2017) service. 

For more information, see [Tracking offline conversions](https://help.bingads.microsoft.com/#apex/3/en/help:app54554/1/en-US/#ext:ConversionTracking-Load).

#### <a name="bulk-v11-offline-conversions-july2017"></a>Bulk API Version 11 for Offline Conversions  
You can send Bing Ads the offline conversion data by uploading one or more [Offline Conversion](../bulk-service/offline-conversion.md) Bulk records.

To manage the MSCLKID Auto Tagging, use the *MSCLKID Auto Tagging Enabled* field of the [Account](../bulk-service/account.md) Bulk record.

#### <a name="campaign-v11-offline-conversions-july2017"></a>Campaign Management API Version 11 for Offline Conversions  

You can manage [OfflineConversionGoal](../campaign-management-service/offlineconversiongoal.md) objects with the previously shipped conversion goal service operations e.g. [AddConversionGoals](../campaign-management-service/addconversiongoals.md).

You can send Bing Ads the offline conversion data by submitting [OfflineConversion](../campaign-management-service/offlineconversion.md) data via the [ApplyOfflineConversions](../campaign-management-service/applyofflineconversions.md) operation.

To manage the MSCLKID Auto Tagging, use the corresponding [AccountProperty](../campaign-management-service/accountproperty.md) (*MSCLKIDAutoTaggingEnabled*) via the [GetAccountProperties](../campaign-management-service/getaccountproperties.md) and [SetAccountProperties](../campaign-management-service/setaccountproperties.md) operations. 

### <a name="reporting-bsc-july2017"></a>New Reporting Columns for Bing Shopping Campaigns
The *ReturnOnAdSpend*, *BidStrategyType*, *LocalStoreCode*, and *StoreId* columns have been added to the [ProductDimensionPerformanceReportColumn](../reporting-service/productdimensionperformancereportcolumn.md) value set.

The *ReturnOnAdSpend*, *BidStrategyType*, and *LocalStoreCode* columns have been added to the [ProductPartitionPerformanceReportColumn](../reporting-service/productpartitionperformancereportcolumn.md) value set.

The *ReturnOnAdSpend*, *BidStrategyType*, and *LocalStoreCode* columns have been added to the [ProductPartitionUnitPerformanceReportColumn](../reporting-service/productpartitionunitperformancereportcolumn.md) value set.

### <a name="inheritedbidstrategytype-july2017"></a>Inherited Bid Strategy Type
You can get the bid strategy type that is inherited from each ad group or keyword's parent campaign or ad group. This value is equal to the parent campaign or ad group's *Bid Strategy Type* field. Possible values are *EnhancedCpc*, *ManualCpc*, *MaxClicks*, *MaxConversions*, and *TargetCpa*.

#### <a name="bulk-v11-inheritedbidstrategytype-july2017"></a>Bulk API Version 11 for Inherited Bid Strategy Type  
The *Inherited Bid Strategy Type* field is added to the [Ad Group](../bulk-service/ad-group.md) and [Keyword](../bulk-service/keyword.md) records. 

#### <a name="campaign-v11-inheritedbidstrategytype-july2017"></a>Campaign Management API Version 11 for Inherited Bid Strategy Type  
The *InheritedBidStrategyType* element is added to the  [InheritFromParentBiddingScheme](../campaign-management-service/inheritfromparentbiddingscheme.md) object. This element is not returned by default. You must include *InheritedBidStrategyType* in the *ReturnAdditionalFields* optional request element when calling [GetAdGroupsByCampaignId](../campaign-management-service/getadgroupsbycampaignid.md), [GetAdGroupsByIds](../campaign-management-service/getadgroupsbyids.md), [GetKeywordsByAdGroupId](../campaign-management-service/getkeywordsbyadgroupid.md), [GetKeywordsByEditorialStatus](../campaign-management-service/getkeywordsbyeditorialstatus.md), and [GetKeywordsByIds](../campaign-management-service/getkeywordsbyids.md).


### <a name="sdk-july2017"></a>Bing Ads Software Development Kit (SDK) Updates
The Bing Ads .NET, Java, and Python SDKs are updated with support for the following features. Unless otherwise noted the changes only apply to Bing Ads API version 11. Some objects are reserved for future use, so please refer to the service reference documentation for availability details.

#### <a name="sdk-breaking-changes-july2017"></a>Breaking Changes
> [!IMPORTANT]
> Before you upgrade to the latest SDK please note the following breaking changes.
* The *Status* property of the *BulkCampaignProductScope* object is removed. The Bulk file *Status* field is now mapped to the *Status* element of the *BiddableCampaignCriterion* of the *BulkCampaignProductScope*. 
* All BulkEntity derived SDK objects (except *BulkAdGroupProductPartition*) which previously contained the *AdGroupCriterion* or *CampaignCriterion* property are updated as either Biddable or Negative. Both the type and the name are updated e.g. *BulkAdGroupAgeCriterion* has property name *BiddableAdGroupCriterion* and data type *BiddableAdGroupCriterion*. The purpose is to be clear about the supported data type per bulk entity up front, rather than causing friction later i.e., runtime errors due to mismatch of BulkEntity to concrete criterion type. Several bulk entities were updated during the May 2017 release; and the remaining mappings are fixed with this release.

#### <a name="sdk-non-breaking-changes-july2017"></a>Non Breaking Changes
* The [Ad Insight]( release-notes.md#keyword-planner-july2017) service proxies are updated to support the keyword planner. 
* The [Bulk]( release-notes.md#bulk-v11-labels-july2017) service proxies are updated to support labels.
* The [Campaign Management]( release-notes.md#campaign-v11-labels-july2017) service proxies are updated to support labels.  
* The [Bulk]( release-notes.md#bulk-v11-offline-conversions-july2017) service proxies are updated to support offline conversions.
* The [Campaign Management]( release-notes.md#campaign-v11-offline-conversions-july2017) service proxies are updated to support offline conversions.  
* Support is added for Bulk entity mapping of multiple campaign languages i.e., updated mapping of the *Language* field in the Bulk file to the *BulkCampaign* and *BulkAdGroup*. 
* Support is added for Bulk entity mapping of MaxConversions, MaxCpc, and TargetCpa bid strategy types i.e., mapping of the *Bid Strategy Type*, *Bid Strategy MaxCpc*, and *Bid Strategy TargetCpa* fields in the Bulk file to the *BulkCampaign*. 
* Support is added for Bulk entity mapping of LocalInventoryAdsEnabled for Bing Shopping campaigns i.e., mapping of the *LocalInventoryAdsEnabled* field in the Bulk file to the *BulkCampaign*.
* Performance data mapping is added to the *BulkAdGroupRemarketingListAssociation* object.
* New version 11 bulk audience objects are added i.e., *BulkAdGroupNegativeRemarketingListAssociation*, *BulkCustomAudience*, *BulkAdGroupCustomAudience*, *BulkAdGroupNegativeCustomAudience*, *BulkInMarketAudience*, *BulkAdGroupInMarketAudience*, and *BulkAdGroupNegativeInMarketAudience* objects are added to the SDK for reading and writing the corresponding Bulk file records.
* New version 11 bulk price ad extension objects are added i.e., *BulkPriceAdExtension*, *BulkCampaignPriceAdExtension*, and *BulkAdGroupPriceAdExtension* objects are added to the SDK for reading and writing the corresponding Bulk file records.
* New version 11 bulk account level ad extension objects are added i.e., *BulkAccountAppAdExtension*, *BulkAccountCalloutAdExtension*, *BulkAccountImageAdExtension*, *BulkAccountLocationAdExtension*, *BulkAccountPriceAdExtension*, *BulkAccountReviewAdExtension*, and *BulkAccountSitelink2AdExtension* objects are added to the SDK for reading and writing the corresponding Bulk file records.

## <a name="may2017"></a>May 2017
For information about this month's changes to Bing Ads services, see the following sections.

-   [Bing Ads API Version 11 General Availability](#v11-ga-may2017)  
-   [Bing Ads Software Development Kit (SDK) Updates](#sdk-may2017)  
-   [Dynamic Search Ads Reports](#reporting-v11-dsa-may2017)  

### <a name="v11-ga-may2017"></a>Bing Ads API Version 11 General Availability
Bing Ads API Version 11 is released to production. For more details, see [Migrate to Version 11](migration-guide.md) and [Bing Ads API Reference](reference.md).

### <a name="sdk-may2017"></a>Bing Ads PHP Software Development Kit (SDK)
The Bing Ads .NET, Java, and PHP SDKs are updated with support for Bing Ads API Version 11 [web service addresses](web-service-addresses.md). This release enables you to [upgrade](migration-guide.md) existing features from version 9 and 10 to version 11. 

Bulk entity support for new version 11 features e.g. *BulkPriceAdExtension* will be added to the .NET, Java, and Python SDKs in a future release.

### <a name="reporting-v11-dsa-may2017"></a>Dynamic Search Ads Reports
The the following reports are added for Dynamic Search Ads.
- [DSAAutoTargetPerformanceReportRequest](../reporting-service/dsaautotargetperformancereportrequest.md)  
- [DSACategoryPerformanceReportRequest](../reporting-service/dsacategoryperformancereportrequest.md)  
- [DSASearchQueryPerformanceReportRequest](../reporting-service/dsasearchqueryperformancereportrequest.md)

## <a name="april2017"></a>April 2017
For information about this month's changes to Bing Ads services, see the following sections.

-   [Bing Ads API Version 11 Preview](#v11-preview-april2017)  
-   [Bing Ads PHP Software Development Kit (SDK)](#php-sdk-april2017)  
-   [Bing Shopping Product Search Query Performance Report](#productsearchqueryperformancereport-april2017)  

### <a name="v11-preview-april2017"></a>Bing Ads API Version 11 Preview
A preview of the Bing Ads API Version 11 is released to sandbox. For more details, see [Migrate to Version 11](migration-guide.md).

### <a name="php-sdk-april2017"></a>Bing Ads PHP Software Development Kit (SDK)
The Bing Ads PHP SDK is now available. 

For details please see the [blog post](https://blogs.msdn.microsoft.com/bing_ads_api/2017/04/05/announcing-bing-ads-php-sdk/) and [Get Started Using PHP with Bing Ads Services](get-started-php.md).

### <a name="productsearchqueryperformancereport-april2017"></a>Bing Shopping Product Search Query Performance Report
The Product Search Query performance report is now available for Bing Shopping Campaigns. Submit the [ProductPartitionPerformanceReportRequest](../reporting-service/productpartitionperformancereportrequest.md) to see what your audience is searching for when your product ads are shown.
