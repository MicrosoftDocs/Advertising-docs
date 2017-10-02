---
title: NegativeKeywordList Data Object
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# NegativeKeywordList Data Object
Defines a negative keyword list. You can add negative keywords to a negative keyword list and associate the list with one or more campaigns.

## Syntax
```xml
<xs:complexType name="NegativeKeywordList" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:SharedList">
      <xs:sequence />
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [NegativeKeywordList](negativekeywordlist.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementssharedlist"></a>Inherited Elements from SharedList
The [NegativeKeywordList](negativekeywordlist.md) object derives from the [SharedList](sharedlist.md) object, and inherits the following elements. The descriptions below are specific to [NegativeKeywordList](negativekeywordlist.md), and might not apply to other objects that inherit the same elements from the [SharedList](sharedlist.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="itemcount"></a>ItemCount|The number of [SharedListItem](../campaign-management/sharedlistitem.md) objects that are added to this shared list.<br /><br />**Add:** Read-only<br />**Update:** Read-only|**int**|

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementssharedentity"></a>Inherited Elements from SharedEntity
The [NegativeKeywordList](negativekeywordlist.md) object derives from the [SharedEntity](sharedentity.md) object, and inherits the following elements. The descriptions below are specific to [NegativeKeywordList](negativekeywordlist.md), and might not apply to other objects that inherit the same elements from the [SharedEntity](sharedentity.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="associationcount"></a>AssociationCount|The number of active associations between this object and an entity such as a campaign.<br /><br />For a [NegativeKeywordList](../campaign-management/negativekeywordlist.md), the maximum association count is 20.<br /><br />**Add:** Read-only<br />**Update:** Read-only|**int**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br />**Note:** Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for the *SharedEntity* object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The unique Bing Ads identifier of the shared entity.<br /><br />**Add:** Read-only<br />**Update:** Required|**long**|
|<a name="name"></a>Name|The name of the shared entity.<br /><br />For a [NegativeKeywordList](../campaign-management/negativekeywordlist.md), the maximum length is 255.<br /><br />**Add:** Optional<br />**Update:** Optional|**string**|
|<a name="type"></a>Type|The type of the shared entity. For more information about shared entity types, see [SharedEntity Data Object Remarks](../campaign-management/sharedentity.md#remarks).<br /><br />**Add:** Read-only<br />**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

