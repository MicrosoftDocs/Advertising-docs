---
title: BiddableCampaignCriterion Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a biddable criterion that you want applied to the specified campaign.
---
# BiddableCampaignCriterion Data Object - Campaign Management
Defines a biddable criterion that you want applied to the specified campaign.

## Syntax
```xml
<xs:complexType name="BiddableCampaignCriterion" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:CampaignCriterion">
      <xs:sequence>
        <xs:element minOccurs="0" name="CriterionBid" nillable="true" type="tns:CriterionBid" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="criterionbid"></a>CriterionBid|The bid to use in the auction.<br/><br/>**Add:** Requirements vary depending on the type of *Criterion* that is [inherited](#inheritedelements) from the [CampaignCriterion](/bingads/campaign-management-service/campaigncriterion.md) object. The bid is optional and will be set to the default of *0* if not included for [AgeCriterion](/bingads/campaign-management-service/agecriterion.md), [DayTimeCriterion](/bingads/campaign-management-service/daytimecriterion.md), [DeviceCriterion](/bingads/campaign-management-service/devicecriterion.md), [GenderCriterion](/bingads/campaign-management-service/gendercriterion.md), [LocationCriterion](/bingads/campaign-management-service/locationcriterion.md), and [RadiusCriterion](/bingads/campaign-management-service/radiuscriterion.md). The bid is not applicable for [LocationIntentCriterion](/bingads/campaign-management-service/locationintentcriterion.md) and [ProductScope](/bingads/campaign-management-service/productscope.md) (The service will not return any error and the bid will be ignored even if you include it).<br/>**Update:** Requirements vary depending on the type of *Criterion* that is [inherited](#inheritedelements) from the [CampaignCriterion](/bingads/campaign-management-service/campaigncriterion.md) object. The bid is required for [AgeCriterion](/bingads/campaign-management-service/agecriterion.md), [DayTimeCriterion](/bingads/campaign-management-service/daytimecriterion.md), [DeviceCriterion](/bingads/campaign-management-service/devicecriterion.md), [GenderCriterion](/bingads/campaign-management-service/gendercriterion.md), [LocationCriterion](/bingads/campaign-management-service/locationcriterion.md), and [RadiusCriterion](/bingads/campaign-management-service/radiuscriterion.md). The bid is not applicable for [LocationIntentCriterion](/bingads/campaign-management-service/locationintentcriterion.md) and [ProductScope](/bingads/campaign-management-service/productscope.md) (The service will not return any error and the bid will be ignored even if you include it).|[CriterionBid](criterionbid.md)|

The [BiddableCampaignCriterion](biddablecampaigncriterion.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementscampaigncriterion"></a>Inherited Elements from CampaignCriterion
The [BiddableCampaignCriterion](biddablecampaigncriterion.md) object derives from the [CampaignCriterion](campaigncriterion.md) object, and inherits the following elements. The descriptions below are specific to [BiddableCampaignCriterion](biddablecampaigncriterion.md), and might not apply to other objects that inherit the same elements from the [CampaignCriterion](campaigncriterion.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign to apply the criterion to.<br/><br/>**Add:** Required<br/>**Update:** Required|**long**|
|<a name="criterion"></a>Criterion|The criterion to apply to the campaign. The criterion helps determine whether ads in the campaign are served.<br/><br/>For a list of available criterion types, see [CampaignCriterionType](/bingads/campaign-management-service/campaigncriteriontype.md).<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|[Criterion](criterion.md)|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The unique Bing Ads identifier for the campaign criterion.<br/><br/>**Add:** Read-only<br/>**Update:** Required|**long**|
|<a name="status"></a>Status|A status value that determines whether the criterion applies for the campaign.<br/><br/>Currently the only supported status for biddable campaign criterions is *Active*.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[CampaignCriterionStatus](campaigncriterionstatus.md)|
|<a name="type"></a>Type|The type of the campaign criterion. This value is *BiddableCampaignCriterion* when you retrieve a biddable campaign criterion. For more information about campaign criterion types, see the [CampaignCriterion Data Object Remarks](/bingads/campaign-management-service/campaigncriterion.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

