---
title: NegativeKeyword Data Object
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a negative keyword with match type.
---
# NegativeKeyword Data Object
Defines a negative keyword with match type. A negative keyword can be added and deleted, but cannot be updated.

You may choose to assign negative keywords to an individual campaign or ad group. An assigned set of negative keywords cannot be shared with other campaigns or ad groups.

Negative keywords can also be added and deleted from a shared negative keyword list. The negative keyword list can be shared or associated with multiple campaigns.

> [!NOTE]
> The same negative keyword and match type can be added to all campaigns, ad groups, and negative keyword lists if you choose. Each instance must be added and associated individually and would be assigned a unique negative keyword identifier.

For more information about managing negative keywords and negative keyword lists, please see the technical guide about [Negative Keywords](http://go.microsoft.com/fwlink/?LinkID=691225).

## Syntax
```xml
<xs:complexType name="NegativeKeyword" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:SharedListItem">
      <xs:sequence>
        <xs:element minOccurs="0" name="Id" nillable="true" type="xs:long" />
        <xs:element name="MatchType" type="tns:MatchType" />
        <xs:element name="Text" nillable="true" type="xs:string" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="id"></a>Id|The unique Bing Ads identifier of the negative keyword.<br/><br/>**Add:** Read-only|**long**|
|<a name="matchtype"></a>MatchType|The type of match to compare the negative keyword and the user's search term.<br /><br />The supported values for a negative keyword are Exact and Phrase.<br/><br/>**Add:** Required|[MatchType](matchtype.md)|
|<a name="text"></a>Text|The negative keyword text. The text can contain a maximum of 100 characters.<br/><br/>**Add:** Required|**string**|

The [NegativeKeyword](negativekeyword.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementssharedlistitem"></a>Inherited Elements from SharedListItem
The [NegativeKeyword](negativekeyword.md) object derives from the [SharedListItem](sharedlistitem.md) object, and inherits the following elements. The descriptions below are specific to [NegativeKeyword](negativekeyword.md), and might not apply to other objects that inherit the same elements from the [SharedListItem](sharedlistitem.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br /> Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for the *SharedListItem* object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="type"></a>Type|The type of the shared list item.  This value is *NegativeKeyword* when you retrieve a negative keyword. For more information about shared list item types, see [SharedListItem Data Object Remarks](../campaign-management-service/sharedlistitem.md#remarks).<br/><br/>**Add:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[EntityNegativeKeyword](entitynegativekeyword.md)  
