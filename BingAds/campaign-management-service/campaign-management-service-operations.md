---
title: Campaign Management Service Operations
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Service operations reference for the CampaignManagement service.
---
# Campaign Management Service Operations
The Campaign Management service defines the following data objects.

|Service Operation|Description|Request Limits|
|---|---|---|
|[AddAdExtensions](addadextensions.md)|Adds one or more ad extensions to an account's ad extension library.|N/A.|
|[AddAdGroupCriterions](addadgroupcriterions.md)|Adds one or more ad group criterions.|N/A.|
|[AddAdGroups](addadgroups.md)|Adds new ad groups to a specified campaign.|N/A.|
|[AddAds](addads.md)|Adds one or more ads to an ad group.|N/A.|
|[AddAudiences](addaudiences.md)|Adds one or more audiences.|N/A.|
|[AddBudgets](addbudgets.md)|Adds new budgets to the account's shared budget library.|N/A.|
|[AddCampaignCriterions](addcampaigncriterions.md)|Adds one or more campaign criterions that help determine whether ads in each campaign get served.|N/A.|
|[AddCampaigns](addcampaigns.md)|Adds one or more campaigns to the specified account.|N/A.|
|[AddConversionGoals](addconversiongoals.md)|Adds new conversion goals to the account's shared conversion goal library.|N/A.|
|[AddKeywords](addkeywords.md)|Adds one or more keywords to an ad group.|N/A.|
|[AddLabels](addlabels.md)|Adds one or more labels to an account.|N/A.|
|[AddListItemsToSharedList](addlistitemstosharedlist.md)|Adds negative keywords to the shared negative keyword list.|N/A.|
|[AddMedia](addmedia.md)|Adds the specified media to an account's media library.|N/A.|
|[AddNegativeKeywordsToEntities](addnegativekeywordstoentities.md)|Adds negative keywords to the specified campaign or ad group.|N/A.|
|[AddSharedEntity](addsharedentity.md)|Adds a negative keyword list to the account's library.|N/A.|
|[AddUetTags](adduettags.md)|Adds new Universal Event Tracking (UET) tags that you can add to your website to allow Bing Ads to collect actions people take on your website.|N/A.|
|[AppealEditorialRejections](appealeditorialrejections.md)|Appeals the editorial rejections of one or more ads or keywords that failed editorial review.|N/A.|
|[ApplyOfflineConversions](applyofflineconversions.md)|Applies offline conversions for the account with Microsoft Click Id among other offline conversion data.|N/A.|
|[ApplyProductPartitionActions](applyproductpartitionactions.md)|Applies an add, update, or delete action to each of the specified [BiddableAdGroupCriterion](../campaign-management-service/biddableadgroupcriterion.md) or [NegativeAdGroupCriterion](../campaign-management-service/negativeadgroupcriterion.md), which each contain a [ProductPartition](../campaign-management-service/productpartition.md).|N/A.|
|[DeleteAdExtensions](deleteadextensions.md)|Deletes one or more ad extensions from the account's ad extension library.|N/A.|
|[DeleteAdExtensionsAssociations](deleteadextensionsassociations.md)|Removes the specified association from the respective campaigns or ad groups.|N/A.|
|[DeleteAdGroupCriterions](deleteadgroupcriterions.md)|Deletes the specified ad group criterions.|N/A.|
|[DeleteAdGroups](deleteadgroups.md)|Deletes one or more ad groups from the specified campaign.|N/A.|
|[DeleteAds](deleteads.md)|Deletes one or more ads from the specified ad group.|N/A.|
|[DeleteAudiences](deleteaudiences.md)|Deletes the specified audiences.|N/A.|
|[DeleteBudgets](deletebudgets.md)|Deletes budgets from the account's shared budget library.|N/A.|
|[DeleteCampaignCriterions](deletecampaigncriterions.md)|Deletes one or more campaign criterions.|N/A.|
|[DeleteCampaigns](deletecampaigns.md)|Deletes one or more campaigns in a specified account.|N/A.|
|[DeleteKeywords](deletekeywords.md)|Deletes one or more keywords in a specified ad group.|N/A.|
|[DeleteLabelAssociations](deletelabelassociations.md)|Deletes label associations.|N/A.|
|[DeleteLabels](deletelabels.md)|Deletes one or more labels from the account.|N/A.|
|[DeleteListItemsFromSharedList](deletelistitemsfromsharedlist.md)|Deletes negative keywords from a negative keyword list.|N/A.|
|[DeleteMedia](deletemedia.md)|Deletes the specified media from an account's media library.|N/A.|
|[DeleteNegativeKeywordsFromEntities](deletenegativekeywordsfromentities.md)|Deletes negative keywords from the specified campaign or ad group.|N/A.|
|[DeleteSharedEntities](deletesharedentities.md)|Deletes negative keyword lists from the account's library.|N/A.|
|[DeleteSharedEntityAssociations](deletesharedentityassociations.md)|Removes the association between a negative keyword list and an entity such as a campaign.|N/A.|
|[GetAccountMigrationStatuses](getaccountmigrationstatuses.md)|Gets the migration status info for the specified accounts.|N/A.|
|[GetAccountProperties](getaccountproperties.md)|Gets account level properties by name.|N/A.|
|[GetAdExtensionIdsByAccountId](getadextensionidsbyaccountid.md)|Gets the ad extensions from the account's ad extension library.|N/A.|
|[GetAdExtensionsAssociations](getadextensionsassociations.md)|Gets the respective ad extension associations by the specified campaign and ad group identifiers.|N/A.|
|[GetAdExtensionsByIds](getadextensionsbyids.md)|Gets the specified ad extensions from the account's ad extension library.|N/A.|
|[GetAdExtensionsEditorialReasons](getadextensionseditorialreasons.md)|Gets editorial rejection reasons for the respective ad extension and entity associations.|N/A.|
|[GetAdGroupCriterionsByIds](getadgroupcriterionsbyids.md)|Gets ad group criterions by identifiers and types.|N/A.|
|[GetAdGroupsByCampaignId](getadgroupsbycampaignid.md)|Gets the ad groups within the specified campaign.|N/A.|
|[GetAdGroupsByIds](getadgroupsbyids.md)|Gets the specified ad groups within the specified campaign.|N/A.|
|[GetAdsByAdGroupId](getadsbyadgroupid.md)|Retrieves the ads within an ad group.|N/A.|
|[GetAdsByEditorialStatus](getadsbyeditorialstatus.md)|Retrieves the ads that belong to the specified ad group and have the specified editorial review status.|N/A.|
|[GetAdsByIds](getadsbyids.md)|Retrieves the specified ads from the specified ad group.|N/A.|
|[GetAudiencesByIds](getaudiencesbyids.md)|Retrieves the specified audiences from the specified account.|N/A.|
|[GetBMCStoresByCustomerId](getbmcstoresbycustomerid.md)|Gets the Bing Merchant Center stores for the specified customer.|N/A.|
|[GetBSCCountries](getbsccountries.md)|Gets the list of supported sales country codes for Bing Shopping campaigns.|N/A.|
|[GetBudgetsByIds](getbudgetsbyids.md)|Gets the specified budgets from the account's shared budget library.|N/A.|
|[GetCampaignCriterionsByIds](getcampaigncriterionsbyids.md)|Gets the specified campaign criterions.|N/A.|
|[GetCampaignIdsByBudgetIds](getcampaignidsbybudgetids.md)|Gets the campaign identifiers that share each specified budget.|N/A.|
|[GetCampaignsByAccountId](getcampaignsbyaccountid.md)|Gets the campaigns within an account.|N/A.|
|[GetCampaignsByIds](getcampaignsbyids.md)|Gets the specified campaigns within an account.|N/A.|
|[GetConversionGoalsByIds](getconversiongoalsbyids.md)|Gets the specified conversion goals.|N/A.|
|[GetConversionGoalsByTagIds](getconversiongoalsbytagids.md)|Gets the conversion goals that use the specified UET tags.|N/A.|
|[GetEditorialReasonsByIds](geteditorialreasonsbyids.md)|Gets the reasons why the specified entities failed editorial review and whether the rejection is appealable.|N/A.|
|[GetGeoLocationsFileUrl](getgeolocationsfileurl.md)|Gets a temporary URL that you can use to download a file that contains the supported geographical location targeting codes.|N/A.|
|[GetKeywordsByAdGroupId](getkeywordsbyadgroupid.md)|Gets the keywords within an ad group.|N/A.|
|[GetKeywordsByEditorialStatus](getkeywordsbyeditorialstatus.md)|Retrieves the keywords with the specified editorial review status.|N/A.|
|[GetKeywordsByIds](getkeywordsbyids.md)|Retrieves the specified keywords.|N/A.|
|[GetLabelAssociationsByEntityIds](getlabelassociationsbyentityids.md)|Gets label associations by entity identifiers.|N/A.|
|[GetLabelAssociationsByLabelIds](getlabelassociationsbylabelids.md)|Gets label associations by label identifiers.|N/A.|
|[GetLabelsByIds](getlabelsbyids.md)|Gets labels by label identifiers.|N/A.|
|[GetListItemsBySharedList](getlistitemsbysharedlist.md)|Gets the negative keywords of a negative keyword list.|N/A.|
|[GetMediaAssociations](getmediaassociations.md)|Gets the media associations of the specified entity type from an account's media library.|N/A.|
|[GetMediaByIds](getmediabyids.md)|Gets the specified media from an account's media library.|N/A.|
|[GetMediaMetaDataByAccountId](getmediametadatabyaccountid.md)|Gets the media meta data of the specified entity type from an account's media library.|N/A.|
|[GetMediaMetaDataByIds](getmediametadatabyids.md)|Gets the specified media meta data from an account's media library.|N/A.|
|[GetNegativeKeywordsByEntityIds](getnegativekeywordsbyentityids.md)|Gets the negative keywords that are only associated with the specified campaigns or ad groups.|N/A.|
|[GetNegativeSitesByAdGroupIds](getnegativesitesbyadgroupids.md)|Gets the negative site URLs of the specified ad groups.|N/A.|
|[GetNegativeSitesByCampaignIds](getnegativesitesbycampaignids.md)|Gets the negative site URLs of the specified campaigns.|N/A.|
|[GetSharedEntitiesByAccountId](getsharedentitiesbyaccountid.md)|Gets the negative keyword lists from the account's library.|N/A.|
|[GetSharedEntityAssociationsByEntityIds](getsharedentityassociationsbyentityids.md)|Gets negative keyword list associations for the specified campaigns.|N/A.|
|[GetSharedEntityAssociationsBySharedEntityIds](getsharedentityassociationsbysharedentityids.md)|Gets shared entity associations for the specified negative keyword lists.|N/A.|
|[GetUetTagsByIds](getuettagsbyids.md)|Gets the specified Universal Event Tracking (UET) tags.|N/A.|
|[SetAccountProperties](setaccountproperties.md)|Sets account level properties by name.|N/A.|
|[SetAdExtensionsAssociations](setadextensionsassociations.md)|Associates the specified ad extensions with the respective campaigns or ad groups.|N/A.|
|[SetLabelAssociations](setlabelassociations.md)|Sets label associations.|N/A.|
|[SetNegativeSitesToAdGroups](setnegativesitestoadgroups.md)|Sets the negative site URLs of the specified ad groups.|N/A.|
|[SetNegativeSitesToCampaigns](setnegativesitestocampaigns.md)|Sets the negative site URLs of the specified campaigns.|N/A.|
|[SetSharedEntityAssociations](setsharedentityassociations.md)|Sets the association between a campaign and a negative keyword list.|N/A.|
|[UpdateAdExtensions](updateadextensions.md)|Updates one or more ad extensions within an account's ad extension library.|N/A.|
|[UpdateAdGroupCriterions](updateadgroupcriterions.md)|Updates one or more ad group criterions.|N/A.|
|[UpdateAdGroups](updateadgroups.md)|Updates the specified ad groups in a campaign.|N/A.|
|[UpdateAds](updateads.md)|Updates the specified ads within an ad group.|N/A.|
|[UpdateAudiences](updateaudiences.md)|Updates the specified audiences.|N/A.|
|[UpdateBudgets](updatebudgets.md)|Updates the specified budgets in the account's shared budget library.|N/A.|
|[UpdateCampaignCriterions](updatecampaigncriterions.md)|Updates one or more campaign criterions.|N/A.|
|[UpdateCampaigns](updatecampaigns.md)|Updates specified campaigns in a specified account.|N/A.|
|[UpdateConversionGoals](updateconversiongoals.md)|Updates conversion goals within the account's shared conversion goal library.|N/A.|
|[UpdateKeywords](updatekeywords.md)|Updates the keywords within a specified ad group.|N/A.|
|[UpdateLabels](updatelabels.md)|Updates the labels within the account.|N/A.|
|[UpdateSharedEntities](updatesharedentities.md)|Updates negative keyword lists within the account's library.|N/A.|
|[UpdateUetTags](updateuettags.md)|Updates the specified Universal Event Tracking (UET) tags.|N/A.|
