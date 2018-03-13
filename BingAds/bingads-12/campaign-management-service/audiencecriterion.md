---
title: AudienceCriterion Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a criterion that can be used to show ads to a specific audience.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# AudienceCriterion Data Object - Campaign Management
Defines a criterion that can be used to show ads to a specific audience.

The *AudienceCriterion* criterion can be included within [AdGroupCriterion](adgroupcriterion.md) and [NegativeAdGroupCriterion](negativeadgroupcriterion.md) objects. 

## Syntax
```xml
<xs:complexType name="AudienceCriterion" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Criterion">
      <xs:sequence>
        <xs:element minOccurs="0" name="AudienceId" nillable="true" type="xs:long" />
        <xs:element minOccurs="0" name="AudienceType" nillable="true" type="tns:AudienceType" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="audienceid"></a>AudienceId|The Bing Ads identifier of the [Audience](audience.md).<br/><br/>**Add:** Required<br/>**Update:** Read-only. You must leave this element null or the audience must already be associated with the specified entity. To associate a different audience with the entity, you must add a new audience criterion and optionally delete any existing audience criterions.|**long**|
|<a name="audiencetype"></a>AudienceType|The audience type.<br/><br/>**Add:** Required<br/>**Update:** Read-only. |[AudienceType](audiencetype.md)|

The [AudienceCriterion](audiencecriterion.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementscriterion"></a>Inherited Elements from Criterion
The [AudienceCriterion](audiencecriterion.md) object derives from the [Criterion](criterion.md) object, and inherits the following elements. The descriptions below are specific to [AudienceCriterion](audiencecriterion.md), and might not apply to other objects that inherit the same elements from the [Criterion](criterion.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of the criterion. This value is *Audience* when you retrieve an audience criterion. For more information about criterion types, see the [Criterion Data Object Remarks](criterion.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

