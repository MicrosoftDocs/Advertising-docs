---
title: BiddableCampaignCriterion Data Object
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# BiddableCampaignCriterion Data Object
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
|<a name="criterionbid"></a>CriterionBid|The bid to use in the auction.<br/><br/>**Add:** Requirements vary depending on the type of *Criterion* that is [inherited](#InheritedElements) from the [CampaignCriterion](../campaign-management/campaigncriterion.md) object. The bid is optional and will be set to the default of *0* if not included for [AgeCriterion](../campaign-management/agecriterion.md), [DayTimeCriterion](../campaign-management/daytimecriterion.md), [DeviceCriterion](../campaign-management/devicecriterion.md), [GenderCriterion](../campaign-management/gendercriterion.md), [LocationCriterion](../campaign-management/locationcriterion.md), and [RadiusCriterion](../campaign-management/radiuscriterion.md). The bid is not applicable for [LocationIntentCriterion](../campaign-management/locationintentcriterion.md) and [ProductScope](../campaign-management/productscope.md) (The service will not return any error and the bid will be ignored even if you include it).<br/>**Update:** Requirements vary depending on the type of *Criterion* that is [inherited](#InheritedElements) from the [CampaignCriterion](../campaign-management/campaigncriterion.md) object. The bid is required for [AgeCriterion](../campaign-management/agecriterion.md), [DayTimeCriterion](../campaign-management/daytimecriterion.md), [DeviceCriterion](../campaign-management/devicecriterion.md), [GenderCriterion](../campaign-management/gendercriterion.md), [LocationCriterion](../campaign-management/locationcriterion.md), and [RadiusCriterion](../campaign-management/radiuscriterion.md). The bid is not applicable for [LocationIntentCriterion](../campaign-management/locationintentcriterion.md) and [ProductScope](../campaign-management/productscope.md) (The service will not return any error and the bid will be ignored even if you include it).|[CriterionBid](criterionbid.md)|

The [BiddableCampaignCriterion](biddablecampaigncriterion.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementscampaigncriterion"></a>Inherited Elements from CampaignCriterion
The [BiddableCampaignCriterion](biddablecampaigncriterion.md) object derives from the [CampaignCriterion](campaigncriterion.md) object, and inherits the following elements. The descriptions below are specific to [BiddableCampaignCriterion](biddablecampaigncriterion.md), and might not apply to other objects that inherit the same elements from the [CampaignCriterion](campaigncriterion.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign to apply the criterion to.<br/><br/>**Add:** Required<br/>**Update:** Required|**long**|
|<a name="criterion"></a>Criterion|The criterion to apply to the campaign. The criterion helps determine whether ads in the campaign are served.<br/><br/>For a list of available criterion types, see [CampaignCriterionType](../campaign-management/campaigncriteriontype.md).<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|[Criterion](criterion.md)|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|Reserved.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The unique Bing Ads identifier for the campaign criterion.<br/><br/>**Add:** Read-only<br/>**Update:** Required|**long**|
|<a name="status"></a>Status|A status value that determines whether the criterion applies for the campaign.<br/><br/>Currently the only supported status for biddable campaign criterions is *Active*.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[CampaignCriterionStatus](campaigncriterionstatus.md)|
|<a name="type"></a>Type|The type of the campaign criterion. This value is *BiddableCampaignCriterion* when you retrieve a biddable campaign criterion. For more information about campaign criterion types, see the [CampaignCriterion Data Object Remarks](../campaign-management/campaigncriterion.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

