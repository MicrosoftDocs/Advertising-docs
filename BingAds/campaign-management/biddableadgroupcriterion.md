---
title: BiddableAdGroupCriterion Data Object
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# BiddableAdGroupCriterion Data Object
Defines a biddable criterion that you want applied to the specified ad group.

## Syntax
```xml
<xs:complexType name="BiddableAdGroupCriterion" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:AdGroupCriterion">
      <xs:sequence>
        <xs:element minOccurs="0" name="CriterionBid" nillable="true" type="tns:CriterionBid" />
        <xs:element minOccurs="0" name="DestinationUrl" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="EditorialStatus" nillable="true" type="tns:AdGroupCriterionEditorialStatus" />
        <xs:element minOccurs="0" name="FinalAppUrls" nillable="true" type="q75:ArrayOfAppUrl" xmlns:q75="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" />
        <xs:element minOccurs="0" name="FinalMobileUrls" nillable="true" type="q76:ArrayOfstring" xmlns:q76="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
        <xs:element minOccurs="0" name="FinalUrls" nillable="true" type="q77:ArrayOfstring" xmlns:q77="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
        <xs:element minOccurs="0" name="TrackingUrlTemplate" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="UrlCustomParameters" nillable="true" type="q78:CustomParameters" xmlns:q78="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="criterionbid"></a>CriterionBid|The bid to use in the auction.<br/><br/>**Add:** Requirements vary depending on the type of *Criterion* that is [inherited](#InheritedElements) from the [AdGroupCriterion](../campaign-management/adgroupcriterion.md) object. The bid is optional and will be set to the default of *0* if not included for [AgeCriterion](../campaign-management/agecriterion.md), [DayTimeCriterion](../campaign-management/daytimecriterion.md), [DeviceCriterion](../campaign-management/devicecriterion.md), [GenderCriterion](../campaign-management/gendercriterion.md), [LocationCriterion](../campaign-management/locationcriterion.md), [RadiusCriterion](../campaign-management/radiuscriterion.md), [AudienceCriterion](../campaign-management/audiencecriterion.md), and [Webpage](../campaign-management/webpage.md) criterions. The bid is not applicable for [LocationIntentCriterion](../campaign-management/locationintentcriterion.md) (The service will not return any error and the bid will be ignored even if you include it). When you add a [ProductPartition](../campaign-management/productpartition.md) with the [ApplyProductPartitionActions](../campaign-management/applyproductpartitionactions.md) operation the bid is required unless the product partition type is *Subdivision*, in which case the bid is not allowed.<br/>**Update:** Requirements vary depending on the type of *Criterion* that is [inherited](#InheritedElements) from the [AdGroupCriterion](../campaign-management/adgroupcriterion.md) object. The bid is required for [AgeCriterion](../campaign-management/agecriterion.md), [DayTimeCriterion](../campaign-management/daytimecriterion.md), [DeviceCriterion](../campaign-management/devicecriterion.md), [GenderCriterion](../campaign-management/gendercriterion.md), [LocationCriterion](../campaign-management/locationcriterion.md), and [RadiusCriterion](../campaign-management/radiuscriterion.md). The bid is not applicable for [LocationIntentCriterion](../campaign-management/locationintentcriterion.md) (The service will not return any error and the bid will be ignored even if you include it). For [AudienceCriterion](../campaign-management/audiencecriterion.md) and [Webpage](../campaign-management/webpage.md) criterions the bid is optional, and if no value is specified on update, this Bing Ads setting is not changed. When you update a [ProductPartition](../campaign-management/productpartition.md) with the [ApplyProductPartitionActions](../campaign-management/applyproductpartitionactions.md) operation the bid is optional, and if no value is specified on update, this Bing Ads setting is not changed.|[CriterionBid](criterionbid.md)|
|<a name="destinationurl"></a>DestinationUrl|The URL of the webpage that the user is taken to when they click the ad.<br /><br />This element is only used if the *Criterion* property that is [inherited](#InheritedElements) from the [AdGroupCriterion](../campaign-management/adgroupcriterion.md) object is a [ProductPartition](../campaign-management/productpartition.md) criterion. For details see [ProductPartition Usage](#productpartition) below.|**string**|
|<a name="editorialstatus"></a>EditorialStatus|Reserved for future use.|[AdGroupCriterionEditorialStatus](adgroupcriterioneditorialstatus.md)|
|<a name="finalappurls"></a>FinalAppUrls|Reserved for future use.|[AppUrl](appurl.md) array|
|<a name="finalmobileurls"></a>FinalMobileUrls|Reserved for future use.|**string**|
|<a name="finalurls"></a>FinalUrls|Reserved for future use.|**string**|
|<a name="trackingurltemplate"></a>TrackingUrlTemplate|Tracking templates are where you can specify URL tracking parameters that are used in tandem with your final URL or landing page.<br/><br/> We recommend that you add the tracking template at the account level and then it will be applied to all URLs for lower level entities such as campaigns, ad groups, and ads. To learn more, see the Bing Ads help articles [URL Tracking with Upgraded URLs](~/guides/url-tracking-upgraded-urls.md).<br/><br/>This element is only used if the *Criterion* property that is [inherited](#InheritedElements) from the [AdGroupCriterion](../campaign-management/adgroupcriterion.md) object is either a [ProductPartition](../campaign-management/productpartition.md) or [Webpage](../campaign-management/webpage.md) criterion. For details see [ProductPartition Usage](#productpartition) and [Webpage Usage](#webpage) below.|**string**|
|<a name="urlcustomparameters"></a>UrlCustomParameters|Your custom collection of key and value parameters for URL tracking.<br/><br/>This element is only used if the *Criterion* property that is [inherited](#InheritedElements) from the [AdGroupCriterion](../campaign-management/adgroupcriterion.md) object is either a [ProductPartition](../campaign-management/productpartition.md) or [Webpage](../campaign-management/webpage.md) criterion. For details see [ProductPartition Usage](#productpartition) and [Webpage Usage](#webpage) below.|[CustomParameters](customparameters.md)|

The [BiddableAdGroupCriterion](biddableadgroupcriterion.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsadgroupcriterion"></a>Inherited Elements from AdGroupCriterion
The [BiddableAdGroupCriterion](biddableadgroupcriterion.md) object derives from the [AdGroupCriterion](adgroupcriterion.md) object, and inherits the following elements. The descriptions below are specific to [BiddableAdGroupCriterion](biddableadgroupcriterion.md), and might not apply to other objects that inherit the same elements from the [AdGroupCriterion](adgroupcriterion.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupid"></a>AdGroupId|The identifier of the ad group to apply the criterion to.<br/><br/>**Add:** Required<br/>**Update:** Required|**long**|
|<a name="criterion"></a>Criterion|The criterion to apply to the ad group. The criterion helps determine whether ads in the ad group are served.<br/><br/>For a list of available criterion types, see [AdGroupCriterionType](../campaign-management/adgroupcriteriontype.md).<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|[Criterion](criterion.md)|
|<a name="id"></a>Id|The unique Bing Ads identifier for the ad group criterion.<br/><br/>**Add:** Read-only<br/>**Update:** Required|**long**|
|<a name="status"></a>Status|A status value that determines whether the criterion applies for the ad group.<br/><br/>For most biddable ad group criterions the only supported status value is *Active*. For exceptions, see [Webpage Usage](#webpage) below.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AdGroupCriterionStatus](adgroupcriterionstatus.md)|
|<a name="type"></a>Type|The type of the ad group criterion. This value is *BiddableAdGroupCriterion* when you retrieve a biddable ad group criterion. For more information about ad group criterion types, see the [AdGroupCriterion Data Object Remarks](../campaign-management/adgroupcriterion.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

