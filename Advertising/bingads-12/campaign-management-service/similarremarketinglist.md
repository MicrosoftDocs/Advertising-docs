---
title: SimilarRemarketingList Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an audience that is similar to one of your remarketing lists.
---
# SimilarRemarketingList Data Object - Campaign Management
Defines an audience that is similar to one of your remarketing lists.

> [!NOTE]
> Microsoft Advertising will automatically generate similar audiences for remarketing lists if you are a pilot participant. You cannot create or edit the similar audience for a remarketing list. Having said that, you can add and delete similar remarketing list associations and exclusions. If you delete the source remarketing list, then the similar audience will also be deleted. If a similar audience is associated with a campaign or ad group, then you cannot delete the source remarketing list. 

## Syntax
```xml
<xs:complexType name="SimilarRemarketingList" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Audience">
      <xs:sequence>
        <xs:element minOccurs="0" name="SourceId" type="xs:long" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="sourceid"></a>SourceId|The Microsoft Advertising identifier of the remarketing list that Microsoft Advertising used to generate this similar audience.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|**long**|

The [SimilarRemarketingList](similarremarketinglist.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsaudience"></a>Inherited Elements from Audience
The [SimilarRemarketingList](similarremarketinglist.md) object derives from the [Audience](audience.md) object, and inherits the following elements. The descriptions below are specific to [SimilarRemarketingList](similarremarketinglist.md), and might not apply to other objects that inherit the same elements from the [Audience](audience.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="audiencenetworksize"></a>AudienceNetworkSize|The total number of people who are active members of this audience in the Audience network. This gives you an idea of how many Audience network users you can target.<br/><br/>The audience needs to have at least 300 people before Microsoft Advertising will use it for optimizations.<br/><br/>The audience network size of a similar audience can differ from the audience network size of the [source](#sourceid) remarketing list.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|**long**|
|<a name="description"></a>Description|This element is not applicable for similar audiences.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|**string**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br/><br/>Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for the *Audience* object.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The Microsoft Advertising identifier of the similar audience.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|**long**|
|<a name="membershipduration"></a>MembershipDuration|This element is not applicable for similar audiences.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|**int**|
|<a name="name"></a>Name|The name of the similar audience is set by Microsoft Advertising. The name can contain a maximum of 128 characters.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|**string**|
|<a name="parentid"></a>ParentId|The Microsoft Advertising identifier of the account or customer. <br/><br/>If the *Scope* is set to *Account*, this is the account ID, and otherwise it is the customer ID.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|**long**|
|<a name="scope"></a>Scope|Scope defines what accounts can use this audience.<br/><br/>The scope of a similar audience is automatically set to the scope of the [source](#sourceid) remarketing list.<br/><br/>If scope is set to *Account*, the audience can only be associated with ad groups within one specified account (*ParentId*). If scope is set to *Customer*, the audience can be associated with any ad groups across all of the customer's accounts.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|[EntityScope](entityscope.md)|
|<a name="searchsize"></a>SearchSize|The total number of people who are active members of this audience in the Search network. This gives you an idea of how many search users you can target.<br/><br/>The audience needs to have at least 1,000 people before Microsoft Advertising will use it for optimizations.<br/><br/>The search size of a similar audience can differ from the search size of the [source](#sourceid) remarketing list.<br/><br/>This property will be nil or empty for up to 24 hours while the [source](#sourceid) remarketing list is being built, for example if you add or update the remarketing list membership duration, rule, or tag identifier of the [source](#sourceid) remarketing list.<br/><br/>This property will be nil or empty if the UET tag associated with the [source](#sourceid) remarketing list has a status of Unverified or Inactive, because the remarketing list can't receive the customer information from your website that it needs to build the list.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|**long**|
|<a name="supportedcampaigntypes"></a>SupportedCampaignTypes|The list of campaign types that support this audience.<br/><br/>Supported values are Audience, DynamicSearchAds, Search, and Shopping. New campaign types might be added in the future, so you should not take any dependency on a fixed set of values.<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|**string** array|
|<a name="type"></a>Type|The type of the audience. This value is *SimilarRemarketingList* when you retrieve a similar audience for remarketing lists. For more information about audience types, see the [Audience Data Object Remarks](audience.md#remarks).<br/><br/>**Add:** Not supported<br/>**Update:** Not supported|[AudienceType](audiencetype.md)|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

