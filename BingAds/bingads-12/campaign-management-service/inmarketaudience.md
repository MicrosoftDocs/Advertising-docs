---
title: InMarketAudience Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an in-market audience.
---
# InMarketAudience Data Object - Campaign Management
Defines an in-market audience. 

> [!NOTE]
> You cannot add, update, or delete an in-market audience using the Bing Ads API. Having said that, you can add and delete in-market audience associations and exclusions.
> Bing Ads API will always return all currently active in-market audiences. The service does not return deleted in-market audiences, or any delta download to see what changed. 
> You should not take any dependencies on the sandbox in-market audiences. Some in-market audiences are available in sandbox, but not in production. The in-market audience property values can also differ between sandbox and production e.g., the audience name and size. 

> [!NOTE]
> This feature is available only in the United States.

> [!TIP]
> For an overview of in-market audiences see the [About in-market audiences](https://help.ads.microsoft.com/#apex/3/en/56851/-1) help topic.

## Syntax
```xml
<xs:complexType name="InMarketAudience" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Audience">
      <xs:sequence />
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [InMarketAudience](inmarketaudience.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsaudience"></a>Inherited Elements from Audience
The [InMarketAudience](inmarketaudience.md) object derives from the [Audience](audience.md) object, and inherits the following elements. The descriptions below are specific to [InMarketAudience](inmarketaudience.md), and might not apply to other objects that inherit the same elements from the [Audience](audience.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="audiencenetworksize"></a>AudienceNetworkSize|The total number of people who are active members of this audience in the Audience network. This gives you an idea of how many Audience network users you can target.<br/><br/>The audience needs to have at least 300 people before Microsoft Advertising will use it for optimizations.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|**long**|
|<a name="description"></a>Description|The description of the audience. Use a description to help you remember what audience you are targeting.<br/><br/>The description can contain a maximum of 1,024 characters.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|**string**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br/><br/>Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for the *Audience* object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The Microsoft Advertising identifier of the audience.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|**long**|
|<a name="membershipduration"></a>MembershipDuration|When you create an audience, you can specify how far back in time Microsoft Advertising should look for actions that match your audience definition.<br/><br/>The mimimum duration is 1 day and the maximum duration allowed is 180 days.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|**int**|
|<a name="name"></a>Name|The name of the audience. The name can contain a maximum of 128 characters.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|**string**|
|<a name="parentid"></a>ParentId|The Microsoft Advertising identifier of the customer that contains the in-market audience.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|**long**|
|<a name="scope"></a>Scope|Scope defines what accounts can use this audience.<br/><br/>For an in-market audience the only supported scope is *Customer*, and the in-market audience can be associated with any ad groups across all of the customer's accounts.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|[EntityScope](entityscope.md)|
|<a name="searchsize"></a>SearchSize|The total number of people who are active members of this audience in the Search network. This gives you an idea of how many search users you can target.<br/><br/>The audience needs to have at least 1,000 people before Microsoft Advertising will use it for optimizations.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|**long**|
|<a name="supportedcampaigntypes"></a>SupportedCampaignTypes|The list of campaign types that support this audience.<br/><br/>Supported values are Audience, DynamicSearchAds, Search, and Shopping. New campaign types might be added in the future, so you should not take any dependency on a fixed set of values.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|**string** array|
|<a name="type"></a>Type|The type of the audience. This value is *InMarket* when you retrieve an in-market audience. For more information about audience types, see the [Audience Data Object Remarks](audience.md#remarks).<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|[AudienceType](audiencetype.md)|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

