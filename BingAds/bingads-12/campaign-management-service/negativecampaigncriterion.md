---
title: NegativeCampaignCriterion Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a criterion that you want to exclude from the specified campaign.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.
# NegativeCampaignCriterion Data Object - Campaign Management
Defines a criterion that you want to exclude from the specified campaign.

## Syntax
```xml
<xs:complexType name="NegativeCampaignCriterion" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:CampaignCriterion">
      <xs:sequence />
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [NegativeCampaignCriterion](negativecampaigncriterion.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementscampaigncriterion"></a>Inherited Elements from CampaignCriterion
The [NegativeCampaignCriterion](negativecampaigncriterion.md) object derives from the [CampaignCriterion](campaigncriterion.md) object, and inherits the following elements. The descriptions below are specific to [NegativeCampaignCriterion](negativecampaigncriterion.md), and might not apply to other objects that inherit the same elements from the [CampaignCriterion](campaigncriterion.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign to apply the criterion to.<br/><br/>**Add:** Required<br/>**Update:** Required|**long**|
|<a name="criterion"></a>Criterion|The criterion to apply to the campaign. The criterion helps determine whether ads in the campaign are served.<br/><br/>For a list of available criterion types, see [CampaignCriterionType](../campaign-management-service/campaigncriteriontype.md).<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|[Criterion](criterion.md)|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The unique Bing Ads identifier for the campaign criterion.<br/><br/>**Add:** Read-only<br/>**Update:** Required|**long**|
|<a name="status"></a>Status|A status value that determines whether the criterion applies for the campaign.<br/><br/>Currently the only supported status for negative campaign criterions is *Active*.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[CampaignCriterionStatus](campaigncriterionstatus.md)|
|<a name="type"></a>Type|The type of the campaign criterion. This value is *NegativeCampaignCriterion* when you retrieve a negative campaign criterion. For more information about campaign criterion types, see the [CampaignCriterion Data Object Remarks](../campaign-management-service/campaigncriterion.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

