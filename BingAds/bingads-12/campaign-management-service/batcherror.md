---
title: BatchError Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an error object that identifies the item within the batch of items in the request message that caused the operation to fail, and describes the reason for the failure.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# BatchError Data Object - Campaign Management
Defines an error object that identifies the item within the batch of items in the request message that caused the operation to fail, and describes the reason for the failure.

## Syntax
```xml
<xs:complexType name="BatchError" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Code" type="xs:int" />
    <xs:element minOccurs="0" name="Details" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="ErrorCode" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="FieldPath" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="ForwardCompatibilityMap" nillable="true" type="q10:ArrayOfKeyValuePairOfstringstring" xmlns:q10="http://schemas.datacontract.org/2004/07/System.Collections.Generic" />
    <xs:element minOccurs="0" name="Index" type="xs:int" />
    <xs:element minOccurs="0" name="Message" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Type" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="code"></a>Code|A numeric error code that identifies the error.|**int**|
|<a name="details"></a>Details|A message that provides additional details about the batch error. This string can be empty.|**string**|
|<a name="errorcode"></a>ErrorCode|A symbolic string constant that identifies the error. For example, UserIsNotAuthorized.|**string**|
|<a name="fieldpath"></a>FieldPath|The name of the data object's element where the error occurred. For example if the *TrackingUrlTemplate* of a [Campaign](campaign.md) contains invalid text, the value of this *FieldPath* element is TrackingUrlTemplate.<br /><br /> This value is subject to change, so you should not take a dependency on the current string format.<br /><br /> This element is not supported for all errors. The field path is supported for errors related to *FinalMobileUrls*, *FinalUrls*, *TrackingUrlTemplate*, and *UrlCustomParameters* elements of the respective [Campaign](campaign.md), [AdGroup](adgroup.md), [TextAd](textad.md), [ProductAd](productad.md), [BiddableAdGroupCriterion](biddableadgroupcriterion.md), and [Keyword](keyword.md) objects. It is also supported for errors related to all fields of the [CalloutAdExtension](calloutadextension.md) and [ReviewAdExtension](reviewadextension.md) objects.|**string**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br />Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for this object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="index"></a>Index|The zero-based index of the item in the batch of items in the request message that failed.|**int**|
|<a name="message"></a>Message|A message that describes the error.|**string**|
|<a name="type"></a>Type|Reserved for internal use.|**string**|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[AddAdGroups](addadgroups.md)  
[AddAds](addads.md)  
[AddAudiences](addaudiences.md)  
[AddBudgets](addbudgets.md)  
[AddCampaigns](addcampaigns.md)  
[AddConversionGoals](addconversiongoals.md)  
[AddKeywords](addkeywords.md)  
[AddLabels](addlabels.md)  
[AddListItemsToSharedList](addlistitemstosharedlist.md)  
[AddSharedEntity](addsharedentity.md)  
[AddUetTags](adduettags.md)  
[ApiFaultDetail](apifaultdetail.md)  
[AppealEditorialRejections](appealeditorialrejections.md)  
[ApplyOfflineConversions](applyofflineconversions.md)  
[ApplyProductPartitionActions](applyproductpartitionactions.md)  
[BatchErrorCollection](batcherrorcollection.md)  
[DeleteAdExtensions](deleteadextensions.md)  
[DeleteAdExtensionsAssociations](deleteadextensionsassociations.md)  
[DeleteAdGroupCriterions](deleteadgroupcriterions.md)  
[DeleteAdGroups](deleteadgroups.md)  
[DeleteAds](deleteads.md)  
[DeleteAudiences](deleteaudiences.md)  
[DeleteBudgets](deletebudgets.md)  
[DeleteCampaignCriterions](deletecampaigncriterions.md)  
[DeleteCampaigns](deletecampaigns.md)  
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
[GetBudgetsByIds](getbudgetsbyids.md)  
[GetCampaignCriterionsByIds](getcampaigncriterionsbyids.md)  
[GetCampaignIdsByBudgetIds](getcampaignidsbybudgetids.md)  
[GetCampaignsByIds](getcampaignsbyids.md)  
[GetConversionGoalsByIds](getconversiongoalsbyids.md)  
[GetConversionGoalsByTagIds](getconversiongoalsbytagids.md)  
[GetEditorialReasonsByIds](geteditorialreasonsbyids.md)  
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
[UpdateBudgets](updatebudgets.md)  
[UpdateCampaigns](updatecampaigns.md)  
[UpdateConversionGoals](updateconversiongoals.md)  
[UpdateKeywords](updatekeywords.md)  
[UpdateLabels](updatelabels.md)  
[UpdateSharedEntities](updatesharedentities.md)  
[UpdateUetTags](updateuettags.md)  
