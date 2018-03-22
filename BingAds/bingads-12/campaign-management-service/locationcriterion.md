---
title: LocationCriterion Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a criterion that can be used to show ads to users in a specific location.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# LocationCriterion Data Object - Campaign Management
Defines a criterion that can be used to show ads to users in a specific location.

With location criterions, you can choose to show ads to potential customers in, searching for, or viewing pages about:
*  All available countries/regions
*  Selected cities, postal codes, metro areas (Nielsen DMA? in the United States), counties, states/provinces, and countries/regions

Each location criterion defines a location code for the accompanying criterion bid adjustment. 

The maximum number of combined location and negative location criterions that you can specify per campaign or ad group is 10,000.  

> [!NOTE]
> You can only have one [LocationIntentCriterion](locationintentcriterion.md) per campaign or ad group to determine the location intent option that applies for all of the campaign or ad group's geographical criterions (location, negative location, and radius criterions). When you create the campaign or ad group's first criterion, a [LocationIntentCriterion](locationintentcriterion.md) will also be added automatically with the default *IntentOption* set to *PeopleInOrSearchingForOrViewingPages*. You can add or update a campaign or ad group's [LocationIntentCriterion](locationintentcriterion.md), whether or not the campaign or ad group has any other criterions. You cannot delete a [LocationIntentCriterion](locationintentcriterion.md), although it has no purpose without location or radius criterions. 

The *LocationCriterion* criterion can be included within [AdGroupCriterion](adgroupcriterion.md), [NegativeAdGroupCriterion](negativeadgroupcriterion.md), [CampaignCriterion](campaigncriterion.md), and [NegativeCampaignCriterion](negativecampaigncriterion.md) objects. If ad group level location criterions are specified (positive or negative), the campaign level location criterions are ignored for that ad group. In other words the ad group location criterions override the campaign location criterions, and are not applied as a union.  

Also note that you must consider the location, negative location, and radius criterions as a set of *geo criterions*. If the ad group has any geo criterions, then none of the campaign's geo criterions are inherited. If the ad group doesn't have any geo criterions, then all of the campaign's geo criterions are inherited. The geo criterions can be inherited from the campaign even if the ad group has a location intent criterion. If the ad group's geo criterions are used, then the ad group's location intent criterion is used; if the campaign's geo criterions are inherited, then the campaign's location intent criterion is used and the ad group's location intent criterion is ignored. You cannot delete a campaign or ad group's location intent criterion, although it has no purpose without location or radius criterions. 

## Syntax
```xml
<xs:complexType name="LocationCriterion" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Criterion">
      <xs:sequence>
        <xs:element minOccurs="0" name="DisplayName" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="EnclosedLocationIds" nillable="true" type="q59:ArrayOflong" xmlns:q59="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
        <xs:element minOccurs="0" name="LocationId" nillable="true" type="xs:long" />
        <xs:element minOccurs="0" name="LocationType" nillable="true" type="xs:string" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="displayname"></a>DisplayName|The location display name.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|
|<a name="enclosedlocationids"></a>EnclosedLocationIds|Reserved for internal use.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**long** array|
|<a name="locationid"></a>LocationId|The unique Bing Ads identifier for the location where you want to show your ads.<br /><br />For geographical location codes, see [GetGeoLocationsFileUrl](getgeolocationsfileurl.md) and [Geographical Location Codes](../guides/geographical-location-codes.md).<br/><br/>**Add:** Required<br/>**Update:** Not allowed. If you specify this element it must match the existing setting.|**long**|
|<a name="locationtype"></a>LocationType|The location type.<br/><br/>Possible values include, but are not limited to *City*, *Country*, *MetroArea*, *PostalCode*, and *State*.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only |**string**|

The [LocationCriterion](locationcriterion.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementscriterion"></a>Inherited Elements from Criterion
The [LocationCriterion](locationcriterion.md) object derives from the [Criterion](criterion.md) object, and inherits the following elements. The descriptions below are specific to [LocationCriterion](locationcriterion.md), and might not apply to other objects that inherit the same elements from the [Criterion](criterion.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of the criterion. This value is *Location* when you retrieve a location criterion. For more information about criterion types, see the [Criterion Data Object Remarks](criterion.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

