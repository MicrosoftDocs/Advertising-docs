---
title: Setting Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the base class of a setting.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# Setting Data Object - Campaign Management
Defines the base class of a setting.

Do not try to instantiate a *Setting*. You can create one or more following objects that derive from it.

|Setting|Supported Entity|
|-----|-----|
|[DynamicSearchAdsSetting](dynamicsearchadssetting.md)|[Campaign](campaign.md)|
|[ShoppingSetting](shoppingsetting.md)|[Campaign](campaign.md)|
|[TargetSetting](targetsetting.md)|[AdGroup](adgroup.md)| 

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
For Java and the .NET languages, do not set the *Type* element because the value is determined by the type of setting you instantiate.

If you generate the SOAP manually, use the *type* attribute of the `<Setting>` node as shown in the following example, to specify that the setting is a shopping setting.

```xml
<Setting i:type="ShoppingSetting">
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[AdGroup](adgroup.md)  
[Campaign](campaign.md)  
