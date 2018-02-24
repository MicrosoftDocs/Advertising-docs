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
> You cannot add, update, or delete an in-market audience using the Bing Ads API. Having said that, you can add and delete ad group in-market audience associations and exclusions.


> [!NOTE]
> Not everyone has this feature yet. If you don't, don't worry. It's coming soon.

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
|<a name="description"></a>Description|The description of the audience. Use a description to help you remember what audience you are targeting.<br/><br/>The description can contain a maximum of 1,024 characters.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|**string**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br /> Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for the *Audience* object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The Bing Ads identifier of the audience.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|**long**|
|<a name="membershipduration"></a>MembershipDuration|When you create an audience, you can specify how far back in time Bing Ads should look for actions that match your audience definition.<br/><br/>The mimimum duration is 1 day and the maximum duration allowed is 180 days.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|**int**|
|<a name="name"></a>Name|The name of the audience. The name can contain a maximum of 128 characters.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|**string**|
|<a name="parentid"></a>ParentId|The Bing Ads identifier of the customer that contains the in-market audience.<br/><br/>**Add:** Not supported<br/>**Update:**Not supported|**long**|
|<a name="scope"></a>Scope|Scope defines what accounts can use this audience.<br/><br/>For an in-market audience the only supported scope is *Customer*, and the in-market audience can be associated with any ad groups across all of the customer's accounts.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|[EntityScope](entityscope.md)|
|<a name="searchsize"></a>SearchSize|The total number of people who belong to this audience. This gives you an idea of how many search users you can target.<br/><br/>This property will be nil or empty if the search audience size is less than 1,000. The audience needs to have at least 1,000 people before Bing Ads will use it for optimizations.<br /><br />**Add:** Read-only<br/>**Update:** Read-only|**long**|
|<a name="type"></a>Type|The type of the audience. This value is *InMarket* when you retrieve an in-market audience. For more information about audience types, see the [Audience Data Object Remarks](/bingads/campaign-management-service/audience.md#remarks).<br /><br />**Add:** Not supported<br/>**Update:** Not supported|[AudienceType](audiencetype.md)|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

