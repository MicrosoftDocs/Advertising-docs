---
title: RemarketingList Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a remarketing list.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# RemarketingList Data Object - Campaign Management
Defines a remarketing list.

> [!TIP]
> For an implementation overview, see the [Universal Event Tracking](../guides/universal-event-tracking.md) technical guide.

## Syntax
```xml
<xs:complexType name="RemarketingList" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Audience">
      <xs:sequence>
        <xs:element minOccurs="0" name="Rule" nillable="true" type="tns:RemarketingRule" />
        <xs:element minOccurs="0" name="TagId" nillable="true" type="xs:long" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="rule"></a>Rule|A rule includes conditions used to determine who to add to your remarketing list.<br /><br />You can choose one of the four types of rules to target different audiences: [CustomEventsRule](customeventsrule.md), [PageVisitorsRule](pagevisitorsrule.md), [PageVisitorsWhoDidNotVisitAnotherPageRule](pagevisitorswhodidnotvisitanotherpagerule.md), and [PageVisitorsWhoVisitedAnotherPageRule](pagevisitorswhovisitedanotherpagerule.md).<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.If you want to keep any of the previous rule items, then you must explicitly set them again during update. You can choose to change the type of rule during update.|[RemarketingRule](remarketingrule.md)|
|<a name="tagid"></a>TagId|The Bing Ads identifier of the Universal Event Tracking (UET) tag that is used with the remarketing list.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**long**|

The [RemarketingList](remarketinglist.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsaudience"></a>Inherited Elements from Audience
The [RemarketingList](remarketinglist.md) object derives from the [Audience](audience.md) object, and inherits the following elements. The descriptions below are specific to [RemarketingList](remarketinglist.md), and might not apply to other objects that inherit the same elements from the [Audience](audience.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="description"></a>Description|The description of the audience. Use a description to help you remember what audience you are targeting.<br/><br/>The description can contain a maximum of 1,024 characters.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br /> Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for the *Audience* object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The Bing Ads identifier of the audience.<br/><br/>**Add:** Read-only<br/>**Update:** Required and read-only|**long**|
|<a name="membershipduration"></a>MembershipDuration|When you create an audience, you can specify how far back in time Bing Ads should look for actions that match your audience definition.<br/><br/>The mimimum duration is 1 day and the maximum duration allowed is 180 days.<br/><br/>**Add:** Optional. If not specified, the membership duration will be set to 30 by default.<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**int**|
|<a name="name"></a>Name|The name of the audience. The name can contain a maximum of 128 characters.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="parentid"></a>ParentId|The Bing Ads identifier of the account or customer. <br/><br/>If the *Scope* is set to *Account*, this is the account ID, and otherwise it is the customer ID.<br/><br/>**Add:** Required<br/>**Update:** Read-only. You cannot change the parent ID.|**long**|
|<a name="scope"></a>Scope|Scope defines what accounts can use this audience.<br/><br/> If scope is set to *Account*, the audience can only be associated with ad groups within one specified account (*ParentId*). If scope is set to *Customer*, the audience can be associated with any ad groups across all of the customer's accounts.<br/><br/>**Add:** Required<br/>**Update:** Read-only. You cannot change the scope.|[EntityScope](entityscope.md)|
|<a name="searchsize"></a>SearchSize|The total number of people who belong to this audience. This gives you an idea of how many search users you can target.<br/><br/>This property will be nil or empty if the search audience size is less than 1,000. The audience needs to have at least 1,000 people before Bing Ads will use it for optimizations.<br/><br/>This property will be nil or empty for up to 24 hours while the audience is being built, for example if you add or update the remarketing list membership duration, rule, or tag identifier.<br/><br/>This property will be nil or empty if the UET tag associated with the remarketing list has a status of Unverified or Inactive, because the remarketing list can't receive the customer information from your website that it needs to build the list.<br /><br />**Add:** Read-only<br/>**Update:** Read-only|**long**|
|<a name="type"></a>Type|The type of the audience. This value is *RemarketingList* when you retrieve a remarketing list audience. For more information about audience types, see the [Audience Data Object Remarks](audience.md#remarks).<br /><br />**Add:** Read-only<br/>**Update:** Read-only|[AudienceType](audiencetype.md)|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

