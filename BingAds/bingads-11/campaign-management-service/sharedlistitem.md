---
title: SharedListItem Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the base class of a shared list item.
---
# SharedListItem Data Object - Campaign Management
Defines the base class of a shared list item.

Do not try to instantiate a *SharedListItem*. You can create the following object that derives from it.
-   [NegativeKeyword](../campaign-management-service/negativekeyword.md)

## Syntax
```xml
<xs:complexType name="SharedListItem" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="ForwardCompatibilityMap" nillable="true" type="q82:ArrayOfKeyValuePairOfstringstring" xmlns:q82="http://schemas.datacontract.org/2004/07/System.Collections.Generic" />
    <xs:element minOccurs="0" name="Type" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br /> Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for the *SharedListItem* object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="type"></a>Type|The type of the shared list item. For more information about shared list item types, see [Remarks](#remarks).<br /><br />**Add:** Read-only<br />**Update:** Read-only|**string**|

## <a name="remarks"></a>Remarks
For Java and the .NET languages, do not set the *Type* element because the value is determined by the object instance.

If you generate the SOAP manually, use the *Type* attribute of the `<SharedListItem>` node as shown in the following example, to specify whether the shared list item is a negative keyword.

```xml
<SharedListItem i:type="-- specify derived type here with the appropriate prefix --">
  <ForwardCompatibilityMap xmlns:e6="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
    <e6:KeyValuePairOfstringstring>
      <e6:key i:nil="false"></e6:key>
      <e6:value i:nil="false"></e6:value>
    </e6:KeyValuePairOfstringstring>
  </ForwardCompatibilityMap>
  <Type i:nil="false"></Type>
  <!--Keep these fields if you set the i:type attribute to NegativeKeyword-->
  <Id i:nil="false"></Id>
  <MatchType></MatchType>
  <Text i:nil="false"></Text>
</SharedListItem>
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[AddListItemsToSharedList](addlistitemstosharedlist.md)  
[AddSharedEntity](addsharedentity.md)  
[GetListItemsBySharedList](getlistitemsbysharedlist.md)  
