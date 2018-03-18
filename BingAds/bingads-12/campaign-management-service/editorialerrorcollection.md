---
title: EditorialErrorCollection Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a nested list of error object that identifies one of potentially many reasons why an entity failed editorial review.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# EditorialErrorCollection Data Object - Campaign Management
Defines a nested list of error object that identifies one of potentially many reasons why an entity failed editorial review.

## Syntax
```xml
<xs:complexType name="EditorialErrorCollection" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:BatchErrorCollection">
      <xs:sequence>
        <xs:element minOccurs="0" name="Appealable" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="DisapprovedText" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="Location" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="PublisherCountry" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="ReasonCode" type="xs:int" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="appealable"></a>Appealable|Reserved for future use.|**boolean**|
|<a name="disapprovedtext"></a>DisapprovedText|The text that caused the entity to be disapproved.<br /><br />For text length violations, this element specifies the number of characters by which the specified text exceeds the maximum.|**string**|
|<a name="location"></a>Location|The element or property of the entity that caused the entity to be disapproved.|**string**|
|<a name="publishercountry"></a>PublisherCountry|The corresponding country or region for the flagged editorial issue.|**string**|
|<a name="reasoncode"></a>ReasonCode|A numeric code that identifies the error. For more information, see [Editorial Reason Codes](../guides/editorial-failure-reason-codes.md).|**int**|

The [EditorialErrorCollection](editorialerrorcollection.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsbatcherrorcollection"></a>Inherited Elements from BatchErrorCollection
The [EditorialErrorCollection](editorialerrorcollection.md) object derives from the [BatchErrorCollection](batcherrorcollection.md) object, and inherits the following elements. The descriptions below are specific to [EditorialErrorCollection](editorialerrorcollection.md), and might not apply to other objects that inherit the same elements from the [BatchErrorCollection](batcherrorcollection.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="batcherrors"></a>BatchErrors|A list of batch errors corresponding to the nested list index.|[BatchError](batcherror.md) array|
|<a name="code"></a>Code|A numeric error code that identifies the error for the top level list index.|**int**|
|<a name="details"></a>Details|A message that provides additional details about the batch error for the top level list index. This string can be empty.|**string**|
|<a name="errorcode"></a>ErrorCode|A symbolic string constant that identifies the error for the top level list index.|**string**|
|<a name="fieldpath"></a>FieldPath|The name of the data object's element where the error occurred.<br /><br />This value is subject to change, so you should not take a dependency on the current string format.<br /><br />This element is not supported for all errors.|**string**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br /> Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for this data object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="index"></a>Index|The zero-based top level list index in the request message that failed.|**int**|
|<a name="message"></a>Message|A message that describes the error for the top level list index.|**string**|
|<a name="type"></a>Type|Reserved for internal use.|**string**|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

