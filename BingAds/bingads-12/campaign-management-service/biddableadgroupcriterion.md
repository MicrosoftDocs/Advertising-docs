---
title: BiddableAdGroupCriterion Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a biddable criterion that you want applied to the specified ad group.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# BiddableAdGroupCriterion Data Object - Campaign Management
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
        <xs:element minOccurs="0" name="FinalAppUrls" nillable="true" type="tns:ArrayOfAppUrl" />
        <xs:element minOccurs="0" name="FinalMobileUrls" nillable="true" type="q60:ArrayOfstring" xmlns:q60="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
        <xs:element minOccurs="0" name="FinalUrls" nillable="true" type="q61:ArrayOfstring" xmlns:q61="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
        <xs:element minOccurs="0" name="TrackingUrlTemplate" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="UrlCustomParameters" nillable="true" type="tns:CustomParameters" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="criterionbid"></a>CriterionBid|The bid to use in the auction.<br/><br/>**Add:** Requirements vary depending on the type of *Criterion* that is [inherited](#inheritedelements) from the [AdGroupCriterion](adgroupcriterion.md) object. The bid is optional and will be set to the default of *0* if not included for [AgeCriterion](agecriterion.md), [DayTimeCriterion](daytimecriterion.md), [DeviceCriterion](devicecriterion.md), [GenderCriterion](gendercriterion.md), [LocationCriterion](locationcriterion.md), [RadiusCriterion](radiuscriterion.md), [AudienceCriterion](audiencecriterion.md), and [Webpage](webpage.md) criterions. The bid is not applicable for [LocationIntentCriterion](locationintentcriterion.md) (The service will not return any error and the bid will be ignored even if you include it). When you add a [ProductPartition](productpartition.md) with the [ApplyProductPartitionActions](applyproductpartitionactions.md) operation the bid is required unless the product partition type is *Subdivision*, in which case the bid is not allowed.<br/>**Update:** Requirements vary depending on the type of *Criterion* that is [inherited](#inheritedelements) from the [AdGroupCriterion](adgroupcriterion.md) object. The bid is required for [AgeCriterion](agecriterion.md), [DayTimeCriterion](daytimecriterion.md), [DeviceCriterion](devicecriterion.md), [GenderCriterion](gendercriterion.md), [LocationCriterion](locationcriterion.md), and [RadiusCriterion](radiuscriterion.md). The bid is not applicable for [LocationIntentCriterion](locationintentcriterion.md) (The service will not return any error and the bid will be ignored even if you include it). For [AudienceCriterion](audiencecriterion.md) and [Webpage](webpage.md) criterions the bid is optional, and if no value is specified on update, this Bing Ads setting is not changed. When you update a [ProductPartition](productpartition.md) with the [ApplyProductPartitionActions](applyproductpartitionactions.md) operation the bid is optional, and if no value is specified on update, this Bing Ads setting is not changed.|[CriterionBid](criterionbid.md)|
|<a name="destinationurl"></a>DestinationUrl|The URL of the webpage that the user is taken to when they click the ad.<br /><br />This element is only used if the *Criterion* property that is [inherited](#inheritedelements) from the [AdGroupCriterion](adgroupcriterion.md) object is a [ProductPartition](productpartition.md) criterion. For details see [ProductPartition Usage](#productpartition) below.|**string**|
|<a name="editorialstatus"></a>EditorialStatus|Reserved for future use.|[AdGroupCriterionEditorialStatus](adgroupcriterioneditorialstatus.md)|
|<a name="finalappurls"></a>FinalAppUrls|Reserved for future use.|[AppUrl](appurl.md) array|
|<a name="finalmobileurls"></a>FinalMobileUrls|Reserved for future use.|**string** array|
|<a name="finalurls"></a>FinalUrls|Reserved for future use.|**string** array|
|<a name="trackingurltemplate"></a>TrackingUrlTemplate|Tracking templates are where you can specify URL tracking parameters that are used in tandem with your final URL or landing page.<br/><br/> We recommend that you add the tracking template at the account level and then it will be applied to all URLs for lower level entities such as campaigns, ad groups, and ads. To learn more, see the Bing Ads help articles [URL Tracking with Upgraded URLs](../guides/url-tracking-upgraded-urls.md).<br/><br/>This element is only used if the *Criterion* property that is [inherited](#inheritedelements) from the [AdGroupCriterion](adgroupcriterion.md) object is either a [ProductPartition](productpartition.md) or [Webpage](webpage.md) criterion. For details see [ProductPartition Usage](#productpartition) and [Webpage Usage](#webpage) below.|**string**|
|<a name="urlcustomparameters"></a>UrlCustomParameters|Your custom collection of key and value parameters for URL tracking.<br/><br/>This element is only used if the *Criterion* property that is [inherited](#inheritedelements) from the [AdGroupCriterion](adgroupcriterion.md) object is either a [ProductPartition](productpartition.md) or [Webpage](webpage.md) criterion. For details see [ProductPartition Usage](#productpartition) and [Webpage Usage](#webpage) below.|[CustomParameters](customparameters.md)|

The [BiddableAdGroupCriterion](biddableadgroupcriterion.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsadgroupcriterion"></a>Inherited Elements from AdGroupCriterion
The [BiddableAdGroupCriterion](biddableadgroupcriterion.md) object derives from the [AdGroupCriterion](adgroupcriterion.md) object, and inherits the following elements. The descriptions below are specific to [BiddableAdGroupCriterion](biddableadgroupcriterion.md), and might not apply to other objects that inherit the same elements from the [AdGroupCriterion](adgroupcriterion.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupid"></a>AdGroupId|The identifier of the ad group to apply the criterion to.<br/><br/>**Add:** Required<br/>**Update:** Required|**long**|
|<a name="criterion"></a>Criterion|The criterion to apply to the ad group. The criterion helps determine whether ads in the ad group are served.<br/><br/>For a list of available criterion types, see [AdGroupCriterionType](adgroupcriteriontype.md).<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|[Criterion](criterion.md)|
|<a name="id"></a>Id|The unique Bing Ads identifier for the ad group criterion.<br/><br/>**Add:** Read-only<br/>**Update:** Required|**long**|
|<a name="status"></a>Status|A status value that determines whether the criterion applies for the ad group.<br/><br/>For most biddable ad group criterions the only supported status value is *Active*. For exceptions, see [Webpage Usage](#webpage) below.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AdGroupCriterionStatus](adgroupcriterionstatus.md)|
|<a name="type"></a>Type|The type of the ad group criterion. This value is *BiddableAdGroupCriterion* when you retrieve a biddable ad group criterion. For more information about ad group criterion types, see the [AdGroupCriterion Data Object Remarks](adgroupcriterion.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## <a name="remarks"></a>Remarks
### <a name="productpartition"></a>ProductPartition Usage
If the *Criterion* property that is [inherited](#inheritedelements) from the [AdGroupCriterion](adgroupcriterion.md) object is a [ProductPartition](productpartition.md) criterion, please note the following usage of *BiddableAdGroupCriterion* properties.

#### <a name="productpartition_destinationurl"></a>DestinationUrl
If you are currently using Destination URLs, you must eventually replace them with Tracking Templates. For more information, see [URL Tracking with Upgraded URLs](../guides/url-tracking-upgraded-urls.md).

The URL can contain dynamic parameters such as {MatchType}. For a list of supported parameters, see the Bing Ads help article [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2).

The URL can contain a maximum of 1,024 characters. If the URL does not specify a protocol, the system uses the HTTP protocol when a user clicks the ad. If the URL specifies the HTTP protocol when you add an ad, the service will remove the http:// protocol string (the HTTP protocol string does not count against the 1,024 character limit); however, the service will not remove an HTTPS protocol string (https://) from the URL.

On update, to remove the destination URL, set it to an empty string (*""*). If you leave the element null it will not be updated.

The destination URL is used if specified; otherwise, the destination URL is determined by the corresponding value of the 'Link' that you specified  for the product offer in your Bing Merchant Center catalog.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.  

#### <a name="productpartition_trackingurltemplate"></a>TrackingUrlTemplate
The tracking templates can be used in tandem with the URL specified in the 'Link' field for the product offer that you submitted via the [Content API](/bingads/shopping-content/index). By combining the feed URL with the tracking template, the landing page URL is assembled where a user is directed after clicking the ad. When you use the *TrackingUrlTemplate* element to update the URL parameters instead of updating them in the feed URL, the feed URL doesn't need to go through editorial review and your ads will continue to serve uninterrupted. For example if your product offer URL in the catalog feed is *http://contoso.com/*, you could specify the following tracking template: *{lpurl}?matchtype={matchtype}&device={device}*.

The following validation rules apply to tracking templates. For more details about supported templates and parameters, see the Bing Ads help article [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2)

- Tracking templates defined for lower level entities e.g. ads override those set for higher level entities e.g. campaign. For more information, see [Entity Hierarchy and Limits](../guides/entity-hierarchy-limits.md).

- The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*. 

- Bing Ads does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the landing page URL will include the key and value placeholders of your custom parameters without substitution. For example if your tracking template is for example *http://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}*, and neither *{_season}* or *{_promocode}* are defined at the campaign, ad group, criterion, keyword, or ad level, then the landing page URL will be the same.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.  

#### <a name="productpartition_urlcustomparameters"></a>UrlCustomParameters
You may include up to 3 individual [CustomParameter](customparameter.md) objects within the [CustomParameters](customparameters.md) object. Each [CustomParameter](customparameter.md) contains a *Key* and *Value* element.

On update, set the *UrlCustomParameters* element to null or empty to retain any existing custom parameters. To remove all custom parameters, set the *Parameters* element of the [CustomParameters](customparameters.md) object to null or empty. To remove a subset of custom parameters, specify the custom parameters that you want to keep in the *Parameters* element of the [CustomParameters](customparameters.md) object.

**Add:** Optional  
**Update:** Optional  

### <a name="webpage"></a>Webpage Usage
If the *Criterion* property that is [inherited](#inheritedelements) from the [AdGroupCriterion](adgroupcriterion.md) object is a [Webpage](webpage.md) criterion, please note the following usage of *BiddableAdGroupCriterion* properties.

#### <a name="webpage_status"></a>Status
**Add:** Optional. You can set the status to *Active* or *Paused*. You cannot set the status to *Deleted*.     
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.  

#### <a name="webpage_trackingurltemplate"></a>TrackingUrlTemplate
For [Webpage](webpage.md) criterion the tracking templates can be used in tandem with the landing page URL that is generated dynamically from the domain that you specified for your Dynamic Search Ads campaign. By combining the domain with the tracking template, the landing page URL is assembled where a user is directed after clicking the ad. Here is an example tracking template: *{lpurl}?matchtype={matchtype}&device={device}*.

The following validation rules apply to tracking templates. For more details about supported templates and parameters, see the Bing Ads help article [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2)

- Tracking templates defined for lower level entities e.g. ads override those set for higher level entities e.g. campaign. For more information, see [Entity Hierarchy and Limits](../guides/entity-hierarchy-limits.md).

- The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*. 

- Bing Ads does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the landing page URL will include the key and value placeholders of your custom parameters without substitution. For example if your tracking template is for example *http://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}*, and neither *{_season}* or *{_promocode}* are defined at the campaign, ad group, criterion, keyword, or ad level, then the landing page URL will be the same.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.  

#### <a name="webpage_urlcustomparameters"></a>UrlCustomParameters
You may include up to 3 individual [CustomParameter](customparameter.md) objects within the [CustomParameters](customparameters.md) object. Each [CustomParameter](customparameter.md) contains a *Key* and *Value* element.

On update, set the *UrlCustomParameters* element to null or empty to retain any existing custom parameters. To remove all custom parameters, set the *Parameters* element of the [CustomParameters](customparameters.md) object to null or empty. To remove a subset of custom parameters, specify the custom parameters that you want to keep in the *Parameters* element of the [CustomParameters](customparameters.md) object.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    .

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

