---
title: "Migrating to Bing Ads API Version 11"
ms.service: "bing-ads"
ms.topic: "article"
ms.date: 11/01/2017
author: "eric-urban"
ms.author: "eur"
description: Get details about migrating to Bing Ads API version 11.
---
# Migrating to Bing Ads API Version 11
All Bing Ads API SOAP web services are available with Version 11.   

> [!IMPORTANT]
> With the availability of Bing Ads API version 11, the previous versions of the API (v10 for Ad Insight, Bulk, and Campaign Management services and v9 for Customer Billing, Customer Management, and Reporting services) are sunset as of October 31st. 

The sections below describe changes from version 10 to version 11 of the [Ad Insight](~/ad-insight-service/ad-insight-service-reference.md), [Bulk](~/bulk-service/bulk-service-reference.md), and [Campaign Management](~/campaign-management-service/campaign-management-service-reference.md) services, and changes from version 9 to version 11 of the [Customer Billing](~/customer-billing-service/customer-billing-service-reference.md), [Customer Management](~/customer-management-service/customer-management-service-reference.md), and [Reporting](~/reporting-service/reporting-service-reference.md) services.

## <a name="adinsight"></a>Ad Insight

### Breaking Changes

#### Proxy Client

Update your proxy client to use the new endpoint address and namespace.

The namespace is `https://bingads.microsoft.com/AdInsight/v11`.

The production endpoint is [https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc).

