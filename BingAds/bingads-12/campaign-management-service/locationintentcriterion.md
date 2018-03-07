---
title: LocationIntentCriterion Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a criterion that determines the intent option for all location and radius criterions of the campaign or ad group.
---
# LocationIntentCriterion Data Object - Campaign Management
Defines a criterion that determines the intent option for all location and radius criterions of the campaign or ad group. There isn't any accompanying criterion bid adjustment. 

The maximum number of location intent criterions that you can specify per campaign or ad group is one.

> [!NOTE]
> You can only have one [LocationIntentCriterion](locationintentcriterion.md) per campaign or ad group to determine the location intent option that applies for all of the campaign or ad group's geographical criterions (location, negative location, and location intent criterions). When you create the campaign or ad group's first criterion, a [LocationIntentCriterion](locationintentcriterion.md) will also be added automatically with the default *IntentOption* set to *PeopleInOrSearchingForOrViewingPages*. You can add or update a campaign or ad group's [LocationIntentCriterion](locationintentcriterion.md), whether or not the campaign or ad group has any other criterions. You cannot delete a [LocationIntentCriterion](locationintentcriterion.md), although it has no purpose without location or location intent criterions. 

The *LocationIntentCriterion* criterion can be included within [AdGroupCriterion](adgroupcriterion.md) and [CampaignCriterion](campaigncriterion.md) objects. 

Also note that you must consider the location, negative location, and radius criterions as a set of *geo criterions*. If the ad group has any geo criterions, then none of the campaign's geo criterions are inherited. If the ad group doesn't have any geo criterions, then all of the campaign's geo criterions are inherited. The geo criterions can be inherited from the campaign even if the ad group has a location intent criterion. If the ad group's geo criterions are used, then the ad group's location intent criterion is used; if the campaign's geo criterions are inherited, then the campaign's location intent criterion is used and the ad group's location intent criterion is ignored. You cannot delete a campaign or ad group's location intent criterion, although it has no purpose without location or radius criterions. 

## Syntax
```xml
<xs:complexType name="LocationIntentCriterion" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Criterion">
      <xs:sequence>
        <xs:element minOccurs="0" name="IntentOption" nillable="true" type="tns:IntentOption" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="intentoption"></a>IntentOption|Determines whether a person must be physically located in the targeted location in order for the ad to display.<br/><br/>The following values are supported. The default value is *PeopleInOrSearchingForOrViewingPages*.<br/>- Use *PeopleInOrSearchingForOrViewingPages* if you want to show ads to people in, searching for, or viewing pages about your targeted location.<br/>- Use *PeopleSearchingForOrViewingPages* if you want to show ads to people searching for or viewing pages about your targeted location.<br/>- Use *PeopleIn* if you want to show ads to people in your targeted location.<br/><br/>**Add:** Optional. If no value is specified the default value is *PeopleInOrSearchingForOrViewingPages*.<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|[IntentOption](intentoption.md)|

The [LocationIntentCriterion](locationintentcriterion.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementscriterion"></a>Inherited Elements from Criterion
The [LocationIntentCriterion](locationintentcriterion.md) object derives from the [Criterion](criterion.md) object, and inherits the following elements. The descriptions below are specific to [LocationIntentCriterion](locationintentcriterion.md), and might not apply to other objects that inherit the same elements from the [Criterion](criterion.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of the criterion. This value is *LocationIntent* when you retrieve a location intent criterion. For more information about criterion types, see the [Criterion Data Object Remarks](criterion.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

