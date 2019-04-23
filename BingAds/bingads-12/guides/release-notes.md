---
title: "Bing Ads API Release Notes"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Get information about changes to Bing Ads API Version 12 by month. 
---
# Bing Ads API Release Notes
See below for information about changes to Bing Ads API Version 12 by month. 

## <a name="april2019"></a>April 2019
See below for Bing Ads API updates during this calendar month. 

- [New Production OAuth Endpoint](#oauth-april2019)  
- [Bing Ads Software Development Kit (SDK) Updates](#sdk-april2019)  

## <a name="oauth-april2019"></a>New Production OAuth Endpoint
The [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) for developers is now available. The Microsoft identity platform endpoint allows both work or school accounts from Azure AD and personal Microsoft accounts (MSA), such as hotmail.com, outlook.com, and msn.com. The [Live Connect](authentication-oauth-live-connect.md) endpoint only allows authentication with personal accounts. 

> [!IMPORTANT]
> During Q2 calendar year 2019 the Bing Ads SDKs will be updated to use the [Microsoft identity platform endpoint](https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-overview). Even if your users do not have work or school accounts, and even if you do not use the Bing Ads SDKs we encourage you to update the authorization URL during calendar year 2019, since the Live Connect endpoint is no longer the recommended approach for Bing Ads users. For details see [Upgrade to the Microsoft identity platform endpoint FAQ](authentication-oauth.md#upgrade-identity-platform-faq) and [Authentication with the Microsoft identity platform endpoint](authentication-oauth-identity-platform.md). 

### <a name="sdk-april2019"></a>Bing Ads Software Development Kit (SDK) Updates
The Bing Ads .NET, Java, Php, and Python SDKs are updated with support for version 13. For details please see release notes for Bing Ads [.NET](https://github.com/BingAds/BingAds-dotNet-SDK/releases/tag/v12.13.1), [Java](https://github.com/BingAds/BingAds-Java-SDK/releases/tag/v12.13.1), [Php](https://github.com/BingAds/BingAds-PHP-SDK/releases/tag/v0.12.13.1), and [Python](https://github.com/BingAds/BingAds-Python-SDK/releases/tag/v12.13.1) SDK version 12.13.1. 

## <a name="march2019"></a>March 2019
See below for Bing Ads API updates during this calendar month. 

- [Final Url Suffix](#finalurlsuffix-march2019)  
- [New Report Columns](#reportcolumns-march2019)  
- [Bing Ads Software Development Kit (SDK) Updates](#sdk-march2019)  

### <a name="finalurlsuffix-march2019"></a>Final Url Suffix
The final URL suffix will include tracking parameters that will be appended to the end of your landing page URL.

Final URL suffix is currently only available at the account, campaign, ad group, and keyword level for Phase 1 pilot customers ([GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) returns 533). Final URL suffix will be available in other entities for Phase 2 pilot customers ([GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) returns 566). Later this year Final URL suffix will be available in all of the above entities for all customers. 

#### <a name="bulk-finalurlsuffix-march2019"></a>Final Url Suffix for Bulk API
The *Final Url Suffix* field is added for future use in the following Bulk records. 
- [Account](../bulk-service/account.md#finalurlsuffix)  
- [Action Ad Extension](../bulk-service/action-ad-extension.md#finalurlsuffix)  
- [Ad Group](../bulk-service/ad-group.md#finalurlsuffix)  
- [Ad Group Product Partition](../bulk-service/ad-group-product-partition.md#finalurlsuffix)  
- [App Ad Extension](../bulk-service/app-ad-extension.md#finalurlsuffix)  
- [App Install Ad](../bulk-service/app-install-ad.md#finalurlsuffix)  
- [Campaign](../bulk-service/campaign.md#finalurlsuffix)  
- [Dynamic Search Ad](../bulk-service/dynamic-search-ad.md#finalurlsuffix)  
- [Expanded Text Ad](../bulk-service/expanded-text-ad.md#finalurlsuffix)  
- [Image Ad Extension](../bulk-service/image-ad-extension.md#finalurlsuffix)  
- [Keyword](../bulk-service/keyword.md#finalurlsuffix)  
- [Price Ad Extension](../bulk-service/price-ad-extension.md#finalurlsuffix)  
- [Responsive Ad](../bulk-service/responsive-ad.md#finalurlsuffix)  
- [Responsive Search Ad](../bulk-service/responsive-search-ad.md#finalurlsuffix)  
- [Sitelink Ad Extension](../bulk-service/sitelink-ad-extension.md#finalurlsuffix)  

#### <a name="campaign-finalurlsuffix-march2019"></a>Final Url Suffix for Campaign Management API
The *FinalUrlSuffix* element is added for future use in the following Campaign Management API objects. 
- [AccountProperty](../campaign-management-service/accountproperty.md#finalurlsuffix)  
- [ActionAdExtension](../campaign-management-service/actionadextension.md#finalurlsuffix)  
- [Ad](../campaign-management-service/ad.md#finalurlsuffix)  
- [AdGroup](../campaign-management-service/adgroup.md#finalurlsuffix)  
- [AppAdExtension](../campaign-management-service/appadextension.md#finalurlsuffix)  
- [BiddableAdGroupCriterion](../campaign-management-service/biddableadgroupcriterion.md#finalurlsuffix)  
- [Campaign](../campaign-management-service/campaign.md#finalurlsuffix)  
- [ImageAdExtension](../campaign-management-service/imageadextension.md#finalurlsuffix)  
- [Keyword](../campaign-management-service/keyword.md#finalurlsuffix)  
- [PriceAdExtension](../campaign-management-service/priceadextension.md#finalurlsuffix)  
- [SitelinkAdExtension](../campaign-management-service/sitelinkadextension.md#finalurlsuffix)  

### <a name="reportcolumns-march2019"></a>New Report Columns
The *CampaignType* column is added to the following reports. 
- [AdPerformanceReportColumn](../reporting-service/adperformancereportcolumn.md) 
- [AdGroupPerformanceReportColumn](../reporting-service/adgroupperformancereportcolumn.md) 
- [CampaignPerformanceReportColumn](../reporting-service/campaignperformancereportcolumn.md) 

### <a name="sdk-march2019"></a>Bing Ads Software Development Kit (SDK) Updates
The Bing Ads .NET, Java, Php, and Python SDKs are updated. For details please see release notes for Bing Ads [.NET](https://github.com/BingAds/BingAds-dotNet-SDK/releases/tag/v12.0.4), [Java](https://github.com/BingAds/BingAds-Java-SDK/releases/tag/v12.0.4), [Php](https://github.com/BingAds/BingAds-PHP-SDK/releases/tag/v0.12.0.4), and [Python](https://github.com/BingAds/BingAds-Python-SDK/releases/tag/v12.0.4) SDK version 12.0.4. 

## <a name="january2019"></a>January 2019
See below for Bing Ads API updates during this calendar month. 
 
- [Bing Ads Software Development Kit (SDK) Updates](#sdk-january2019)  

### <a name="sdk-january2019"></a>Bing Ads Software Development Kit (SDK) Updates
The Bing Ads .NET, Java, Php, and Python SDKs are updated. For details please see release notes for Bing Ads [.NET](https://github.com/BingAds/BingAds-dotNet-SDK/releases/tag/v12.0.3), [Java](https://github.com/BingAds/BingAds-Java-SDK/releases/tag/v12.0.3), [Php](https://github.com/BingAds/BingAds-PHP-SDK/releases/tag/v0.12.0.3), and [Python](https://github.com/BingAds/BingAds-Python-SDK/releases/tag/v12.0.3) SDK version 12.0.3. 

### <a name="biddingscheme-january2019"></a>Default Bid Strategy 
From January 28th, 2019 onward if you do not set BiddingScheme, then EnhancedCpc will be used by default for Search and Dynamic Search Ads campaigns. Prior to January 28th, 2019 if you did not set BiddingScheme for Search and Dynamic Search Ads campaigns, then ManualCpc was used by default. 

## <a name="december2018"></a>December 2018
See below for Bing Ads API updates during this calendar month. 
 
- [Bing Ads Software Development Kit (SDK) Updates](#sdk-december2018)  

### <a name="sdk-december2018"></a>Bing Ads Software Development Kit (SDK) Updates
The Bing Ads .NET, Java, Php, and Python SDKs are updated. For details please see release notes for Bing Ads [.NET](https://github.com/BingAds/BingAds-dotNet-SDK/releases/tag/v12.0.2), [Java](https://github.com/BingAds/BingAds-Java-SDK/releases/tag/v12.0.2), [Php](https://github.com/BingAds/BingAds-PHP-SDK/releases/tag/v0.12.0.2), and [Python](https://github.com/BingAds/BingAds-Python-SDK/releases/tag/v12.0.2) SDK version 12.0.2. 

## <a name="november2018"></a>November 2018
See below for Bing Ads API updates during this calendar month. 
 
- [Bing Ads Software Development Kit (SDK) Updates](#sdk-november2018)  
- [New Report Columns](#reportcolumns-november2018)  
- [Experiment Campaigns](#experiments-november2018)  

### <a name="sdk-november2018"></a>Bing Ads Software Development Kit (SDK) Updates
The Bing Ads .NET, Java, Php, and Python SDKs are updated. For details please see release notes for Bing Ads [.NET](https://github.com/BingAds/BingAds-dotNet-SDK/releases/tag/v12.0.1), [Java](https://github.com/BingAds/BingAds-Java-SDK/releases/tag/v12.0.1), [Php](https://github.com/BingAds/BingAds-PHP-SDK/releases/tag/v0.12.0.1), and [Python](https://github.com/BingAds/BingAds-Python-SDK/releases/tag/v12.0.1) SDK version 12.0.1. 

### <a name="reportcolumns-november2018"></a>New Report Columns
The *AbsoluteTopImpressionSharePercent* and *ClickSharePercent* columns are added to the following reports. 
- [AccountPerformanceReportColumn](../reporting-service/accountperformancereportcolumn.md) 
- [AdGroupPerformanceReportColumn](../reporting-service/adgroupperformancereportcolumn.md) 
- [CampaignPerformanceReportColumn](../reporting-service/campaignperformancereportcolumn.md) 
- [ProductDimensionPerformanceReportColumn](../reporting-service/productdimensionperformancereportcolumn.md) 
- [ProductPartitionPerformanceReportColumn](../reporting-service/productpartitionperformancereportcolumn.md) 

The *AssistedClicks* and *AssistedImpressions* columns are added to the following reports. 
- [ProductDimensionPerformanceReportColumn](../reporting-service/productdimensionperformancereportcolumn.md) 
- [ProductPartitionPerformanceReportColumn](../reporting-service/productpartitionperformancereportcolumn.md) 
- [ProductPartitionUnitPerformanceReportColumn](../reporting-service/productpartitionunitperformancereportcolumn.md) 
- [ProductSearchQueryPerformanceReportColumn](../reporting-service/productsearchqueryperformancereportcolumn.md) 

The *AdDescription2* column is added to the following reports. 
- [AdDynamicTextPerformanceReportColumn](../reporting-service/addynamictextperformancereportcolumn.md) 
- [AdPerformanceReportColumn](../reporting-service/adperformancereportcolumn.md) 

The *TitlePart3* column is added to the following reports. 
- [AdDynamicTextPerformanceReportColumn](../reporting-service/addynamictextperformancereportcolumn.md) 
- [AdExtensionByAdReportColumn](../reporting-service/adextensionbyadreportcolumn.md) 
- [AdPerformanceReportColumn](../reporting-service/adperformancereportcolumn.md) 

### <a name="experiments-november2018"></a>Experiment Campaigns
Service definitions for experiment campaigns are available in preview for pilot participants.

An experiment is where you split a Search campaign’s budget and traffic, and then run an A/B test during a limited date range.

> [!NOTE]
> Not everyone has this feature yet. If you don't, don't worry. It's coming soon.  

How would using a different bid strategy, or a different kind of targeting, affect your ad campaign's performance? Would it be better, worse, or basically the same? Now you can run an A/B test to find out!

With Bing Ads experiments, you create a duplicate of a search campaign that receives a split of your base campaign's budget and ad traffic. You can create up to 10 nonconcurrent experiments per base campaign. Then, you can:
- Try out changes in the experiment campaign.
- See how the experiment campaign performs compared to the base campaign.
- If you like the experiment's results, apply the changes to the base campaign or create a whole new campaign.

> [!IMPORTANT]
> Even if you do not use experiments, please take note of the experiment campaign business rules if your application is used by clients who do run experiments. 
> - The budget, budget type, and time zone of an experiment campaign cannot be updated. The budget and time zone of an experiment campaign are always inherited from the base campaign settings.  
> - If you want to change an experiment's budget, you will need to change the base campaign's budget. The change in value will then be split based on your experiment traffic split percent setting. 
> - An experiment campaign will have one new property that non-experiment campaigns do not have i.e., the experiment ID. You can determine whether the campaign is an independent or experiment campaign by checking the new [Experiment Id](../bulk-service/campaign.md#experimentid) field (Bulk service) or [ExperimentId](../campaign-management-service/campaign.md#experimentid) element (Campaign Management service). If the experiment ID is null or empty, then it is not an experiment campaign. If you use the Campaign Management service, the [ExperimentId](../campaign-management-service/campaign.md#experimentid) is not returned by default, so you'll need to explicitly set *ReturnAdditionalFields* via the [GetCampaignsByAccountId](../campaign-management-service/getcampaignsbyaccountid.md) and [GetCampaignsByIds](../campaign-management-service/getcampaignsbyids.md). 
> - Experiments are only available for Search campaigns. If the campaign uses a shared budget, then you cannot use it as the base campaign for an experiment.

You can manage experiment settings using the Bulk service ([Experiment Record](../bulk-service/experiment.md)) or Campaign Management service ([Experiment](../campaign-management-service/experiment.md)). You can manage regular (independent) campaigns and experiment campaigns using the Bulk service ([Campaign Record](../bulk-service/campaign.md)) or Campaign Management service ([Campaign](../campaign-management-service/campaign.md)). 


## <a name="october2018"></a>October 2018
See below for Bing Ads API updates during this calendar month. 
 
- [Bing Ads Software Development Kit (SDK) Updates](#sdk-october2018)  
- [Longer Expanded Text Ads](#expandedtextads-october2018)  
- [Paging for Media Meta Data](#mediametadatapaging-october2018)  
- [Dynamic Search Ads Source and Custom Label](#dsasource-october2018)  
- [Responsive Ad Type Filter for Reporting](#responsiveadfilter-october2018)  

### <a name="sdk-october2018"></a>Bing Ads Software Development Kit (SDK) Updates
The Bing Ads .NET, Java, Php, and Python SDKs are updated. For details please see release notes for Bing Ads [.NET](https://github.com/BingAds/BingAds-dotNet-SDK/releases/tag/v11.12.7), [Java](https://github.com/BingAds/BingAds-Java-SDK/releases/tag/v11.12.7), [Php](https://github.com/BingAds/BingAds-PHP-SDK/releases/tag/v0.11.12.7), and [Python](https://github.com/BingAds/BingAds-Python-SDK/releases/tag/v11.12.7) SDK version 11.12.7. 

### <a name="expandedtextads-october2018"></a>Longer Expanded Text Ads
The maximum length of the Expanded Text Ad Text field is increased from 80 to 90, or from 40 to 45 for double-width characters. 

The TextPart2 and TitlePart3 fields are added to expanded text ads. 

For more details see [Expanded Text Ad](../bulk-service/expanded-text-ad.md) (Bulk service) and [ExpandedTextAd](../campaign-management-service/expandedtextad.md) (Campaign Management service).


### <a name="mediametadatapaging-october2018"></a>Paging for Media Meta Data
The [PageInfo](../campaign-management-service/getmediametadatabyaccountid.md#pageinfo) element is added to the [GetMediaMetaDataByAccountId](../campaign-management-service/getmediametadatabyaccountid.md) operation. This optional request element determines the index and size of media meta data results per page. By default if this element is not specified, all media meta data in the account will be returned.

> [!TIP]
> As a best practice you should implement paging where results are limited to 1,000 per page. In a future version of the API if this element is not specified, the defaut page Index will be 0 and the default Size will be 1,000.

### <a name="dsasource-october2018"></a>Dynamic Search Ads Source and Custom Label
Dynamic Search Ads customers in the United States and the United Kingdom can now manage the page feeds targeting source and custom labels via Bing Ads API. 

You can set the page feeds targeting source with the Campaign Management service via the [DynamicSearchAdsSetting](../campaign-management-service/dynamicsearchadssetting.md) or with the Bulk service via the [Source](../bulk-service/campaign.md#source) field of a [Campaign](../bulk-service/campaign.md) record. 

You can set the page feeds custom label auto targets with the Campaign Management service via the [WebpageCondition](../campaign-management-service/webpagecondition.md) i.e., set the operand to [CustomLabel](../campaign-management-service/webpageconditionoperand.md#customlabel). You can set the page feeds custom label auto targets with the Bulk service via the the dynamic ad target condition and value fields of a [Ad Group Dynamic Search Ad Target](../bulk-service/ad-group-dynamic-search-ad-target.md), [Ad Group Negative Dynamic Search Ad Target](../bulk-service/ad-group-negative-dynamic-search-ad-target.md), or [Campaign Negative Dynamic Search Ad Target](../bulk-service/campaign-negative-dynamic-search-ad-target.md) record. 

> [!NOTE]
> Although you can manage the page feeds source and custom labels via Bing Ads API, page feeds upload is only supported through the Bing Ads web application. For more details about uploading page feeds, see the [About dynamic search ads page feeds](https://help.bingads.microsoft.com/#apex/3/en/60010/0) help article.

### <a name="responsiveadfilter-october2018"></a>Responsive Ad Type Filter for Reporting
The *ResponsiveAd* value is added to the [AdTypeReportFilter](../reporting-service/adtypereportfilter.md) value set. You can filter by ad type within the following report filters. 

- [AdDynamicTextPerformanceReportFilter](../reporting-service/addynamictextperformancereportfilter.md)  
- [AdPerformanceReportFilter](../reporting-service/adperformancereportfilter.md)  
- [KeywordPerformanceReportFilter](../reporting-service/keywordperformancereportfilter.md)  
- [ProductSearchQueryPerformanceReportFilter](../reporting-service/productsearchqueryperformancereportfilter.md)  
- [SearchQueryPerformanceReportFilter](../reporting-service/searchqueryperformancereportfilter.md)  

## <a name="september2018"></a>September 2018
See below for Bing Ads API updates during this calendar month. 
 
- [Bing Ads Software Development Kit (SDK) Updates](#sdk-september2018)   
- [Customer Id and Customer Name Report Columns](#customeridcustomername-september2018)  

### <a name="sdk-september2018"></a>Bing Ads Software Development Kit (SDK) Updates
The Bing Ads .NET, Java, Php, and Python SDKs are updated. For details please see release notes for Bing Ads [.NET](https://github.com/BingAds/BingAds-dotNet-SDK/releases/tag/v11.12.6), [Java](https://github.com/BingAds/BingAds-Java-SDK/releases/tag/v11.12.6), [Php](https://github.com/BingAds/BingAds-PHP-SDK/releases/tag/v0.11.12.6), and [Python](https://github.com/BingAds/BingAds-Python-SDK/releases/tag/v11.12.6) SDK version 11.12.6. 

### <a name="customeridcustomername-september2018"></a>Customer Id and Name Report Columns
The *CustomerId* and *CustomerName* columns are added to the following reports. 
- [AccountPerformanceReportColumn](../reporting-service/accountperformancereportcolumn.md) 
- [AdGroupPerformanceReportColumn](../reporting-service/adgroupperformancereportcolumn.md) 
- [AdPerformanceReportColumn](../reporting-service/adperformancereportcolumn.md) 
- [CampaignPerformanceReportColumn](../reporting-service/campaignperformancereportcolumn.md) 
- [DestinationUrlPerformanceReportColumn](../reporting-service/destinationurlperformancereportcolumn.md) 
- [DSASearchQueryPerformanceReportColumn](../reporting-service/dsasearchqueryperformancereportcolumn.md) 
- [ProductSearchQueryPerformanceReportColumn](../reporting-service/productsearchqueryperformancereportcolumn.md) 
- [SearchQueryPerformanceReportColumn](../reporting-service/searchqueryperformancereportcolumn.md) 

The *CustomerId* and *CustomerName* columns had already been available via the [ProductMatchCountReportColumn](../reporting-service/productmatchcountreportcolumn.md) prior this this month's release. 

## <a name="august2018"></a>August 2018
See below for Bing Ads API updates during this calendar month. 
 
- [Conflict Type for the Negative Keyword Conflict Report](#negativekeywordconflicttype-august2018)  
- [Ad Click Parallel Tracking](#adclickparalleltracking-august2018)   
- [Bing Ads Software Development Kit (SDK) Updates](#sdk-august2018)   
- [Customer Address](#customeraddress-august2018)  
- [Validate Address](#validateaddress-august2018)  
- [Entity Attributes for the Change History Report](#changehistoryreportentity-august2018)  
- [Profile Criteria for Campaigns](#campaignprofilecriteria-august2018)  
- [Similar Audiences for Remarketing Lists](#similaraudiences-august2018)  

### <a name="negativekeywordconflicttype-august2018"></a>Conflict Type for the Negative Keyword Conflict Report
The [ConflictType](../reporting-service/negativekeywordconflictreportcolumn.md#conflicttype) element is added to the [NegativeKeywordConflictReportColumn](../reporting-service/negativekeywordconflictreportcolumn.md) value set. 

Data in this download column represent the type of negative keyword conflict encountered. Some advertisers intentionally create negative keyword conflicts to block a portion of match type traffic. For example, if your phrase match keywords are "stereo plug," you might also choose "stereo plug" as an exact match negative keyword text to match only with this phrase. In this scenario, customers that are searching for specific items like "3.5mm stereo plug" or "gold stereo plug" would see ads for the "stereo plug" phrase match keyword, but customers searching for "stereo plug" wouldn’t see ads for the exact match keyword. If you are an advertiser who intentionally blocks a portion of match type traffic, you can use this column to filter out intentional negative keyword conflicts. If you're not, you should investigate and fix both types of conflicts.

### <a name="adclickparalleltracking-august2018"></a>Ad Click Parallel Tracking
Support for ad click parallel tracking is enabled for pilot customers. Parallel tracking lets you send users directly to your final URL while click measurement runs in the background. Parallel tracking reduces the time it takes for your landing page to load, increasing customer satisfaction with your ad and website (making conversions more likely!).

> [!IMPORTANT]
> Parallel tracking is only available for pilot customers ([GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) returns 474), and currently all other customers are opted out. During pilot you can enable and disable the feature i.e., set the property to *true* or *false*. By the end of calendar year 2019 all customers will be enabled for parallel tracking, and the value can only be set to *true*. 

You need to have {lpurl] or one of its variants in your URL's tracking template for parallel tracking to work. For more information see [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2-500).

You can manage parallel tracking via the [GetAccountProperties](../campaign-management-service/getaccountproperties.md) and [SetAccountProperties](../campaign-management-service/setaccountproperties.md) service operations. If the account property [Name](../campaign-management-service/accountproperty.md#name) element is set to [AdClickParallelTracking](../campaign-management-service/accountproperty.md#adclickparalleltracking), then the returned [Value](../campaign-management-service/accountproperty.md#value) can be either *true* or *false*. If the value is *true*, then parallel tracking is enabled.

### <a name="sdk-august2018"></a>Bing Ads Software Development Kit (SDK) Updates
The Bing Ads .NET, Java, Php, and Python SDKs are updated.
- Updated service proxies to support customer address, campaign level profile criteria, similar audiences for remarketing lists, and new change history report columns. 

### <a name="customeraddress-august2018"></a>Customer Address
The [CustomerAddress](../customer-management-service/customer.md#customeraddress) element is added back to the [Customer](../customer-management-service/customer.md) object. This element had been removed during the transition from Bing Ads API Version 11 to Version 12. Although you must set the account [BusinessAddress](../customer-management-service/advertiseraccount.md#businessaddress), the customer address is optional if your application has a dependency on it. Bing Ads does not use the customer address, and instead uses the account business address. 

### <a name="validateaddress-august2018"></a>Validate Address
The [ValidateAddress](../customer-management-service/validateaddress.md) operation is added. The operation determines whether or not the submitted address is valid for Bing Ads accounts. For Australia (AU), Canada (CA), and The United States (US), the operation validates whether or not you could ship something to the address. For all other countries basic address verification (AVS) is completed. 

### <a name="changehistoryreportentity-august2018"></a>Entity Attributes for the Change History Report
The [EntityId](../reporting-service/searchcampaignchangehistoryreportcolumn.md#entityid) and [EntityName](../reporting-service/searchcampaignchangehistoryreportcolumn.md#entityname) elements are added to the [SearchCampaignChangeHistoryReportColumn](../reporting-service/searchcampaignchangehistoryreportcolumn.md) value set. 

### <a name="campaignprofilecriteria-august2018"></a>Profile Criteria for Campaigns
Professional profile targeting via LinkedIn is coming soon to Dynamic Search Ads, Search, and Shopping campaigns. 

The Campaign Management service is updated to support the new campaign level profile criterion types i.e., the [CompanyName](../campaign-management-service/campaigncriteriontype.md#companyname), [Industry](../campaign-management-service/campaigncriteriontype.md#industry), and [JobFunction](../campaign-management-service/campaigncriteriontype.md#jobfunction) values are added to the [CampaignCriterionType](../campaign-management-service/campaigncriteriontype.md) value set. Use the existing [BiddableCampaignCriterion](../campaign-management-service/biddablecampaigncriterion.md) object with the corresponding operations e.g., [AddCampaignCriterions](../campaign-management-service/addcampaigncriterions.md) to manage campaign level criterions. The Campaign Management service already includes definitions for ad group level profile criterion types via the [AdGroupCriterionType](../campaign-management-service/adgroupcriteriontype.md) value set. Use the existing [BiddableAdGroupCriterion](../campaign-management-service/biddableadgroupcriterion.md) object with the corresponding operations e.g., [AddAdGroupCriterions](../campaign-management-service/addadgroupcriterions.md) to manage ad group level criterions. 

The Bulk service is updated to support the new profile criterion types i.e., upload and download the [Campaign Company Name Criterion](../bulk-service/campaign-company-name-criterion.md), [Campaign Industry Criterion](../bulk-service/campaign-industry-criterion.md), and [Campaign Job Function Criterion](../bulk-service/campaign-job-function-criterion.md) records in a Bulk file. Use the existing [CampaignTargetCriterions](../bulk-service/downloadentity.md#campaigntargetcriterions) value flag for Bulk download. The Bulk service already includes definitions for ad group level profile criterion types via the [Ad Group Company Name Criterion](../bulk-service/ad-group-company-name-criterion.md), [Ad Group Industry Criterion](../bulk-service/ad-group-industry-criterion.md), and [Ad Group Job Function Criterion](../bulk-service/ad-group-job-function-criterion.md) records in a Bulk file. Use the existing [AdGroupTargetCriterions](../bulk-service/downloadentity.md#adgrouptargetcriterions) value flag for Bulk download. 

### <a name="similaraudiences-august2018"></a>Similar Audiences for Remarketing Lists
Similar audiences for remarketing lists is coming soon. Bing Ads will automatically generate similar audiences for remarketing lists for pilot participants. You cannot create or edit the similar audiences for remarketing lists. If you delete the source remarketing list, then the similar audience will also be deleted. If a similar audience is associated with an ad group, then you cannot delete the source remarketing list.

The Campaign Management service is updated to support similar audiences for remarketing i.e., the [SimilarRemarketingList](../campaign-management-service/similarremarketinglist.md) object. Use the existing [GetAudiencesByIds](../campaign-management-service/getaudiencesbyids.md) operation to retrieve the similar audiences. Use the existing [AddAdGroupCriterions](../campaign-management-service/addadgroupcriterions.md), [DeleteAdGroupCriterions](../campaign-management-service/deleteadgroupcriterions.md), [GetAdGroupCriterionsByIds](../campaign-management-service/getadgroupcriterionsbyids.md), and [UpdateAdGroupCriterions](../campaign-management-service/updateadgroupcriterions.md) operations to manage ad group level associations for the similar audiences. 

> [!NOTE]
> Bulk service support for similar audiences for remarketing lists is coming soon. 

## <a name="july2018"></a>July 2018
See below for Bing Ads API updates during this calendar month. 

- [Bing Ads Software Development Kit (SDK) Updates](#sdk-july2018)   

### <a name="sdk-july2018"></a>Bing Ads Software Development Kit (SDK) Updates
The Bing Ads .NET, Java, Php, and Python SDKs are updated.
- Limited the scope to bingads.manage for access token requests. Previously the default scope was used, which can vary if a user granted your app permissions to multiple scopes. The Bing Ads SDKs only support the bingads.manage scope. 
- Updated the Customer Management proxies to support [LinkedAccountIds](#linkedaccountids-june2018) for agencies. For agency users the customer role can contain a list of linked accounts that the user can access as an agency on behalf of another customer.

## <a name="june2018"></a>June 2018
See below for Bing Ads API updates during this calendar month. 

- [Bing Ads Software Development Kit (SDK) Updates](#sdk-june2018)   
- [Linked Account Ids per Customer Role](#linkedaccountids-june2018)

### <a name="sdk-june2018"></a>Bing Ads Software Development Kit (SDK) Updates
The Bing Ads .NET, Java, and Python SDKs are updated to extend support for [Cooperative Bidding](product-ads.md#setup-cooperative) i.e., the BulkAdGroup now supports the coop setting. 

### <a name="linkedaccountids-june2018"></a>Linked Account Ids per Customer Role
The [LinkedAccountIds](../customer-management-service/customerrole.md#linkedaccountids) element is added to the [CustomerRole](../customer-management-service/customerrole.md) object. For agency users the element contains a list of linked accounts that the user can access as an agency on behalf of another customer. 

> [!IMPORTANT]
> The [CustomerRole](../customer-management-service/customerrole.md) objects that represent the user's permissions for agency-linked accounts will not be returned by default when you call the [GetUser](../customer-management-service/getuser.md) service operation. In other words by default the [GetUser](../customer-management-service/getuser.md) operation will only return *CustomerRole* objects for customers that the user can directly access without agency linking. To retrieve [CustomerRole](../customer-management-service/customerrole.md) objects that represent the user's permissions for agency-linked accounts you must set the optional [IncludeLinkedAccountIds](../customer-management-service/getuser.md#includelinkedaccountids) element to *True* when calling the [GetUser](../customer-management-service/getuser.md) operation.

## <a name="may2018"></a>May 2018
See below for Bing Ads API updates during this calendar month. 

- [Bing Ads Software Development Kit (SDK) Updates](#sdk-may2018)   
- [Microsoft Audience Network Preview](#audiencenetwork-may2018)  

### <a name="sdk-may2018"></a>Bing Ads Software Development Kit (SDK) Updates
The Bing Ads .NET, Java, PHP, and Python SDKs are updated to extend support for [Audience Ads](audience-ads.md). New bulk objects are added to the SDK for reading and writing Bulk file records e.g., BulkResponsiveAd and BulkResponsiveAdLabel. 

The Bing Ads .NET, Java, and Python SDKs are updated with retries for the 117 throttling error if encountered while polling for the status of a bulk or reporting operation. 

### <a name="audiencenetwork-may2018"></a>Microsoft Audience Network Preview
Support is added for the Microsoft Audience Network in preview. For details see [Audience Ads](audience-ads.md). For differences between version 11 and 12, see [Migrate to Version 12](migration-guide.md). 

## <a name="april2018"></a>April 2018
See below for Bing Ads API updates during this calendar month. 

- [Version 12 General Availability](#v12-april2018)  
- [Bing Ads Software Development Kit (SDK) Updates](#sdk-april2018)   
- [Product Match Count Report](#reporting-productmatchcount-april2018)   

### <a name="v12-april2018"></a>Version 12 General Availability
Bing Ads API version 12 is now generally available. With the availability of Bing Ads API version 12, version 11 is deprecated and will sunset by October 31, 2018. For more details, see [Migrate to Version 12](migration-guide.md).

### <a name="sdk-april2018"></a>Bing Ads Software Development Kit (SDK) Updates
The Bing Ads .NET, Java, PHP, and Python SDKs are updated to support Bing Ads API Version 12. 

#### <a name="netsdk-april2018"></a>Bing Ads .NET SDK
The Bing Ads .NET SDK is updated to support .NET Standard 2.0. This will enable you to choose from a variety of platforms e.g., .NET Core or .NET Framework 4.6.1. For more information on .NET Standard and how it relates to other .NET frameworks, refer to this article on [.NET Standard](https://docs.microsoft.com/en-us/dotnet/standard/net-standard). 

#### <a name="pythonsdk-april2018"></a>Bing Ads Python SDK
The version parameter is now required when creating each ServiceClient. Previously the version was optional and defaulted to version 11. The version parameter is moved to the second position between the service client name and the authorization data. 

The file_type parameter now defaults to 'Csv' as an *str* datatype instead of the DownloadFileType for BulkFileReader, BulkServiceManager, DownloadParameters and SubmitDownloadParameters. You can set 'Tsv' if you prefer the tab separated file format type.

### <a name="reporting-productmatchcount-april2018"></a>Product Match Count Report
The [ProductMatchCountReportRequest](../reporting-service/productmatchcountreportrequest.md) is added for Bing Shopping campaigns. You can include details in the report such as impressions, clicks, and spend that you can use to see if you are covering and bidding across your Bing shopping campaigns inventory. Note that this only provides the matched data for your current Product Group level, and you cannot obtain historical views.

## <a name="march2018"></a>March 2018
See below for Bing Ads API updates during this calendar month. 

- [Version 12 Sandbox Beta](#v12-march2018)  

### <a name="v12-march2018"></a>Version 12 Sandbox Beta
The sandbox endpoints for Bing Ads API version 12 are available in beta. The interfaces are subject to change prior to general availability. For more details, see [Migrate to Version 12](migration-guide.md).
