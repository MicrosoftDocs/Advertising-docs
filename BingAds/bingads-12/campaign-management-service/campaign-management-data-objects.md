---
title: Campaign Management Data Objects
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Data objects reference for the CampaignManagement service.
---
# Campaign Management Data Objects
The Campaign Management service defines the following data objects.

|Data Object|Description|
|---|---|
|[AccountMigrationStatusesInfo](accountmigrationstatusesinfo.md)|Defines an object that contains migration status for an account.|
|[AccountProperty](accountproperty.md)|Maps an account level property name to a string value.|
|[ActionAdExtension](actionadextension.md)|Defines an action ad extension that can be included in an ad.|
|[Ad](ad.md)|Defines the base object of an ad.|
|[AdApiError](adapierror.md)|Defines an error object that contains the details that explain why the service operation failed.|
|[AdApiFaultDetail](adapifaultdetail.md)|Defines a fault object that operations return when generic errors occur, such as an authentication error.|
|[Address](address.md)|Defines a postal address.|
|[AdExtension](adextension.md)|Defines the base object of an ad extension.|
|[AdExtensionAssociation](adextensionassociation.md)|Defines the relationship and editorial status of an ad extension with an account, campaign, or ad group.|
|[AdExtensionAssociationCollection](adextensionassociationcollection.md)|Defines an array of objects that associate an ad extension and its editorial status to an account, campaign, or ad group.|
|[AdExtensionEditorialReason](adextensioneditorialreason.md)|Defines an object that you can use to determine the component of an ad extension that failed editorial review, and the reason for the failure.|
|[AdExtensionEditorialReasonCollection](adextensioneditorialreasoncollection.md)|Defines a collection of ad extensions that failed editorial review.|
|[AdExtensionIdentity](adextensionidentity.md)|Defines an object that identifies an ad extension revision.|
|[AdExtensionIdToEntityIdAssociation](adextensionidtoentityidassociation.md)|Defines an object that associates an ad extension to a supported entity, for example ad group or campaign.|
|[AdGroup](adgroup.md)|Defines an ad group.|
|[AdGroupCriterion](adgroupcriterion.md)|Defines a criterion that you want applied to the specified ad group.|
|[AdGroupCriterionAction](adgroupcriterionaction.md)|Defines the action to apply to a [BiddableAdGroupCriterion](biddableadgroupcriterion.md) or [NegativeAdGroupCriterion](negativeadgroupcriterion.md), specifically one that contains a [ProductPartition](productpartition.md).|
|[AdGroupNegativeSites](adgroupnegativesites.md)|Defines an object that contains the negative site URLs of an ad group.|
|[AdRotation](adrotation.md)|Defines an object that specifies the type of ad rotation to apply to the ad group.|
|[AgeCriterion](agecriterion.md)|Defines a criterion that can be used to show ads to users in a specific age range.|
|[ApiFaultDetail](apifaultdetail.md)|Defines a fault object that operations return when web service-specific errors occur, such as when the request message contains incomplete or invalid data.|
|[AppAdExtension](appadextension.md)|Defines an app ad extension that can be included in a text ad.|
|[AppInstallAd](appinstallad.md)|Defines an app install ad.|
|[AppInstallGoal](appinstallgoal.md)|Defines an app install conversion goal.|
|[ApplicationFault](applicationfault.md)|Defines the base object from which all fault detail objects derive.|
|[AppUrl](appurl.md)|Defines the operating system platform and URL of the app store download webpage.|
|[Asset](asset.md)|Defines the base object of an asset with a unique Bing Ads identifier that can be reused across multiple ads.|
|[AssetLink](assetlink.md)|Defines the relationship of an asset to an ad.|
|[Audience](audience.md)|Defines the base object of an audience.|
|[AudienceCriterion](audiencecriterion.md)|Defines a criterion that can be used to show ads to a specific audience.|
|[BatchError](batcherror.md)|Defines an error object that identifies the item within the batch of items in the request message that caused the operation to fail, and describes the reason for the failure.|
|[BatchErrorCollection](batcherrorcollection.md)|Defines an error object that contains batch error details for the top level list index and a list of batch errors corresponding to the  nested list index.|
|[Bid](bid.md)|The highest price that you want to pay each time someone clicks your ad.|
|[BiddableAdGroupCriterion](biddableadgroupcriterion.md)|Defines a biddable criterion that you want applied to the specified ad group.|
|[BiddableCampaignCriterion](biddablecampaigncriterion.md)|Defines a biddable criterion that you want applied to the specified campaign.|
|[BiddingScheme](biddingscheme.md)|Defines the base object of a bidding scheme for how you want to manage your bids.|
|[BidMultiplier](bidmultiplier.md)|Defines the multiplier by which to adjust your base bid for the corresponding criterion.|
|[BMCStore](bmcstore.md)|Defines a Bing Merchant Center store.|
|[Budget](budget.md)|Represents a budget that can be shared by any campaigns in an account.|
|[CallAdExtension](calladextension.md)|Defines an object that specifies a click-to-call phone number to include in a text ad.|
|[CalloutAdExtension](calloutadextension.md)|Defines an object that specifies additional text about your business, products, or services to include in a text ad.|
|[Campaign](campaign.md)|Defines a campaign.|
|[CampaignCriterion](campaigncriterion.md)|Defines a criterion that you want applied to the specified campaign.|
|[CampaignNegativeSites](campaignnegativesites.md)|Defines an object that contains the negative site URLs of a campaign.|
|[ConversionGoal](conversiongoal.md)|Defines the base object of a conversion goal.|
|[ConversionGoalRevenue](conversiongoalrevenue.md)|Defines properties for revenue that can be tracked by a conversion goal.|
|[CoOpSetting](coopsetting.md)|Defines the ad group level settings for feed-based cooperative bidding campaigns.|
|[Criterion](criterion.md)|Defines the base object of a criterion.|
|[CriterionBid](criterionbid.md)|Defines a base class for criterion bids.|
|[CustomAudience](customaudience.md)|Defines a custom audience.|
|[CustomEventsRule](customeventsrule.md)|Defines a custom events remarketing rule.|
|[CustomParameter](customparameter.md)|Defines a key and value custom parameter for URL tracking.|
|[CustomParameters](customparameters.md)|Defines a collection of key and value custom parameters for URL tracking.|
|[Date](date.md)|Represents a date.|
|[DayTime](daytime.md)|Defines a day of the week and time range for ad extension scheduling.|
|[DayTimeCriterion](daytimecriterion.md)|Defines a criterion that can be used to show ads to users during a specific day and time range.|
|[DeviceCriterion](devicecriterion.md)|Defines a criterion that can be used to show ads on specific devices.|
|[DurationGoal](durationgoal.md)|Defines a duration conversion goal.|
|[DynamicSearchAd](dynamicsearchad.md)|Defines a dynamic search ad.|
|[DynamicSearchAdsSetting](dynamicsearchadssetting.md)|Defines the campaign level settings for a Dynamic Search Ads campaign.|
|[EditorialApiFaultDetail](editorialapifaultdetail.md)|Defines a fault object that operations such as [AddAdGroupCriterions](addadgroupcriterions.md), [UpdateAdGroupCriterions](updateadgroupcriterions.md), [SetAdExtensionsAssociations](setadextensionsassociations.md), and [UpdateAdExtensions](updateadextensions.md) return when one or more criterion or ad extensions in your request message fail editorial review.|
|[EditorialError](editorialerror.md)|Defines an error object that identifies one of potentially many reasons why an entity failed editorial review.|
|[EditorialErrorCollection](editorialerrorcollection.md)|Defines a nested list of error object that identifies one of potentially many reasons why an entity failed editorial review.|
|[EditorialReason](editorialreason.md)|Defines an object that you can use to determine the component of an ad or keyword that failed editorial review, and the reason for the failure.|
|[EditorialReasonCollection](editorialreasoncollection.md)|Defines a collection of ads or keywords that failed editorial review, and the reason for the failure.|
|[EnhancedCpcBiddingScheme](enhancedcpcbiddingscheme.md)|Defines an object that represents the enhanced CPC bid strategy type.|
|[EntityIdToParentIdAssociation](entityidtoparentidassociation.md)|Defines an object that contains the unique system identifier of an entity such as ad or keyword, and the identifier of its parent.|
|[EntityNegativeKeyword](entitynegativekeyword.md)|Defines an object that contains a set of negative keywords that are only associated with the corresponding entity such as a campaign or ad group.|
|[EventGoal](eventgoal.md)|Defines a custom event conversion goal.|
|[ExpandedTextAd](expandedtextad.md)|Defines an expanded text ad.|
|[Experiment](experiment.md)|Defines an experiment where you split a campaign’s budget and traffic, and then run an A/B test during a limited date range.|
|[FixedBid](fixedbid.md)|Defines the fixed bid to use in the auction.|
|[GenderCriterion](gendercriterion.md)|Defines a criterion that can be used to show ads to users of a specific gender.|
|[GeoPoint](geopoint.md)|Defines an object that contains the longitude and latitude coordinates of a geographical location.|
|[IdCollection](idcollection.md)|Defines an object that contains a list of entity identifiers.|
|[Image](image.md)|Defines an image object that can be added to an account's media library.|
|[ImageAdExtension](imageadextension.md)|Defines an ad extension that specifies an image with alternative text to include in an expanded text ad.|
|[ImageMediaRepresentation](imagemediarepresentation.md)|Defines an image media representation with height and width.|
|[InheritFromParentBiddingScheme](inheritfromparentbiddingscheme.md)|Defines an object that represents the inherit from parent bid strategy type.|
|[InMarketAudience](inmarketaudience.md)|Defines an in-market audience.|
|[InStoreTransactionGoal](instoretransactiongoal.md)|Defines an in-store transaction goal.|
|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md)|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.|
|[Keyword](keyword.md)|Defines a keyword.|
|[Label](label.md)|Labels let you organize campaigns, ad groups, ads, and keywords into groups based on whatever is important to you.|
|[LabelAssociation](labelassociation.md)|Defines the relationship between a label and campaign, ad group, ad, or keyword entity.|
|[LocationAdExtension](locationadextension.md)|Defines an ad extension that specifies a business address and phone number to include in a text ad.|
|[LocationCriterion](locationcriterion.md)|Defines a criterion that can be used to show ads to users in a specific location.|
|[LocationIntentCriterion](locationintentcriterion.md)|Defines a criterion that determines the intent option for all location and radius criterions of the campaign or ad group.|
|[ManualCpcBiddingScheme](manualcpcbiddingscheme.md)|Defines an object that represents the manual CPC bid strategy type.|
|[MaxClicksBiddingScheme](maxclicksbiddingscheme.md)|Defines an object that represents the maximum clicks bid strategy type.|
|[MaxConversionsBiddingScheme](maxconversionsbiddingscheme.md)|Defines an object that represents the maximum conversions bid strategy type.|
|[Media](media.md)|Defines the base object of media.|
|[MediaAssociation](mediaassociation.md)|Defines an object that represents the identified media and an associated entity, for example media associated with an ad group.|
|[MediaMetaData](mediametadata.md)|Defines a media meta data object.|
|[MediaRepresentation](mediarepresentation.md)|Defines a media representation base class that includes a  media download Url.|
|[MigrationStatusInfo](migrationstatusinfo.md)|Defines an object that contains the migration type and status for an account.|
|[NegativeAdGroupCriterion](negativeadgroupcriterion.md)|Defines a criterion that you want to exclude from the specified ad group.|
|[NegativeCampaignCriterion](negativecampaigncriterion.md)|Defines a criterion that you want to exclude from the specified campaign.|
|[NegativeKeyword](negativekeyword.md)|Defines a negative keyword with match type.|
|[NegativeKeywordList](negativekeywordlist.md)|Defines a negative keyword list.|
|[OfflineConversion](offlineconversion.md)|Defines an offline conversion that you send to Bing Ads.|
|[OfflineConversionGoal](offlineconversiongoal.md)|Defines an offline conversion goal.|
|[OperationError](operationerror.md)|Defines an error object that contains the details that explain why the service operation failed.|
|[PagesViewedPerVisitGoal](pagesviewedpervisitgoal.md)|Defines a pages viewed per visit conversion goal.|
|[PageVisitorsRule](pagevisitorsrule.md)|Defines a page visitors remarketing rule.|
|[PageVisitorsWhoDidNotVisitAnotherPageRule](pagevisitorswhodidnotvisitanotherpagerule.md)|Defines a page visitors who did not visit another page remarketing rule.|
|[PageVisitorsWhoVisitedAnotherPageRule](pagevisitorswhovisitedanotherpagerule.md)|Defines a page visitors who visited another page remarketing rule.|
|[Paging](paging.md)|Defines a paging object that you can use to request objects in batches.|
|[PriceAdExtension](priceadextension.md)|Defines an ad extension that includes between 3 and 8 price table rows.|
|[PriceTableRow](pricetablerow.md)|Defines pricing information by currency and unit that you can use with price ad extensions.|
|[ProductAd](productad.md)|Defines a product ad.|
|[ProductAudience](productaudience.md)|Defines a product audience that you can use to remarket products from your Bing Merchant Center store.|
|[ProductCondition](productcondition.md)|Defines a condition that determines whether a product is selected from a customer's Bing Merchant Center catalog file.|
|[ProductPartition](productpartition.md)|Defines an ad group level product partition with one condition that helps determine whether a product from the Bing Merchant Center store gets served as a product ad.|
|[ProductScope](productscope.md)|Defines a campaign level product scope with list of conditions that help determine whether a product from the Bing Merchant Center store gets served as a product ad.|
|[ProfileCriterion](profilecriterion.md)|Defines a criterion that can be used to show ads to users in a specific company, industry, or job function.|
|[RadiusCriterion](radiuscriterion.md)|Defines a criterion that can be used to show ads to users within the radius of a specific geographical location.|
|[RemarketingList](remarketinglist.md)|Defines a remarketing list.|
|[RemarketingRule](remarketingrule.md)|Defines the base object of a remarketing rule.|
|[ResponsiveAd](responsivead.md)|A responsive ad format for Audience ads in the Microsoft Audience Network.|
|[ResponsiveSearchAd](responsivesearchad.md)|A responsive ad format for text ads in the Search network.|
|[ReviewAdExtension](reviewadextension.md)|Defines an object that specifies third-party reviews (exact or paraphrased) about your business, products, or services to include in an expanded text ad.|
|[RuleItem](ruleitem.md)|Defines the base class of a remarketing list rule item.|
|[RuleItemGroup](ruleitemgroup.md)|Defines an object that contains a list of remarketing list rule items that apply to the same visited page.|
|[Schedule](schedule.md)|Defines the start and end date ranges for ad extension scheduling.|
|[Setting](setting.md)|Defines the base class of a setting.|
|[SharedEntity](sharedentity.md)|Defines the base class of a shared entity.|
|[SharedEntityAssociation](sharedentityassociation.md)|Defines an object that contains association information for a campaign and shared entity such as a negative keyword list.|
|[SharedList](sharedlist.md)|Defines the base class of a shared list.|
|[SharedListItem](sharedlistitem.md)|Defines the base class of a shared list item.|
|[ShoppingSetting](shoppingsetting.md)|Defines the campaign level settings for feed-based audience or shopping campaigns.|
|[SimilarRemarketingList](similarremarketinglist.md)|Defines an audience that is similar to one of your remarketing lists.|
|[SitelinkAdExtension](sitelinkadextension.md)|Defines an object with one sitelink per ad extension.|
|[StringRuleItem](stringruleitem.md)|Defines a rule expression that depends on the string values of the Url or Referrer Url.|
|[StructuredSnippetAdExtension](structuredsnippetadextension.md)|Defines an object that pairs one header with between 3 and 10 snippet values that tell customers more about your business.|
|[TargetCpaBiddingScheme](targetcpabiddingscheme.md)|Defines an object that represents the target CPA bid strategy type.|
|[TargetSetting](targetsetting.md)|The target settings that determines whether the Age, Audience, CompanyName, Gender, Industry, and JobFunction criterion type groups use the "target and bid" option or the "bid only" target option.|
|[TargetSettingDetail](targetsettingdetail.md)|Determines whether you want to use the "target and bid" option or the "bid only" target option for the criterion type group.|
|[TextAd](textad.md)|Defines a text ad.|
|[TextAsset](textasset.md)|A text asset with a unique Bing Ads identifier that can be reused across multiple ads.|
|[UetTag](uettag.md)|Defines a Universal Event Tracking (UET) tag that you can add to your website to allow Bing Ads to collect actions people take on your website.|
|[UrlGoal](urlgoal.md)|Defines a URL conversion goal.|
|[Webpage](webpage.md)|Defines a webpage parameter that contains a list of webpage conditions or criteria that help determine whether you want to show dynamic search ads.|
|[WebpageCondition](webpagecondition.md)|Defines a condition or criterion that helps determine whether you want to show dynamic search ads.|
|[WebpageParameter](webpageparameter.md)|Defines the conditions or criteria that determine whether you want to show dynamic search ads.|