The sandbox endpoint is [https://adinsight.api.sandbox.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc](https://adinsight.api.sandbox.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc).

#### <a name="adinsight-monthlybudget"></a>Campaign Monthly Budget
The *MonthlyBudgetSpendUntilDepleted* value is removed from the the [BudgetLimitType](~/ad-insight-service/budgetlimittype.md) value set. Previously the [GetBudgetOpportunities](~/ad-insight-service/getbudgetopportunities.md) operation would return monthly budget opportunities for campaigns using monthly budgets. Monthly budgets are no longer supported in Bing Ads. 


## <a name="bulk"></a>Bulk

### Breaking Changes

#### Proxy Client

Update your proxy client to use the new endpoint address and namespace.

The namespace is `https://bingads.microsoft.com/CampaignManagement/v11`.

The production endpoint is [https://bulk.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/BulkService.svc](https://bulk.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/BulkService.svc).

The sandbox endpoint is [https://bulk.api.sandbox.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/BulkService.svc](https://bulk.api.sandbox.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/BulkService.svc).

#### <a name="bulk-downloadentities"></a>Download Entities
The *DownloadEntities* request element replaces the *Entities* request element for the [DownloadCampaignsByAccountIds](~/bulk-service/downloadcampaignsbyaccountids.md) and [DownloadCampaignsByCampaignIds](~/bulk-service/downloadcampaignsbycampaignids.md) operations. The *DownloadEntities* element accepts a list of [DownloadEntity](~/bulk-service/downloadentity.md) values instead of a flag set used in Bing Ads API version 10. The *BulkDownloadEntity* value set is removed. 

#### <a name="bulk-formatversion5"></a>Format Version 5.0

Support for Bulk file format version 4.0 is removed. Bing Ads API Version 11 only supports format version 5.0. When calling the [DownloadCampaignsByAccountIds](~/bulk-service/downloadcampaignsbyaccountids.md) and [DownloadCampaignsByCampaignIds](~/bulk-service/downloadcampaignsbycampaignids.md) operations you must specify *5.0* in the *FormatVersion* request element. When uploading a bulk file, you must specify 5.0 in the *Name* field of the [Format Version](~/bulk-service/format-version.md) record. Changes to records between format version 4.0 and 5.0 are described in more detail in the following sections.

#### <a name="bulk-targetcriterions"></a>Upgrade from Targets to Criterions
Instead of using targets to show your ads based on age, day and time, device, gender, and location, starting with Bing Ads API version 11 you must use criterions. Partial update of target criterions is supported in Bing Ads API version 11. The following changes are required to upgrade from targets to criterions. 
  * Replaced all target records with criterion records. For example the *Ad Group Age Target* record is replaced with the [Ad Group Age Criterion](~/bulk-service/ad-group-age-criterion.md) record. You can download the new criterion records using the *AdGroupTargetCriterions* and *CampaignTargetCriterions* values of the [DownloadEntity](~/bulk-service/downloadentity.md) value set. 
  * The [Ad Group Age Criterion](~/bulk-service/ad-group-age-criterion.md) and [Campaign Age Criterion](~/bulk-service/campaign-age-criterion.md) records support new values in the *Target* field: *EighteenToTwentyFour*, *TwentyFiveToThirtyFour*, *ThirtyFiveToFortyNine*, *FiftyToSixtyFour*, and *SixtyFiveAndAbove*. The upper bound of each range previously supported in format version 4.0 were not inclusive, for example *EighteenToTwentyFive* would only target ages eighteen through twenty-four. The values in format version 5.0 match the effective target range that remains unchanged. 
  * If an ad group or campaign has any device criterion, then it must have bids for all three device types. Please note this change when adding and updating [Ad Group DeviceOS Criterion](~/bulk-service/ad-group-deviceos-criterion.md) and [Campaign DeviceOS Criterion](~/bulk-service/campaign-deviceos-criterion.md) records. For example you cannot have a campaign that only has one [Campaign DeviceOS Criterion](~/bulk-service/campaign-deviceos-criterion.md) record. If the campaign has any device criterion then it must have three [Campaign DeviceOS Criterion](~/bulk-service/campaign-deviceos-criterion.md) records, each with corresponding supported bids for *Computers*, *Smartphones*, and *Tablets*. Previously in format version 4.0 the missing records were added automatically with bids set to '0' (zero).  
  * The [Ad Group Location Criterion](~/bulk-service/ad-group-location-criterion.md) and [Campaign Location Criterion](~/bulk-service/campaign-location-criterion.md) records support location identifiers in the *Target* field, instead of the location codes that were accepted by the corresponding format version 4.0 target records. The location identifier corresponds to the *ID* field of the geographical locations file. For more information, see [Geographical Location Codes](~/guides/geographical-location-codes.md) and [GetGeoLocationsFileUrl](~/campaign-management-service/getgeolocationsfileurl.md).
  * The *Sub Type* field for [Ad Group Location Criterion](~/bulk-service/ad-group-location-criterion.md) and [Campaign Location Criterion](~/bulk-service/campaign-location-criterion.md) records can include these values: *City*, *Country*, *MetroArea*, *PostalCode*, and *State*. The *Sub Type* field in the Bulk file format version 4.0 target records included these values (with spaces between words): *City*, *Country*, *Metro Area*, *Postal Code*, and *State*. 
  * The *Physical Intent* field is not available in the [Ad Group Location Criterion](~/bulk-service/ad-group-location-criterion.md), [Campaign Location Criterion](~/bulk-service/campaign-location-criterion.md), [Ad Group Radius Criterion](~/bulk-service/ad-group-radius-criterion.md), and [Campaign Radius Criterion](~/bulk-service/campaign-radius-criterion.md) records, as it had been in the corresponding format version 4.0 target records. To determine the intent option for all location and radius criterions of a given ad group or campaign, you can use the new [Ad Group Location Intent Criterion](~/bulk-service/ad-group-location-intent-criterion.md) and [Campaign Location Intent Criterion](~/bulk-service/campaign-location-intent-criterion.md) records. 
  * You cannot delete all criterions by sending one bulk record having *Status* set to *Deleted*. Previously using version 10 targets, you could have sent one row to delete all city targets for example. With criterions, each record must be updated and deleted individually with its unique identifier.

#### <a name="bulk-remarketinglist"></a>Remarketing Lists
For the remarketing list name in the [Remarketing List](~/bulk-service/remarketing-list.md) and [Ad Group Remarketing List Association](~/bulk-service/ad-group-remarketing-list-association.md) records, use the *Audience* field instead of the *Remarketing List* field. For the remarketing list identifier in the same records, use the *Audience Id* field instead of the *Remarketing List Id* field.

Bing Ads API version 11 also supports custom and in-market [audiences](#bulk-audience), in addition to remarketing lists. 

#### <a name="bulk-invalidcriterionstatus"></a>Invalid Criterion Status
An error will be returned if you attempt to set the *Status* of the [Ad Group Negative Dynamic Search Ad Target](~/bulk-service/ad-group-negative-dynamic-search-ad-target.md) or [Campaign Negative Dynamic Search Ad Target](~/bulk-service/campaign-negative-dynamic-search-ad-target.md) to an invalid value e.g. *Paused*. In Bing Ads API version 10, the invalid status update would not succeed but would not result in an error.

#### <a name="bulk-sunset-cpm"></a>Cpm Pricing Model
The CPM pricing model is not supported in Bing Ads, and the *Pricing Model* field of an [Ad Group](~/bulk-service/ad-group.md) is now deprecated. The *Pricing Model* field is now optional, defaults to *Cpc*, and can only be set to *Cpc*. 

### New Features

#### <a name="bulk-audience"></a>Audience Associations and Exclusions
Bing Ads API version 11 now supports custom audiences and in-market audiences, in addition to [remarketing lists](#bulk-remarketinglist). The following audience, association, and exclusion records are supported.

*  [Remarketing List](~/bulk-service/remarketing-list.md)  
*  [Ad Group Remarketing List Association](~/bulk-service/ad-group-remarketing-list-association.md)  
*  [Ad Group Negative Remarketing List Association](~/bulk-service/ad-group-negative-remarketing-list-association.md)  
*  [Custom Audience](~/bulk-service/custom-audience.md)  
*  [Ad Group Custom Audience Association](~/bulk-service/ad-group-custom-audience-association.md)  
*  [Ad Group Negative Custom Audience Association](~/bulk-service/ad-group-negative-custom-audience-association.md)  
*  [In Market Audience](~/bulk-service/in-market-audience.md)  
*  [Ad Group In Market Audience Association](~/bulk-service/ad-group-in-market-audience-association.md)  
*  [Ad Group Negative In Market Audience Association](~/bulk-service/ad-group-negative-in-market-audience-association.md)  

To download these record types individually you can include the following values from the [DownloadEntity](~/bulk-service/downloadentity.md) value set: *RemarketingLists*, *AdGroupRemarketingListAssociations*, *AdGroupNegativeRemarketingListAssociations*, *CustomAudiences*, *AdGroupCustomAudienceAssociations*, *AdGroupNegativeCustomAudienceAssociations*, *InMarketAudiences*, *AdGroupInMarketAudienceAssociations*, *AdGroupNegativeInMarketAudienceAssociations*. You can get all three types of audiences, associations, or exclusions by including the *Audiences*, *AdGroupAudienceAssociations*, and *AdGroupNegativeAudienceAssociations* values.

#### <a name="bulk-accountextensions"></a>Associate Ad Extensions with an Account
Support is added for associating ad extensions at the account level. In Bing Ads API version 10 you could only associate ad extensions with campaigns and ad groups.

> [!NOTE]
> Call ad extensions cannot be associated with an account.

To get and set account level associations, use the following account level association records. 
*   [Account App Ad Extension](~/bulk-service/account-app-ad-extension.md)   
*   [Account Callout Ad Extension](~/bulk-service/account-callout-ad-extension.md)  
*   [Account Image Ad Extension](~/bulk-service/account-image-ad-extension.md)  
*   [Account Location Ad Extension](~/bulk-service/account-location-ad-extension.md)  
*   [Account Price Ad Extension](~/bulk-service/account-price-ad-extension.md)  
*   [Account Review Ad Extension](~/bulk-service/account-review-ad-extension.md)  
*   [Account Sitelink2 Ad Extension](~/bulk-service/account-sitelink2-ad-extension.md)  
*   [Account Structured Snippet Ad Extension](~/bulk-service/account-structured-snippet-ad-extension.md)  

To download these record types individually you can include the following values from the [DownloadEntity](~/bulk-service/downloadentity.md) value set: *AccountAppAdExtensions*, *AccountCalloutAdExtensions*, *AccountImageAdExtensions*, *AccountLocationAdExtensions*, *AccountPriceAdExtensions*, *AccountReviewAdExtensions*, *AccountSitelink2AdExtensions*, *AccountStructuredSnippetAdExtensions*. 

#### <a name="bulk-priceextensions"></a>Price Ad Extensions
Support for price ad extensions is added. You can upload and download these price ad extension records.
*  [Price Ad Extension](~/bulk-service/price-ad-extension.md)  
*  [Account Price Ad Extension](~/bulk-service/account-price-ad-extension.md)  
*  [Ad Group Price Ad Extension](~/bulk-service/ad-group-price-ad-extension.md)  
*  [Campaign Price Ad Extension](~/bulk-service/campaign-price-ad-extension.md) 

To download these record types individually you can include the following values from the [DownloadEntity](~/bulk-service/downloadentity.md) value set: *PriceAdExtensions*, *AdGroupPriceAdExtensions*, *CampaignPriceAdExtensions*, *AccountPriceAdExtensions*. 

## <a name="campaign"></a>Campaign Management

### Breaking Changes

#### Proxy Client
Update your proxy client to use the new endpoint address and namespace.

The namespace is `https://bingads.microsoft.com/CampaignManagement/v11`.

The production endpoint is [https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc).

The sandbox endpoint is [https://campaign.api.sandbox.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc](https://campaign.api.sandbox.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc).

#### <a name="campaign-targetcriterions"></a>Upgrade from Targets to Criterions
Instead of using targets to show your ads based on age, day and time, device, gender, and location, starting with Bing Ads API version 11 you must use criterions. Partial update of target criterions is supported in Bing Ads API version 11. The following changes are required to upgrade from targets to criterions. 
  * Removed all *Target* objects and service operations. For example the *AgeTarget* and *AgeTargetBid* are replaced with the [AgeCriterion](~/campaign-management-service/agecriterion.md) object. To add an age criterion you embed the [AgeCriterion](~/campaign-management-service/agecriterion.md) in either the [BiddableCampaignCriterion](~/campaign-management-service/biddablecampaigncriterion.md) or [BiddableAdGroupCriterion](~/campaign-management-service/biddableadgroupcriterion.md) and then call the respective [AddCampaignCriterions](~/campaign-management-service/addcampaigncriterions.md) or [AddAdGroupCriterions](~/campaign-management-service/addadgroupcriterions.md) service operation. 
  * The [AgeRange](~/campaign-management-service/agerange.md) values are updated: *EighteenToTwentyFour*, *TwentyFiveToThirtyFour*, *ThirtyFiveToFortyNine*, *FiftyToSixtyFour*, and *SixtyFiveAndAbove*. The upper bound of each range previously supported in Bing Ads API Version 10 were not inclusive, for example *EighteenToTwentyFive* would only target ages eighteen through twenty-four. The values in Bing Ads API Version 11 match the effective target range that remains unchanged. 
  * If an ad group or campaign has any device criterion, then it must have bids for all three device types. Please note this change when adding and updating [DeviceCriterion](~/campaign-management-service/devicecriterion.md). For example you cannot have a campaign that only has one [DeviceCriterion](~/campaign-management-service/devicecriterion.md). If the campaign has any device criterion then it must have three [DeviceCriterion](~/campaign-management-service/devicecriterion.md), each with corresponding supported bids for *Computers*, *Smartphones*, and *Tablets*. Previously in Bing Ads API Version 10 the missing bids were added automatically with bids set to '0' (zero).  
  * The [LocationCriterion](~/campaign-management-service/locationcriterion.md) supports location identifiers in its *LocationId* element, instead of the location codes that were accepted for sub location targets e.g. *CityTargetBid* in Bing Ads API Version 10. The location identifier corresponds to the *ID* field of the geographical locations file. For more information, see [Geographical Location Codes](~/guides/geographical-location-codes.md) and [GetGeoLocationsFileUrl](~/campaign-management-service/getgeolocationsfileurl.md).
  * The [LocationIntentCriterion](~/campaign-management-service/locationintentcriterion.md) is added in Bing Ads API Version 11. Previously in Bing Ads API Version 10 you would have set the intent option in the *LocationTarget*, which has been removed. One location intent criterion determines the intent option for all location and radius criterions of a given ad group or campaign. 
  * Use the [BidMultiplier](~/campaign-management-service/bidmultiplier.md) object to adjust the bid for the target criterion. 
  
#### <a name="campaign-biddablecampaigncriterion"></a>Biddable Campaign Criterion
The [BiddableCampaignCriterion](~/campaign-management-service/biddablecampaigncriterion.md) is added, and derives properties from the [CampaignCriterion](~/campaign-management-service/campaigncriterion.md), which is now an abstract base class. You must use [BiddableCampaignCriterion](~/campaign-management-service/biddablecampaigncriterion.md) instead of [CampaignCriterion](~/campaign-management-service/campaigncriterion.md) in add, get, and update campaign criterion operations.
  
#### <a name="campaign-fixedbid"></a>Fixed Bid
Within the [FixedBid](~/campaign-management-service/fixedbid.md) object, the *Bid* element of type [Bid](~/campaign-management-service/bid.md) is replaced by the *Amount* element of type *double*. 

#### <a name="campaign-adgroupcriteriontype"></a>Ad Group Criterion Type
The *AccountId* element is removed from the request message of the [AddAdGroupCriterions](~/campaign-management-service/addadgroupcriterions.md), [DeleteAdGroupCriterions](~/campaign-management-service/deleteadgroupcriterions.md), [GetAdGroupCriterionsByIds](~/campaign-management-service/getadgroupcriterionsbyids.md), and [UpdateAdGroupCriterions](~/campaign-management-service/updateadgroupcriterions.md) operations. You must set the *CustomerAccountId* header element instead.

#### <a name="campaign-adgroupcriteriontype"></a>Shared Target to Criterion Migration
The *IsMigrated* element is added to the response message of the [AddAdGroupCriterions](~/campaign-management-service/addadgroupcriterions.md), [DeleteAdGroupCriterions](~/campaign-management-service/deleteadgroupcriterions.md), [UpdateAdGroupCriterions](~/campaign-management-service/updateadgroupcriterions.md), [AddCampaignCriterions](~/campaign-management-service/addcampaigncriterions.md), [DeleteCampaignCriterions](~/campaign-management-service/deletecampaigncriterions.md), and [UpdateCampaignCriterions](~/campaign-management-service/updatecampaigncriterions.md) operations. The *IsMigrated* element indicates whether or not the campaign or ad group where you added, deleted, or updated target criterions previously shared target criterions with another campaign or ad group. If *IsMigrated* is set to *true*, it indicates that the service migrated the shared target associations and assigned new criterion IDs. If you already have criterion IDs for targets such as age, day and time, device, gender, and location, then you should replace those IDs with all of the new IDs returned by the [GetAdGroupCriterionsByIds](~/campaign-management-service/getadgroupcriterionsbyids.md) or [GetCampaignCriterionsByIds](~/campaign-management-service/getcampaigncriterionsbyids.md) operation (specify *TargetCriterions* as the *CriterionType*). You only need to sync target criterion IDs, as other criterion types such as webpage criterions are not migrated. 

#### <a name="campaign-criterionaccount"></a>Account Id for Criterions
The *CriterionType* value set is renamed [AdGroupCriterionType](~/campaign-management-service/adgroupcriteriontype.md). You'll need to make code changes if you call the [AddAdGroupCriterions](~/campaign-management-service/addadgroupcriterions.md), [DeleteAdGroupCriterions](~/campaign-management-service/deleteadgroupcriterions.md), [GetAdGroupCriterionsByIds](~/campaign-management-service/getadgroupcriterionsbyids.md), or [UpdateAdGroupCriterions](~/campaign-management-service/updateadgroupcriterions.md) operations.

#### <a name="campaign-remarketinglist"></a>Remarketing Lists
The [RemarketingList](~/campaign-management-service/remarketinglist.md) now derives from the [Audience](~/campaign-management-service/audience.md) base class. The *Description*, *ForwardCompatibilityMap*, *Id*, *MembershipDuration*, *Name*, *ParentId*, and *Scope* elements are moved from [RemarketingList](~/campaign-management-service/remarketinglist.md) to the [Audience](~/campaign-management-service/audience.md) base class. The *AddRemarketingLists*, *DeleteRemarketingLists*, *GetRemarketingLists*, and *UpdateRemarketingLists* operations are replaced with the [AddAudiences](~/campaign-management-service/addaudiences.md), [DeleteAudiences](~/campaign-management-service/deleteaudiences.md), [GetAudiencesByIds](~/campaign-management-service/getaudiencesbyids.md), and [UpdateAudiences](~/campaign-management-service/updateaudiences.md) operations. Bing Ads API version 11 also supports custom and in-market [audiences](#campaign-audience), in addition to remarketing lists. 

The *AdGroupRemarketingListAssociation* object and *AddAdGroupRemarketingListAssociations*, *DeleteAdGroupRemarketingListAssociations*, *GetAdGroupRemarketingListAssociations*, and *UpdateAdGroupRemarketingListAssociations* operations are removed. To associate remarketing lists and other audience types with ad groups, use the new [AudienceCriterion](~/campaign-management-service/audiencecriterion.md) object with the [AddAdGroupCriterions](~/campaign-management-service/addadgroupcriterions.md), [DeleteAdGroupCriterions](~/campaign-management-service/deleteadgroupcriterions.md), [GetAdGroupCriterionsByIds](~/campaign-management-service/getadgroupcriterionsbyids.md), and [UpdateAdGroupCriterions](~/campaign-management-service/updateadgroupcriterions.md) operations.

#### <a name="campaign-monthlybudget"></a>Campaign Monthly Budget
Monthly budgets are no longer supported for Bing Ads campaigns. The *MonthlyBudget* element is removed from the [Campaign](~/campaign-management-service/campaign.md) object. The *MonthlyBudgetSpendUntilDepleted* value is removed from the [BudgetLimitType](~/campaign-management-service/budgetlimittype.md) value set.  

#### <a name="campaign-extensionpartialsuccess"></a>Ad Extensions Partial Success
The [AddAdExtensions](~/campaign-management-service/addadextensions.md), [DeleteAdExtensions](~/campaign-management-service/deleteadextensions.md), [DeleteAdExtensionsAssociations](~/campaign-management-service/deleteadextensionsassociations.md), [GetAdExtensionsAssociations](~/campaign-management-service/getadextensionsassociations.md),  [GetAdExtensionsByIds](~/campaign-management-service/getadextensionsbyids.md), [GetAdExtensionsEditorialReasons](~/campaign-management-service/getadextensionseditorialreasons.md), and [UpdateAdExtensions](~/campaign-management-service/updateadextensions.md) operations now support partial success. Either the *PartialErrors* or *NestedPartialErrors* element is added to each operation's response message. Note that the [SetAdExtensionsAssociations](~/campaign-management-service/setadextensionsassociations.md) operation already supported partial success.

#### <a name="campaign-extensiondevicepreference"></a>Ad Extensions Device Preference
The *DevicePreference* element is added to the [AdExtension](~/campaign-management-service/adextension.md) base class, and *DevicePreference* is removed from the [AppAdExtension](~/campaign-management-service/appadextension.md), [CallAdExtension](~/campaign-management-service/calladextension.md), and [Sitelink2AdExtension](~/campaign-management-service/sitelink2adextension.md) objects. Device preference is currently only supported for app, sitelink, and sitelink2 ad extensions. 

#### <a name="campaign-migrationtype"></a>Required Migration Type Filter
The *MigrationType* element of the [GetAccountMigrationStatuses](~/campaign-management-service/getaccountmigrationstatuses.md) service operation is now required. In version 10 if you did not specify any migration type value, by default the *SiteLinkAdExtension* migration status would be returned. 

#### <a name="campaign-requiredadtypes"></a>Required Ad Types
When calling the [GetAdsByAdGroupId](~/campaign-management-service/getadsbyadgroupid.md), [GetAdsByEditorialStatus](~/campaign-management-service/getadsbyeditorialstatus.md), and [GetAdsByIds](~/campaign-management-service/getadsbyids.md) operations the *AdTypes* element is now required. In version 10 these operations returned text and product ads if *AdTypes* was left nil.

#### <a name="campaign-addads"></a>Add Ads Duplicate Error
If you attempt to create an ad with duplicate ad copy, the [AddAds](~/campaign-management-service/addads.md) operation will now consistently return a duplicate ad error. In Version 10, the operation would return an error if the duplicate ad copy exists in the same batch request. However, if duplicate ad copy was provided in a subsequent call the operation appeared to succed but returned the existing ad identifier.

#### <a name="campaign-idcollection"></a>IdCollection Ids Data Type
The *Ids* element of the [IdCollection](~/campaign-management-service/idcollection.md) object is updated from *ArrayOflong* to *ArrayOfNullableOflong*. The response for [AddNegativeKeywordsToEntities](~/campaign-management-service/addnegativekeywordstoentities.md) can now contain a list item that is nil if a negative keyword was not successfully added. In Version 10 if a negative keyword was not added the operation returned *0* as a list item within *Ids* instead of nil. 

#### <a name="campaign-siteplacements"></a>Site Placements Sunset
Site placements were sunset during calendar year 2016, and the following programming elements are removed from the Campaign Management API: *SitePlacement*, *AddSitePlacements*, *DeleteSitePlacements*, *GetSitePlacementsByAdGroupId*, *GetSitePlacementsByIds*, *UpdateSitePlacements*, and *GetPlacementDetailsForUrls*.

#### <a name="campaign-adgroup-biddingmodel"></a>Ad Group Bidding Model
The *BiddingModel* value set is removed and the *BiddingModel* element is removed from the [AdGroup](~/campaign-management-service/adgroup.md) object. The bidding model is effectively determined by the Campaign type e.g. you can bid on keywords in Search and Content campaigns, product groups in Shopping campaigns, or webpage criterion in Dynamic Search Ad campaigns.

#### <a name="campaign-daylightsaving"></a>Campaign Daylight Saving
The *DaylightSaving* element is removed from the [Campaign](~/campaign-management-service/campaign.md) object. Bing Ads will continue to adjust the delivery only on time zones where DST adjustment applies. This setting was only used to interpret the start and end date of your ad groups relative to your campaign's time zone. It has never been used for day and time scheduling.

#### <a name="campaign-biddingschemestartingbid"></a>Bidding Scheme Starting Bid
The *StartingBid* element is removed from the [MaxConversionsBiddingScheme](~/campaign-management-service/maxconversionsbiddingscheme.md) and [TargetCpaBiddingScheme](~/campaign-management-service/targetcpabiddingscheme.md) objects. The starting bid was never implemented, and is removed from the Campaign Management API contract. 

#### <a name="campaign-invalidcriterionstatus"></a>Invalid Criterion Status
An error will be returned if you attempt to set the *Status* of the [NegativeAdGroupCriterion](~/campaign-management-service/negativeadgroupcriterion.md) or [NegativeCampaignCriterion](~/campaign-management-service/negativecampaigncriterion.md) to an invalid value e.g. *Paused*. In Bing Ads API version 10, the invalid status update would not succeed but would not result in an error.

#### <a name="campaign-adformatpreference"></a>Ad Format Preference for Native Ads
The Ad Format Preference is used to indicate whether or not you prefer the ad copy to be shown to users as a search or native ad. Search ads tend to be written as a call to action, whereas native ads should be written in more of an informational style.

The *NativePreference* key is removed from the ad's *ForwardCompatibilityMap*. In its place, the *AdFormatPreference* element of type *string* is added to the [Ad](~/campaign-management-service/ad.md) object. All ad types inherit this element, and currently it is only applicable for the [ExpandedTextAd](~/campaign-management-service/expandedtextad.md) and [TextAd](~/campaign-management-service/textad.md) objects. 

Possible values are *Native* and *All*. If set to *All*, the ad will be eligible for both search and native ad formats. If set to *Native*, the ad will only be eligible for the native ad format.

#### <a name="campaign-returnadditionalfields"></a>Return Additional Fields
The *ReturnAdditionalFields* element is removed from the [GetCampaignsByAccountId](~/campaign-management-service/getcampaignsbyaccountid.md), [GetCampaignsByIds](~/campaign-management-service/getcampaignsbyids.md), [GetAdGroupsByCampaignId](~/campaign-management-service/getadgroupsbycampaignid.md),[GetAdGroupsByIds](~/campaign-management-service/getadgroupsbyids.md), [GetKeywordsByAdGroupId](~/campaign-management-service/getkeywordsbyadgroupid.md), [GetKeywordsByEditorialStatus](~/campaign-management-service/getkeywordsbyeditorialstatus.md), [GetKeywordsByIds](~/campaign-management-service/getkeywordsbyids.md), and [GetAdExtensionsAssociations](~/campaign-management-service/getadextensionsassociations.md),[GetAdExtensionsByIds](~/campaign-management-service/getadextensionsbyids.md) request messages, and the corresponding elements of each [Campaign](~/campaign-management-service/campaign.md), [AdGroup](~/campaign-management-service/adgroup.md), [Keyword](~/campaign-management-service/keyword.md), [AdExtension](~/campaign-management-service/adextension.md), and [RemarketingList](~/campaign-management-service/remarketinglist.md) are returned by default.

#### <a name="campaign-sunset-cpm"></a>Cpm Pricing Model
The CPM pricing model is not supported in Bing Ads, and the *PricingModel* element of an [AdGroup](~/campaign-management-service/adgroup.md) is now deprecated. The *PricingModel* element is now optional, defaults to *Cpc*, and can only be set to *Cpc*. 

### New Features

#### <a name="campaign-audience"></a>Audience Associations and Exclusions
Bing Ads API version 11 now supports custom audiences and in-market audiences, in addition to [remarketing lists](#campaign-remarketinglist). 

The [CustomAudience](~/campaign-management-service/customaudience.md), [InMarketAudience](~/campaign-management-service/inmarketaudience.md), and [RemarketingList](~/campaign-management-service/remarketinglist.md) derive from the [Audience](~/campaign-management-service/audience.md) base class. You can manage audiences with the [AddAudiences](~/campaign-management-service/addaudiences.md), [DeleteAudiences](~/campaign-management-service/deleteaudiences.md), [GetAudiencesByIds](~/campaign-management-service/getaudiencesbyids.md), and [UpdateAudiences](~/campaign-management-service/updateaudiences.md) operations.
 
#### <a name="campaign-accountextensions"></a>Associate Ad Extensions with an Account
Support is added for associating ad extensions at the account level. In Bing Ads API version 10 you could only associate ad extensions with campaigns and ad groups.

> [!NOTE]
> Call ad extensions cannot be associated with an account.

To get and set account level associations, use the *Account* value of the [AssociationType](~/campaign-management-service/associationtype.md) value set. 

#### <a name="campaign-priceextensions"></a>Price Ad Extensions
Support for price ad extensions is added. You can manage the new [PriceAdExtension](~/campaign-management-service/priceadextension.md) object with the [AddAdExtensions](~/campaign-management-service/addadextensions.md), [DeleteAdExtensions](~/campaign-management-service/deleteadextensions.md), [DeleteAdExtensionsAssociations](~/campaign-management-service/deleteadextensionsassociations.md), [GetAdExtensionsAssociations](~/campaign-management-service/getadextensionsassociations.md),  [GetAdExtensionsByIds](~/campaign-management-service/getadextensionsbyids.md), [GetAdExtensionsEditorialReasons](~/campaign-management-service/getadextensionseditorialreasons.md), [SetAdExtensionsAssociations](~/campaign-management-service/setadextensionsassociations.md), and [UpdateAdExtensions](~/campaign-management-service/updateadextensions.md) operations. 

## <a name="billing"></a>Customer Billing

### Breaking Changes

#### Proxy Client
Update your proxy client to use the new endpoint address and namespace.

The namespace is `https://bingads.microsoft.com/Billing/v11`.

The production endpoint is [https://clientcenter.api.bingads.microsoft.com/Api/Billing/v11/CustomerBillingService.svc](https://clientcenter.api.bingads.microsoft.com/Api/Billing/v11/CustomerBillingService.svc).

#### <a name="billing-insertionorderstatus"></a>Insertion Order Status
For parity with the insertion order status values that you'll already find in the Bing Ads web application, the *Exhausted* and *Pending* values are added to the [InsertionOrderStatus](~/customer-billing-service/insertionorderstatus.md) value set. 

> [!NOTE]
> If the insertion order start date is in the future, the Bing Ads API Version 9 status would be Active; However in the Bing Ads web application and Bing Ads API Version 11 the status is Pending.

In addition the *ChangePendingReview* element is added to the [InsertionOrder](~/customer-billing-service/insertionorder.md) object. If this element is true, an update to the insertion order is pending user review. 

## <a name="customer"></a>Customer Management

### Breaking Changes

#### Proxy Client
Update your proxy client to use the new endpoint address and namespace.

The namespace is `https://bingads.microsoft.com/Customer/v11`.

The production endpoint is [https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc).

The sandbox endpoint is [https://clientcenter.api.sandbox.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc](https://clientcenter.api.sandbox.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc).

#### <a name="customer-taxdetails"></a>Tax Details
The *TaxId* is moved as a key and value pair to the *TaxInformation* element of the [AdvertiserAccount](~/customer-management-service/advertiseraccount.md) object. Additional keys include the *TaxType* and *VatNumber*.
 
The *BusinessAddress* element of an [AdvertiserAccount](~/customer-management-service/advertiseraccount.md) is now required when adding accounts. 

The *IncludeTaxDetails* element is removed from the [GetAccount](~/customer-management-service/getaccount.md) and [SearchAccounts](~/customer-management-service/searchaccounts.md) request messages, so the *BusinessAddress* element is now returned by default when retrieving accounts. With this update the *TaxId* and *TaxIdStatus* elements and corresponding value set is also removed.

The *IncludeTaxInformation* element is removed from the [GetAccount](~/customer-management-service/getaccount.md) and [SearchAccounts](~/customer-management-service/searchaccounts.md) request messages, so the *TaxInformation* element is now returned by default when retrieving accounts. 

#### <a name="customer-standarduser"></a>Standard User Role
To represent the Standard user role, the *StandardUser* value is added to the [UserRole](~/customer-management-service/userrole.md) value set. With Customer Management API Version 9 you could not get or set the Standard user role. In version 9 the Advertiser Campaign Manager role value was returned instead.

#### <a name="customer-linkedagencies"></a>Linked Agencies
The *LinkedAgencies* element is added to the [AdvertiserAccount](~/customer-management-service/advertiseraccount.md) object. This array of [CustomerInfo](~/customer-management-service/customerinfo.md) represents the list of agencies linked to the account. This element is reserved for future use.

The *AgencyContactName* and *AgencyCustomerId* elements are removed from the [AdvertiserAccount](~/customer-management-service/advertiseraccount.md) object. Instead you will be able to get those values in the *LinkedAgencies* element.

## <a name="reporting"></a>Reporting

### Breaking Changes

#### Proxy Client
Update your proxy client to use the new endpoint address and namespace.

The namespace is `https://bingads.microsoft.com/Reporting/v11`.

The production endpoint is [https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc).

The sandbox endpoint is [https://reporting.api.sandbox.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc](https://reporting.api.sandbox.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc).

#### <a name="reporting-downloadedcolumns"></a>Consistency Between WSDL Contract and Downloaded Report Columns
Previously there were some discrepancies between the report column value set names and the names of the columns in the downloaded reports. In Reporting API Version 11 most of the downloaded column names match the requested value. For example now when you submit a [KeywordPerformanceReportRequest](~/reporting-service/keywordperformancereportrequest.md) with the *BidMatchType* value from the [KeywordPerformanceReportColumn](~/reporting-service/keywordperformancereportcolumn.md) value set, the column name in the downloaded report is also *BidMatchType* in Reporting API Version 11. Previously in version 9, the column name in the downloaded report was *BiddedMatchType*.

> [!NOTE]
> Some download column names in version 11 do not match the version 11 contract. These will be updated in version 12. For more details see each column description in [Report Attributes and Performance Statistics](../guides/report-attributes-performance-statistics.md).

The following column names have changed in the downloaded reports from version 9 to 11.

Version 9|Version 11  
---------|---------
Ad group item Id|AdGroupCriterionId
BiddedMatchType|BidMatchType
MatchType|DeliveredMatchType
Device type|DeviceType
Path 1|Path1
Path 2|Path2
Title Part 1|TitlePart1
Title Part 2|TitlePart2
Search query|SearchQuery

#### <a name="reporting-percentcolumns"></a>Percent Appended to Downloaded Data
A percent symbol (%) is appended to the downloaded report data for the following columns. 

*ClickSharePercent*  
*Ctr*  
*EstimatedClickPercent*  
*EstimatedConversionRate*  
*EstimatedCtr*  
*EstimatedImpressionPercent*  
*ImpressionLostToAdRelevancePercent*  
*ImpressionLostToBidPercent*  
*ImpressionLostToBudgetPercent*  
*ImpressionLostToRankPercent*  
*ImpressionLostToExpectedCtrPercent*  
*ImpressionSharePercent*  
*LowQualityClicksPercent*  
*LowQualityImpressionsPercent*  
*ReturnOnAdSpend*  

The data is still a percentage and has not changed from version 9 to version 11. The only change is the percent symbol. For example in version 9 the download data for *Ctr* might have been *2.13*, and in version 11 it would be *2.13%*.

#### <a name="reporting-timeperiod"></a>TimePeriod Data Format
The date in the *TimePeriod* column download data is now formatted as YYYY-MM-DD. For example May 1, 2017 would be formatted as 2017-05-01. Previously the date was localized e.g. for English report downloads the date was formatted as m/d/yyyy. 


#### <a name="reporting-qualityscoresov"></a>Rename Quality Score and Share of Voice Subscore
Previously some of the Reporting API quality score and share of voice report column value set names did not match the Bing Ads web application. In Reporting API Version 11 the [AccountPerformanceReportColumn](~/reporting-service/accountperformancereportcolumn.md), [AdGroupPerformanceReportColumn](~/reporting-service/adgroupperformancereportcolumn.md), [CampaignPerformanceReportColumn](~/reporting-service/campaignperformancereportcolumn.md), [KeywordPerformanceReportColumn](~/reporting-service/keywordperformancereportcolumn.md), and [ShareOfVoiceReportColumn](~/reporting-service/shareofvoicereportcolumn.md) value sets are each updated with one or more of the new values, and the new names are also reflected in the downloaded report data i.e. new column header names. 

The following report column values have changed from version 9 to 11.

Version 9|Version 11  
---------|---------
HistoricKeywordRelevance|HistoricExpectedCtr
HistoricLandingPageRelevance|HistoricAdRelevance
HistoricLandingPageUserExperience|HistoricLandingPageExperience
ImpressionLostToKeywordRelevancePercent|ImpressionLostToExpectedCtrPercent
ImpressionLostToLandingPageRelevancePercent|ImpressionLostToAdRelevancePercent
KeywordRelevance|ExpectedCtr
LandingPageRelevance|AdRelevance
LandingPageUserExperience|LandingPageExperience

#### <a name="reporting-renamegeoreports"></a>Rename Geographic and User Location Reports
The following geographic and user location reports have been renamed to clarify their usage and match the Bing Ads web application.

In version 11, the [GeographicPerformanceReportRequest](~/reporting-service/geographicperformancereportrequest.md) with corresponding columns and filter replaces the *GeoLocationPerformanceReportRequest*.The geographic performance report shows impressions, clicks, spend, and average cost-per-click for each ad group, organized into columns that show the location used to serve ads. You can see where your traffic is coming from: the physical location of the people searching for your ad or the locations people are searching for. You can then validate whether your location targeting strategy is successful and identify opportunities to improve.

In version 11, the [UserLocationPerformanceReportRequest](~/reporting-service/userlocationperformancereportrequest.md) with corresponding columns and filter replaces the *GeographicalLocationReportRequest*. The user location performance report shows impressions, clicks, spend, and average cost-per-click for each ad group, organized by city, country, metro area, radius, state, and account. You can see where your traffic is coming from broken out by the physical location and the location people are searching for. You can then validate whether your location targeting strategy is successful, and identify opportunities to improve.

|Report Request|Report Filter|Report Column|
|-------------|-----------------|-----------------|
|[GeographicPerformanceReportRequest](~/reporting-service/geographicperformancereportrequest.md)|[GeographicPerformanceReportFilter](~/reporting-service/geographicperformancereportfilter.md)|[GeographicPerformanceReportColumn](~/reporting-service/geographicperformancereportcolumn.md)|
|[UserLocationPerformanceReportRequest](~/reporting-service/userlocationperformancereportrequest.md)|[UserLocationPerformanceReportFilter](~/reporting-service/userlocationperformancereportfilter.md)|[UserLocationPerformanceReportColumn](~/reporting-service/userlocationperformancereportcolumn.md)|


#### <a name="reporting-reportdownloadurl"></a>Report Download URL and Empty Reports
Even when the *Status* of the [ReportRequestStatus](~/reporting-service/reportrequeststatus.md) object is set to *Success*, the *ReportDownloadUrl* element will be nil if no performance data is available for the submitted report parameters (whether or not header and footer metadata were requested). Previously in version 9 a file that only included header and footer metadata would be returned.


#### <a name="reporting-sunset-bsc-reports"></a>Sunset Product Offer and Product Target Reports
The *ProductOfferPerformanceReportRequest* and *ProductTargetPerformanceReportRequest* with corresponding columns and filters are removed. For Bing Shopping campaigns you should use the [ProductDimensionPerformanceReportRequest](~/reporting-service/productdimensionperformancereportrequest.md), [ProductPartitionPerformanceReportRequest](~/reporting-service/productpartitionperformancereportrequest.md), and [ProductPartitionUnitPerformanceReportRequest](~/reporting-service/productpartitionunitperformancereportrequest.md). 

Additionally, the *ProductTarget* column is removed from the [SearchQueryPerformanceReportColumn](~/reporting-service/searchqueryperformancereportcolumn.md) value set. 

#### <a name="reporting-sunset-extensiondimension"></a>Sunset Ad Extension Dimension Report
The *AdExtensionDimensionReportRequest* with corresponding columns and filters is removed. Previously in Reporting API Version 9 attempting to submit this report request would throw an exception.

#### <a name="reporting-sunset-analytics"></a>Sunset Campaign Analytics Reports
The *TacticChannelReportRequest* and *TrafficSourcesReportRequest* with corresponding columns and filters are removed. Campaign Analytics was deprecated in October 2016, and data processing ended February 2017. If you are using [Universal Event Tracking](../guides/universal-event-tracking.md) you can get conversion data with several other reports, for example the [AccountPerformanceReportColumn](~/reporting-service/accountperformancereportcolumn.md), [AdGroupPerformanceReportColumn](~/reporting-service/adgroupperformancereportcolumn.md), [CampaignPerformanceReportColumn](~/reporting-service/campaignperformancereportcolumn.md), and [KeywordPerformanceReportColumn](~/reporting-service/keywordperformancereportcolumn.md). 

Additionally the *ExtendedCost*, *FunnelConversionRate*, *Step1*, *Step2*, *Step3*, *Step4*, and *Step5* columns are removed from all related value sets.

#### <a name="reporting-sunset-visits"></a>Sunset Visits and Spend Columns
Based on customer feedback about reporting priorities, the *AverageDurationPerVisit*, *AveragePagesPerVisit*, *BounceRate*, and *TotalVisits* columns are removed from the [AccountPerformanceReportColumn](~/reporting-service/accountperformancereportcolumn.md), [AdGroupPerformanceReportColumn](~/reporting-service/adgroupperformancereportcolumn.md), [CampaignPerformanceReportColumn](~/reporting-service/campaignperformancereportcolumn.md), and [KeywordPerformanceReportColumn](~/reporting-service/keywordperformancereportcolumn.md) value sets. 

Additionally the *ReturnOnAdSpend* and *Spend* columns are removed from the [GoalAndFunnelsReportColumn](~/reporting-service/goalsandfunnelsreportcolumn.md) value set.

#### <a name="reporting-sunset-phonespend"></a>Sunset Phone Spend Columns
There is no charge for call forwarding numbers using Skype, so the *PhoneSpend* and *TotalCostPhoneAndClicks* columns are removed from the [AccountPerformanceReportColumn](~/reporting-service/accountperformancereportcolumn.md), [AdGroupPerformanceReportColumn](~/reporting-service/adgroupperformancereportcolumn.md), [CallDetailReportColumn](~/reporting-service/calldetailreportcolumn.md), and [CampaignPerformanceReportColumn](~/reporting-service/campaignperformancereportcolumn.md) value sets. 

#### <a name="reporting-sunset-draft"></a>Sunset Draft Status Filter
The *Draft* status for ad groups was previously sunset in Bing Ads Campaign Management API (draft status removed from ad group status). In turn, the *Draft* value is removed removed from the [AdGroupStatusReportFilter](~/reporting-service/adgroupstatusreportfilter.md) value set.

#### <a name="reporting-sunset-submitted"></a>Sunset Submitted Filter
The *Submitted* status has the same meaning as *Active*, so the *Submitted* value is removed removed from the [AdStatusReportFilter](~/reporting-service/adstatusreportfilter.md), [AdGroupStatusReportFilter](~/reporting-service/adgroupstatusreportfilter.md), [CampaignStatusReportFilter](~/reporting-service/campaignstatusreportfilter.md) value sets.  

#### <a name="reporting-sunset-richads"></a>Sunset Rich Ads Report
The rich ads in search feature was already sunset in Bing Ads, and now the *RichAdComponentPerformanceReportRequest* with corresponding columns and filters is removed from the Reporting API. 

Additionally the *Image*, *Mobile*, *RichAd*, *RichMedia*, and *ThirdPartyCreative* values are removed from the [AdTypeReportFilter](~/reporting-service/adtypereportfilter.md) value set.

#### <a name="reporting-sunset-siteplacements"></a>Sunset Site Performance Report
Site placements are already sunset in Bing Ads, and now the *SitePerformanceReportRequest* with corresponding columns and filters is removed from the Reporting API. 

#### <a name="reporting-sunset-cpm"></a>Cpm Pricing Model
The CPM pricing model is not supported in Bing Ads, so the *AverageCpm* column is removed from the report column value sets. 

The *PricingModelReportFilter* value set is removed from the Reporting API and the *PricingModel* element is removed from the the [PublisherUsagePerformanceReportFilter](~/reporting-service/publisherusageperformancereportfilter.md). 


#### <a name="reporting-sunset-keywordmatchtypeid"></a>Sunset KeywordMatchTypeId Column
The keyword by match type migration was completed October 2013. Since Bing Ads does not return data prior to this date, the KeywordMatchTypeId is removed from the [KeywordPerformanceReportColumn](~/reporting-service/keywordperformancereportcolumn.md) value set. 

### New Features

#### <a name="reporting-excludemetadata"></a>Exclude Report Columns and Metadata
Bing Ads API version 11 now lets you choose whether or not the downloaded report should contain header, column, and footer metadata. You can optionally set any of the *ExcludeColumnHeaders*, *ExcludeReportFooter*, or *ExcludeReportHeader* properties of the [ReportRequest](~/reporting-service/reportrequest.md) to *true* if you want the corresponding metadata excluded from the downloaded report.
 
