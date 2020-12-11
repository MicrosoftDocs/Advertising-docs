---
title: BatchError Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a Campaign Management batch error object that identifies the item within the batch of items in the request message that caused the operation to fail, and describes the reason for the failure.
---
# BatchError Data Object - Campaign Management
Defines a Campaign Management batch error object that identifies the item within the batch of items in the request message that caused the operation to fail, and describes the reason for the failure.

## Syntax
```xml
<xs:complexType name="BatchError" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Code" type="xs:int" />
    <xs:element minOccurs="0" name="Details" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="ErrorCode" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="FieldPath" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="ForwardCompatibilityMap" nillable="true" type="q9:ArrayOfKeyValuePairOfstringstring" xmlns:q9="http://schemas.datacontract.org/2004/07/System.Collections.Generic" />
    <xs:element minOccurs="0" name="Index" type="xs:int" />
    <xs:element minOccurs="0" name="Message" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Type" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [BatchError](batcherror.md) object has the following elements: [Code](#code), [Details](#details), [ErrorCode](#errorcode), [FieldPath](#fieldpath), [ForwardCompatibilityMap](#forwardcompatibilitymap), [Index](#index), [Message](#message), [Type](#type).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="code"></a>Code|A numeric error code that identifies the error.|**int**|
|<a name="details"></a>Details|A message that provides additional details about the batch error. This string can be empty.|**string**|
|<a name="errorcode"></a>ErrorCode|A symbolic string constant that identifies the error. For example, UserIsNotAuthorized.|**string**|
|<a name="fieldpath"></a>FieldPath|The name of the data object's element where the error occurred. For example if the *TrackingUrlTemplate* of a [Campaign](campaign.md) contains invalid text, the value of this *FieldPath* element is TrackingUrlTemplate.<br/><br/>This value is subject to change, so you should not take a dependency on the current string format.<br/><br/>This element is not supported for all errors. The field path is supported for errors related to *FinalMobileUrls*, *FinalUrls*, *TrackingUrlTemplate*, and *UrlCustomParameters* elements of the respective [Campaign](campaign.md), [AdGroup](adgroup.md), [TextAd](textad.md), [ProductAd](productad.md), [BiddableAdGroupCriterion](biddableadgroupcriterion.md), and [Keyword](keyword.md) objects. It is also supported for errors related to all fields of the [CalloutAdExtension](calloutadextension.md) and [ReviewAdExtension](reviewadextension.md) objects.|**string**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br/><br/>Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for this object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="index"></a>Index|The zero-based index of the item in the batch of items in the request message that failed.|**int**|
|<a name="message"></a>Message|A message that describes the error.<br/><br/>For more information about troubleshooting and error handling, see [Handling Service Errors and Exceptions](../guides/handle-service-errors-exceptions.md) and [Operation Error Codes](../guides/operation-error-codes.md).|**string**|
|<a name="type"></a>Type|Reserved for internal use.|**string**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[AddAdGroups](addadgroups.md)  
[AddAds](addads.md)  
[AddAudiences](addaudiences.md)  
[AddBidStrategies](addbidstrategies.md)  
[AddBudgets](addbudgets.md)  
[AddCampaigns](addcampaigns.md)  
[AddConversionGoals](addconversiongoals.md)  
[AddExperiments](addexperiments.md)  
[AddImportJobs](addimportjobs.md)  
[AddKeywords](addkeywords.md)  
[AddLabels](addlabels.md)  
[AddListItemsToSharedList](addlistitemstosharedlist.md)  
[AddSharedEntity](addsharedentity.md)  
[AddUetTags](adduettags.md)  
[ApiFaultDetail](apifaultdetail.md)  
[AppealEditorialRejections](appealeditorialrejections.md)  
[ApplyOfflineConversionAdjustments](applyofflineconversionadjustments.md)  
[ApplyOfflineConversions](applyofflineconversions.md)  
[ApplyProductPartitionActions](applyproductpartitionactions.md)  
[BatchErrorCollection](batcherrorcollection.md)  
[DeleteAdExtensions](deleteadextensions.md)  
[DeleteAdExtensionsAssociations](deleteadextensionsassociations.md)  
[DeleteAdGroupCriterions](deleteadgroupcriterions.md)  
[DeleteAdGroups](deleteadgroups.md)  
[DeleteAds](deleteads.md)  
[DeleteAudiences](deleteaudiences.md)  
[DeleteBidStrategies](deletebidstrategies.md)  
[DeleteBudgets](deletebudgets.md)  
[DeleteCampaignCriterions](deletecampaigncriterions.md)  
[DeleteCampaigns](deletecampaigns.md)  
[DeleteExperiments](deleteexperiments.md)  
[DeleteImportJobs](deleteimportjobs.md)  
[DeleteKeywords](deletekeywords.md)  
[DeleteLabelAssociations](deletelabelassociations.md)  
[DeleteLabels](deletelabels.md)  
[DeleteListItemsFromSharedList](deletelistitemsfromsharedlist.md)  
[DeleteMedia](deletemedia.md)  
[DeleteSharedEntities](deletesharedentities.md)  
[DeleteSharedEntityAssociations](deletesharedentityassociations.md)  
[EditorialApiFaultDetail](editorialapifaultdetail.md)  
[GetAccountProperties](getaccountproperties.md)  
[GetAdExtensionsAssociations](getadextensionsassociations.md)  
[GetAdExtensionsByIds](getadextensionsbyids.md)  
[GetAdExtensionsEditorialReasons](getadextensionseditorialreasons.md)  
[GetAdGroupsByIds](getadgroupsbyids.md)  
[GetAdsByIds](getadsbyids.md)  
[GetAudiencesByIds](getaudiencesbyids.md)  
[GetBidStrategiesByIds](getbidstrategiesbyids.md)  
[GetBudgetsByIds](getbudgetsbyids.md)  
[GetCampaignCriterionsByIds](getcampaigncriterionsbyids.md)  
[GetCampaignIdsByBidStrategyIds](getcampaignidsbybidstrategyids.md)  
[GetCampaignIdsByBudgetIds](getcampaignidsbybudgetids.md)  
[GetCampaignsByIds](getcampaignsbyids.md)  
[GetConversionGoalsByIds](getconversiongoalsbyids.md)  
[GetConversionGoalsByTagIds](getconversiongoalsbytagids.md)  
[GetEditorialReasonsByIds](geteditorialreasonsbyids.md)  
[GetExperimentsByIds](getexperimentsbyids.md)  
[GetImportEntityIdsMapping](getimportentityidsmapping.md)  
[GetImportJobsByIds](getimportjobsbyids.md)  
[GetKeywordsByIds](getkeywordsbyids.md)  
[GetLabelAssociationsByEntityIds](getlabelassociationsbyentityids.md)  
[GetLabelAssociationsByLabelIds](getlabelassociationsbylabelids.md)  
[GetLabelsByIds](getlabelsbyids.md)  
[GetMediaAssociations](getmediaassociations.md)  
[GetMediaMetaDataByIds](getmediametadatabyids.md)  
[GetNegativeKeywordsByEntityIds](getnegativekeywordsbyentityids.md)  
[GetNegativeSitesByAdGroupIds](getnegativesitesbyadgroupids.md)  
[GetNegativeSitesByCampaignIds](getnegativesitesbycampaignids.md)  
[GetSharedEntityAssociationsByEntityIds](getsharedentityassociationsbyentityids.md)  
[GetSharedEntityAssociationsBySharedEntityIds](getsharedentityassociationsbysharedentityids.md)  
[GetUetTagsByIds](getuettagsbyids.md)  
[SetAdExtensionsAssociations](setadextensionsassociations.md)  
[SetLabelAssociations](setlabelassociations.md)  
[SetNegativeSitesToAdGroups](setnegativesitestoadgroups.md)  
[SetNegativeSitesToCampaigns](setnegativesitestocampaigns.md)  
[SetSharedEntityAssociations](setsharedentityassociations.md)  
[UpdateAdGroups](updateadgroups.md)  
[UpdateAds](updateads.md)  
[UpdateAudiences](updateaudiences.md)  
[UpdateBidStrategies](updatebidstrategies.md)  
[UpdateBudgets](updatebudgets.md)  
[UpdateCampaigns](updatecampaigns.md)  
[UpdateConversionGoals](updateconversiongoals.md)  
[UpdateExperiments](updateexperiments.md)  
[UpdateKeywords](updatekeywords.md)  
[UpdateLabels](updatelabels.md)  
[UpdateSharedEntities](updatesharedentities.md)  
[UpdateUetTags](updateuettags.md)  
