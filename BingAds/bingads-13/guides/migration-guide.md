---
title: "Migrate to Bing Ads API Version 13"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Get details about migrating to Bing Ads API version 13.
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# Migrate to Version 13
> [!IMPORTANT]
> With the availability of Bing Ads API version 13, version 12 is deprecated and will sunset by October 31, 2019. 

The sections below describe changes from version 12 to version 13 of the [Ad Insight](../ad-insight-service/ad-insight-service-reference.md), [Bulk](../bulk-service/bulk-service-reference.md), [Campaign Management](../campaign-management-service/campaign-management-service-reference.md), [Customer Billing](../customer-billing-service/customer-billing-service-reference.md), [Customer Management](../customer-management-service/customer-management-service-reference.md), and [Reporting](../reporting-service/reporting-service-reference.md) services. Some [authentication](#authentication) updates are required for all services. 

## <a name="adinsight"></a>Ad Insight

### <a name="adinsight-breakingchanges"></a>Breaking Changes

#### <a name="adinsight-proxy-client"></a>Proxy Client
Update your proxy client to use the new endpoint address and namespace.

The target namespace is `https://bingads.microsoft.com/AdInsight/v13`.

The production endpoint is [https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v13/AdInsightService.svc](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v13/AdInsightService.svc).

The sandbox endpoint is [https://adinsight.api.sandbox.bingads.microsoft.com/Api/Advertiser/AdInsight/v13/AdInsightService.svc](https://adinsight.api.sandbox.bingads.microsoft.com/Api/Advertiser/AdInsight/v13/AdInsightService.svc).

#### <a name="adinsight-datacontractnamespace"></a>Data Contract Namespace
Previously in version 12, the data contract namespace for some entities had varied from the Ad Insight target namespace. If you used any of the following version 12 namespaces, you must insteaed use `https://bingads.microsoft.com/AdInsight/v13` in version 13.
- Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.SearchParameters
- Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Common
- Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions
- Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity

Clients who encode the SOAP envelope e.g. PHP clients who encode a `SoapVar` for [DateRangeSearchParameter](../ad-insight-service/daterangesearchparameter.md), you'll need to update to the Ad Insight Version 13 target namespace i.e., `https://bingads.microsoft.com/AdInsight/v13`.

Bing Ads Python SDK clients will need to update several namespace prefixes for the [SUDS](get-started-python.md#suds) client factory objects e.g., if you used *ns4:DateRangeSearchParameter* in Bing Ads API Version 12 you'll use *DateRangeSearchParameter* (without the 'ns4' prefix) in version 13. See [Using SUDS](get-started-python.md#suds) for details about how to determine the namespace prefix.

## <a name="bulk"></a>Bulk

### <a name="bulk-breakingchanges"></a>Breaking Changes

#### <a name="bulk-proxy-client"></a>Proxy Client
Update your proxy client to use the new endpoint address and namespace.

The target namespace is `https://bingads.microsoft.com/CampaignManagement/v13`.

The production endpoint is [https://bulk.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/BulkService.svc](https://bulk.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/BulkService.svc).

The sandbox endpoint is [https://bulk.api.sandbox.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/BulkService.svc](https://bulk.api.sandbox.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/BulkService.svc).  

#### <a name="bulk-responsivead-imageassets"></a>Responsive Ad Image Assets
The Landscape Image Media Id, Landscape Logo Media Id, Square Image Media Id, and Square Logo Media Id columns are deprecated from the [Responsive Ad](../bulk-service/responsive-ad.md) record. They will still be visible in the download file, although since they will be removed in a future version you should not take any dependencies on these columns. Please use the [Images](../bulk-service/responsive-ad.md#images) column instead. 

#### <a name="bulk-entityperformancedata"></a>Entity Performance Data
Bulk download of performance data was previously sunset in version 12. Now in version 13 the EntityPerformanceData value of the [DataScope](../bulk-service/datascope.md) value set is removed from the service contract. Also the *Date* and *PerformanceStatsDateRange* objects and *ReportTimePeriod* value set are removed If you want data aggregated by day, week, or month, you can use the Bing Ads Reporting API. For more details see [Reports](reports.md).

## <a name="campaign"></a>Campaign Management

### <a name="campaign-breakingchanges"></a>Breaking Changes

#### <a name="campaign-proxy-client"></a>Proxy Client
Update your proxy client to use the new endpoint address and namespace.

The target namespace is `https://bingads.microsoft.com/CampaignManagement/v13`.

The production endpoint is [https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc).

The sandbox endpoint is [https://campaign.api.sandbox.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc](https://campaign.api.sandbox.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc).

#### <a name="campaign-responsivead-imageassets"></a>Responsive Ad Image Assets
The LandscapeImageMediaId, LandscapeLogoMediaId, SquareImageMediaId, and SquareLogoMediaId elements are removed from the [ResponsiveAd](../campaign-management-service/responsivead.md) object. You must use the [Images](../campaign-management-service/responsivead.md#images) element instead. 

#### <a name="campaign-responsivead-textassets"></a>Responsive Ad Text Assets
If you used the *LongHeadline* string element in version 12 you should use the [LongHeadlineString](../campaign-management-service/responsivead.md#longheadlinestring) (string) element in version 13. The data type of [LongHeadline](../campaign-management-service/responsivead.md#longheadline) is updated from string to [AssetLink](../campaign-management-service/assetlink.md). This asset link is reserved for future use. 

The [Headlines](../campaign-management-service/responsivead.md#headlines) and [Descriptions](../campaign-management-service/responsivead.md#descriptions) asset link lists are added for future use. More details will be announced during calendar year 2019. 

#### <a name="campaign-getmediametadatabyaccountid"></a>Default Paging for GetMediaMetaDataByAccountId
If the [PageInfo](../campaign-management-service/getmediametadatabyaccountid.md#pageinfo) element is not set when you call the [GetMediaMetaDataByAccountId](../campaign-management-service/getmediametadatabyaccountid.md) operation, the defaut page Index will be 0 and the default Size will be 1,000. In version 12 if PageInfo was not set, all media meta data in the account would be returned. 

#### <a name="campaign-criterion-bid-ignored"></a>Criterion Bid Ignored for Invalid Data Type
For both version 12 and 13 when adding and updating a [BiddableCampaignCriterion](../campaign-management-service/biddablecampaigncriterion.md), the derived [CriterionBid](../campaign-management-service/criterionbid.md) object type requirements vary depending upon the context of the derived [Criterion](../campaign-management-service/criterion.md) object type that it is paired with. For example, if the inherited [Criterion](../campaign-management-service/biddablecampaigncriterion.md#criterion) is a [ProductScope](../campaign-management-service/productscope.md) criterion, then you should use a [FixedBid](../campaign-management-service/fixedbid.md) object (not a [BidMultiplier](../campaign-management-service/bidmultiplier.md)). 

In version 13 if you do not use the correct [Criterion](../campaign-management-service/criterion.md) object, then your requested bid will be ignored: If the bid is required, the operation will fail; If the bid is optional, the default bid will be used.

In version 12 if you do not use the correct [Criterion](../campaign-management-service/criterion.md) object, then your requested bid would have been honored; however, when you retrieve the object later the correct type is returned. In other words the data type that you set is not the same as the data type retrieved. 

This change from version 12 to version 13 only applies to campaign level biddable criterions. For both version 12 and 13 biddable ad group criterions, if you do not use the correct [Criterion](../campaign-management-service/criterion.md) object, then your requested bid will be ignored: If the bid is required, the operation will fail; If the bid is optional, the default bid will be used.

#### <a name="campaign-keyword-bid"></a>Optional Keyword Bid
When you call the [AddKeywords](../campaign-management-service/addkeywords.md) operation, the [Bid](../campaign-management-service/keyword.md#bid) element of the [Keyword](../campaign-management-service/keyword.md) is optional. Previously in version 12, the bid was required to add keywords. If you want to inherit the default ad group bid for the keyword and match type, then you can leave the keyword bid empty.  

#### <a name="campaign-negativekeyword-matchtype"></a>Negative Keyword Match Type
The [MatchType](../campaign-management-service/negativekeyword.md#matchtype) element of the [NegativeKeyword](../campaign-management-service/negativekeyword.md) is nillable. If you had previously taken a dependency on the default [MatchType](../campaign-management-service/matchtype.md) value in version 12 i.e., Exact, then you must explicitly set this required element in version 13. 

#### <a name="campaign-dynamicsearchads-source"></a>Dynamic Search Ads Source
The *Source* element of the [DynamicSearchAdsSetting](../campaign-management-service/dynamicsearchadssetting.md) is nillable. The *IncludeDynamicSearchAdsSource* element is removed from the [AddCampaigns](../campaign-management-service/addcampaigns.md) and [UpdateCampaigns](../campaign-management-service/updatecampaigns.md) request messages. If you are enabled for page feeds, then in version 13 you can set the Source. 

#### <a name="campaign-description"></a>Campaign Description
The *Description* element is removed from the [Campaign](../campaign-management-service/campaign.md) object. You can still use the [Name](../campaign-management-service/campaign.md) element to provide a unique campaign name. 

#### <a name="campaign-returnadditionalfields"></a>Return Additional Fields
The *ReturnAdditionalFields* element is removed from the [GetAdExtensionsAssociations](../campaign-management-service/getadextensionsassociations.md), [GetAdExtensionsByIds](../campaign-management-service/getadextensionsbyids.md), [GetAdGroupCriterionsByIds](../campaign-management-service/getadgroupcriterionsbyids.md),  [GetAdGroupsByCampaignId](../campaign-management-service/getadgroupsbycampaignid.md), [GetAdGroupsByIds](../campaign-management-service/getadgroupsbyids.md), [GetAdsByAdGroupId](../campaign-management-service/getadsbyadgroupid.md), [GetAdsByEditorialStatus](../campaign-management-service/getadsbyeditorialstatus.md), [GetAdsByIds](../campaign-management-service/getadsbyids.md), [GetCampaignsByAccountId](../campaign-management-service/getcampaignsbyaccountid.md), [GetCampaignsByIds](../campaign-management-service/getcampaignsbyids.md), [GetKeywordsByAdGroupId](../campaign-management-service/getkeywordsbyadgroupid.md), [GetKeywordsByEditorialStatus](../campaign-management-service/getkeywordsbyeditorialstatus.md), and [GetKeywordsByIds](../campaign-management-service/getkeywordsbyids.md) request messages. All elements of each ad, ad extension, ad group, biddable ad group criterion, campaign, and keyword are returned by default. 

In parallel the related AdAdditionalField, AdExtensionAdditionalField, AdGroupAdditionalField, AdGroupCriterionAdditionalField, CampaignAdditionalField, and KeywordAdditionalField value sets are removed. 

#### <a name="campaign-ismigrated"></a>Target Migration Completed
The migration from a shared target to exclusive campaign and ad group target criteria was previously completed. The IsMigrated element is now removed from the response of the [AddAdGroupCriterions](../campaign-management-service/addadgroupcriterions.md), [UpdateAdGroupCriterions](../campaign-management-service/updateadgroupcriterions.md), [AddCampaignCriterions](../campaign-management-service/addcampaigncriterions.md), and [UpdateCampaignCriterions](../campaign-management-service/updatecampaigncriterions.md) operations.

### <a name="campaign-newfeatures"></a>New Features

#### <a name="campaign-bidstrategytypes"></a>New Bid Strategy Types
The [MaxRoasBiddingScheme](../campaign-management-service/maxroasbiddingscheme.md) and [TargetRoasBiddingScheme](../campaign-management-service/targetroasbiddingscheme.md) bid strategy types are added for future use in version 13. 

#### <a name="campaign-customershare"></a>Customer Share
The CustomerShare element is added to the [Audience](../campaign-management-service/audience.md) and [UetTag](../campaign-management-service/uettag.md) objects. This element is reserved for future use. 

#### <a name="campaign-excludefrombidding"></a>Conversion Goal Exclude From Bidding
The ExcludeFromBidding element is added to the [ConversionGoal](../campaign-management-service/conversiongoal.md) object. This element is reserved for future use. 

## <a name="billing"></a>Customer Billing

### <a name="billing-breakingchanges"></a>Breaking Changes

#### <a name="billing-proxy-client"></a>Proxy Client
Update your proxy client to use the new endpoint address and namespace.

The target namespace is `https://bingads.microsoft.com/Billing/v13`.

The production endpoint is [https://clientcenter.api.bingads.microsoft.com/Api/Billing/v13/CustomerBillingService.svc](https://clientcenter.api.bingads.microsoft.com/Api/Billing/v13/CustomerBillingService.svc).

The sandbox endpoint is [https://clientcenter.api.sandbox.bingads.microsoft.com/Api/Billing/v13/CustomerBillingService.svc](https://clientcenter.api.sandbox.bingads.microsoft.com/Api/Billing/v13/CustomerBillingService.svc).

#### <a name="billing-insertionorder"></a>Insertion Order Object
Several properties are added to the [InsertionOrder](../customer-billing-service/insertionorder.md) object. 
- The [IsInSeries](../customer-billing-service/insertionorder.md#isinseries), [SeriesFrequencyType](../customer-billing-service/insertionorder.md#seriesfrequencytype), and [SeriesName](../customer-billing-service/insertionorder.md#seriesname) elements are added for recurring insertion orders. You can retrieve but with very few exceptions cannot add or update an insertion order series via the Bing Ads API. To manage recurring insertion orders in the Bing Ads web application, see the [How do I create and edit an insertion order?](https://help.bingads.microsoft.com/#apex/3/en/52094/0) help article.  
- The [BudgetRemaining](../customer-billing-service/insertionorder.md#budgetremaining), [BudgetRemainingPercent](../customer-billing-service/insertionorder.md#budgetremainingpercent), [BudgetSpent](../customer-billing-service/insertionorder.md#budgetspent), and [BudgetSpentPercent](../customer-billing-service/insertionorder.md#budgetspentpercent) elements are added for convenience. 
- The [AccountNumber](../customer-billing-service/insertionorder.md#accountnumber) is added for convenience. 
- The Queued status value is added to the [InsertionOrderStatus](../customer-billing-service/insertionorderstatus.md) value set. This value is reserved for future use. 

The *BalanceAmount* element is removed i.e., replaced by the The [BudgetRemaining](../customer-billing-service/insertionorder.md#budgetremaining) element. 

#### <a name="billing-getinsertionordersbyaccount"></a>GetInsertionOrdersByAccount is Removed
The GetInsertionOrdersByAccount operation is removed. You can use [SearchInsertionOrders](../customer-billing-service/searchinsertionorders.md) in version 13. 

## <a name="customer"></a>Customer Management

### <a name="customer-breakingchanges"></a>Breaking Changes

#### <a name="customer-proxy-client"></a>Proxy Client
Update your proxy client to use the new endpoint address and namespace.

The target namespace is `https://bingads.microsoft.com/Customer/v13`.

The production endpoint is [https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v13/CustomerManagementService.svc](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v13/CustomerManagementService.svc).

The sandbox endpoint is [https://clientcenter.api.sandbox.bingads.microsoft.com/Api/CustomerManagement/v13/CustomerManagementService.svc](https://clientcenter.api.sandbox.bingads.microsoft.com/Api/CustomerManagement/v13/CustomerManagementService.svc).

#### <a name="customer-includecustomeraddress"></a>Customer Address 
In version 13 the CustomerAddress element will be included in all returned [Customer](../customer-management-service/customer.md) objects by default. You do not need to explicitly request this element. The *IncludeCustomerAddress* element is removed from the [GetCustomer](../customer-management-service/getcustomer.md) and [SearchCustomers](../customer-management-service/searchcustomers.md) request messages.    

#### <a name="customer-includelinkedaccountids"></a>Linked Account Ids 
In version 13 the LinkedAccountIds element will be included in all returned [CustomerRole](../customer-management-service/customerrole.md) objects by default. You do not need to explicitly request this element. The *IncludeLinkedAccountIds* element is removed from the [GetUser](../customer-management-service/getuser.md) request message. 

#### <a name="customer-taxinformation"></a>Tax Information for Australia and Brazil 
The TaxId and TaxType keys are no longer available when you set account [TaxInformation](../customer-management-service/advertiseraccount.md#taxinformation) for Australia and Brazil. For Australia use AUGSTNumber as the key and set the value to your tax identifier. For Brazil the possible keys are CCM, CPF, and CNPJ. 

|Description|Version 12|Version 13|
|-----|-----|-----|
|Accounts in Australia|TaxId=YourTaxId|AUGSTNumber=YourTaxId|
|Business Accounts in Brazil|TaxId=YourTaxId;TaxType=Business|CPNJ=YourTaxId|
|Personal Accounts in Brazil|TaxId=YourTaxId;TaxType=Personal|CPF=YourTaxId|

For business accounts within the city of Sao Paulo, Brazil there is no change to the CCM key between versions 12 and 13. 

### <a name="customer-newfeatures"></a>New Features

#### <a name="customer-role-customerlinkpermission"></a>Customer Role Link Permission 
The CustomerLinkPermission element is added to the [CustomerRole](../customer-management-service/customerrole.md) object. This element is reserved for future use. 

## <a name="reporting"></a>Reporting

### <a name="reporting-breakingchanges"></a>Breaking Changes

#### <a name="reporting-proxy-client"></a>Proxy Client
Update your proxy client to use the new endpoint address and namespace.

The target namespace is `https://bingads.microsoft.com/Reporting/v13`.

The production endpoint is [https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v13/ReportingService.svc](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v13/ReportingService.svc).

The sandbox endpoint is [https://reporting.api.sandbox.bingads.microsoft.com/Api/Advertiser/Reporting/v13/ReportingService.svc](https://reporting.api.sandbox.bingads.microsoft.com/Api/Advertiser/Reporting/v13/ReportingService.svc).  

#### <a name="reporting-productmatchcount-requiredcolumns"></a>Required Columns for ProductMatchCountReportRequest
The required columns are updated when submitting the [ProductMatchCountReportRequest](../reporting-service/productmatchcountreportrequest.md). In version 13 the AccountName, CampaignName, MatchedProductsAtProductGroup, and ProductGroup columns are required.

Previously in version 12 in addition to the AccountName and CampaignName requirement, one or more of the MatchedProductsAtAdGroup, MatchedProductsAtCampaign, or MatchedProductsAtProductGroup performance statistics columns were required. 

#### <a name="reporting-languagereportfilter"></a>Language Report Filter
The [LanguageReportFilter](../reporting-service/languagereportfilter.md) value set is added. The LanguageCode (string) element is replaced by the Languages ([LanguageReportFilter](../reporting-service/languagereportfilter.md)) element in the following report filters. 
- [AdDynamicTextPerformanceReportFilter](../reporting-service/addynamictextperformancereportfilter.md)
- [AdGroupPerformanceReportFilter](../reporting-service/adgroupperformancereportfilter.md)
- [AdPerformanceReportFilter](../reporting-service/adperformancereportfilter.md)
- [AgeGenderAudienceReportFilter](../reporting-service/agegenderaudiencereportfilter.md)
- [DestinationUrlPerformanceReportFilter](../reporting-service/destinationurlperformancereportfilter.md)
- [DSAAutoTargetPerformanceReportFilter](../reporting-service/dsaautotargetperformancereportfilter.md)
- [DSACategoryPerformanceReportFilter](../reporting-service/dsacategoryperformancereportfilter.md)
- [DSASearchQueryPerformanceReportFilter](../reporting-service/dsasearchqueryperformancereportfilter.md)
- [GeographicPerformanceReportFilter](../reporting-service/geographicperformancereportfilter.md)
- [KeywordPerformanceReportFilter](../reporting-service/keywordperformancereportfilter.md)
- [ProductDimensionPerformanceReportFilter](../reporting-service/productdimensionperformancereportfilter.md)
- [ProductPartitionPerformanceReportFilter](../reporting-service/productpartitionperformancereportfilter.md)
- [ProductPartitionUnitPerformanceReportFilter](../reporting-service/productpartitionunitperformancereportfilter.md)
- [ProductSearchQueryPerformanceReportFilter](../reporting-service/productsearchqueryperformancereportfilter.md)
- [ProfessionalDemographicsAudienceReportFilter](../reporting-service/professionaldemographicsaudiencereportfilter.md)
- [PublisherUsagePerformanceReportFilter](../reporting-service/publisherusageperformancereportfilter.md)
- [SearchQueryPerformanceReportFilter](../reporting-service/searchqueryperformancereportfilter.md)
- [ShareOfVoiceReportFilter](../reporting-service/shareofvoicereportfilter.md)
- [UserLocationPerformanceReportFilter](../reporting-service/userlocationperformancereportfilter.md)

#### <a name="reporting-reportlanguage"></a>French Report Headers
Support for downloading a report with headers in French is removed. Only English headers are supported in version 13. The *Language* element is removed from the [ReportRequest](../reporting-service/reportrequest.md) object, and the *ReportLanguage* value set is removed. 

#### <a name="reporting-agegenderdemographicreport"></a>Removed AgeGenderDemographicReportRequest
The AgeGenderDemographicReportRequest is removed. Instead you can use the [AgeGenderAudienceReportRequest](../reporting-service/agegenderaudiencereportrequest.md). 

#### <a name="reporting-score-unavailable"></a>Dash for Unavailable Quality Score
In version 13 if the quality score was not computed the data returned will be "-" (dash) in the AdRelevance, ExpectedCtr, HistoricalAdRelevance, HistoricalExpectedCtr, HistoricalLandingPageExperience, HistoricalQualityScore, LandingPageExperience, and QualityScore columns. In version 12 the value of "0" (zero) had been returned. These columns are available in the [AdGroupPerformanceReportColumn](../reporting-service/adgroupperformancereportcolumn.md), [CampaignPerformanceReportColumn](../reporting-service/campaignperformancereportcolumn.md), [KeywordPerformanceReportColumn](../reporting-service/keywordperformancereportcolumn.md), and [ShareOfVoiceReportColumn](../reporting-service/shareofvoicereportcolumn.md) value sets.

#### <a name="reporting-impressionshare"></a>Removed Some Impression Share Columns
The ImpressionLostToAdRelevancePercent, ImpressionLostToBidPercent, ImpressionLostToExpectedCtrPercent, and ImpressionLostToRelevancePercent columns are removed from the [AccountPerformanceReportColumn](../reporting-service/accountperformancereportcolumn.md), [AdGroupPerformanceReportColumn](../reporting-service/adgroupperformancereportcolumn.md), [CampaignPerformanceReportColumn](../reporting-service/campaignperformancereportcolumn.md), and [ShareOfVoiceReportColumn](../reporting-service/shareofvoicereportcolumn.md) value sets. 

#### <a name="reporting-averagecpp-clickcalls"></a>Removed AverageCpp, ClickCalls, and ManualCalls Columns
The AverageCpp, ClickCalls, and ManualCalls columns are removed from the [AccountPerformanceReportColumn](../reporting-service/accountperformancereportcolumn.md), [AdGroupPerformanceReportColumn](../reporting-service/adgroupperformancereportcolumn.md) and [CampaignPerformanceReportColumn](../reporting-service/campaignperformancereportcolumn.md) value sets. 

#### <a name="reporting-calldetailreportcolumns"></a>Removed CallStatus and CallTypeName Columns
The CallStatus and CallTypeName columns are removed from the [CallDetailReportColumn](../reporting-service/calldetailreportcolumn.md) value set. Bing Ads stopped charging for manual calls to a tracked number on March 12, 2014. 
