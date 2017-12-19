---
title: CustomAudience Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a custom audience.
---
# CustomAudience Data Object - Campaign Management
Defines a custom audience. 

> [!NOTE]
> Only update of the *Description* is supported. You cannot add or delete a custom audience using the Bing Ads API.


> [!NOTE]
> Not everyone has this feature yet. If you don't, don't worry. It's coming soon.

## Syntax
```xml
<xs:complexType name="CustomAudience" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Audience">
      <xs:sequence />
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [CustomAudience](customaudience.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsaudience"></a>Inherited Elements from Audience
The [CustomAudience](customaudience.md) object derives from the [Audience](audience.md) object, and inherits the following elements. The descriptions below are specific to [CustomAudience](customaudience.md), and might not apply to other objects that inherit the same elements from the [Audience](audience.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="description"></a>Description|The description of the audience. Use a description to help you remember what audience you are targeting.<br/><br/>The description can contain a maximum of 1,024 characters.<br/><br/>**Add:** Not supported<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br /> Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for the *Audience* object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The Bing Ads identifier of the audience.<br/><br/>**Add:** Not supported<br/>**Update:** Required and read-only|**long**|
|<a name="membershipduration"></a>MembershipDuration|The membership duration determines how far back in time Bing Ads should look for actions that match your custom audience definition in order to add people to your list. For a custom audience the membership duration is not set in the Bing Ads web application, and Bing Ads defers to your custom audience provider settings.<br/><br/>When you request the custom audience via Bing Ads API, the returned membership duration will be null.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|**int**|
|<a name="name"></a>Name|The name of the audience. The name can contain a maximum of 128 characters.<br/><br/>**Add:** Not supported<br/>**Update:** Read-only|**string**|
|<a name="parentid"></a>ParentId|The Bing Ads identifier of the customer that contains the custom audience.<br/><br/>**Add:** Not supported<br/>**Update:**Not supported|**long**|
|<a name="scope"></a>Scope|Scope defines what accounts can use this audience.<br/><br/>For an custom audience the only supported scope is *Customer*, and the custom audience can be associated with any ad groups across all of the customer's accounts.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|[EntityScope](entityscope.md)|
|<a name="type"></a>Type|The type of the audience. This value is *Custom* when you retrieve a custom audience. For more information about audience types, see the [Audience Data Object Remarks](../campaign-management-service/audience.md#remarks).<br /><br />**Add:** Not supported<br/>**Update:** Read-only|[AudienceType](audiencetype.md)|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

