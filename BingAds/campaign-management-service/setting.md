---
title: Setting Data Object
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the base class of a setting.
---
# Setting Data Object
Defines the base class of a setting.

Do not try to instantiate a *Setting*. You can create one or more following objects that derive from it.
- [DynamicSearchAdsSetting](../campaign-management-service/dynamicsearchadssetting.md)  
- [ShoppingSetting](../campaign-management-service/shoppingsetting.md)  

## Syntax
```xml
<xs:complexType name="Setting" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Type" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of setting. For more information, see [Remarks](#remarks).|**string**|

## <a name="remarks"></a>Remarks
For Java and the .NET languages, do not set the *Type* element because the value is determined by whether you instantiate a [DynamicSearchAdsSetting](../campaign-management-service/dynamicsearchadssetting.md) or [ShoppingSetting](../campaign-management-service/shoppingsetting.md).

If you generate the SOAP manually, use the *type* attribute of the `<Setting>` node as shown in the following example, to specify that the setting is a shopping setting.

```xml
<Setting i:type="ShoppingSetting">
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[AdGroup](adgroup.md)  
[Campaign](campaign.md)  
