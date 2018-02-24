---
title: PriceExtensionType Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible types of price ad extensions.
---
# PriceExtensionType Value Set - Campaign Management
Defines the possible types of price ad extensions.

## Syntax
```xml
<xs:simpleType name="PriceExtensionType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Unknown" />
    <xs:enumeration value="Brands" />
    <xs:enumeration value="Events" />
    <xs:enumeration value="Locations" />
    <xs:enumeration value="Neighborhoods" />
    <xs:enumeration value="ProductCategories" />
    <xs:enumeration value="ProductTiers" />
    <xs:enumeration value="Services" />
    <xs:enumeration value="ServiceCategories" />
    <xs:enumeration value="ServiceTiers" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="brands"></a>Brands|The header and description of the [PriceAdExtension](priceadextension.md) are related to brands.|
|<a name="events"></a>Events|The header and description of the [PriceAdExtension](priceadextension.md) are related to events.|
|<a name="locations"></a>Locations|The header and description of the [PriceAdExtension](priceadextension.md) are related to locations.|
|<a name="neighborhoods"></a>Neighborhoods|The header and description of the [PriceAdExtension](priceadextension.md) are related to neighborhoods.|
|<a name="productcategories"></a>ProductCategories|The header and description of the [PriceAdExtension](priceadextension.md) are related to product categories.|
|<a name="producttiers"></a>ProductTiers|The header and description of the [PriceAdExtension](priceadextension.md) are related to product tiers.|
|<a name="servicecategories"></a>ServiceCategories|The header and description of the [PriceAdExtension](priceadextension.md) are related to service categories.|
|<a name="services"></a>Services|The header and description of the [PriceAdExtension](priceadextension.md) are related to services.|
|<a name="servicetiers"></a>ServiceTiers|The header and description of the [PriceAdExtension](priceadextension.md) are related to service tiers.|
|<a name="unknown"></a>Unknown|Reserved for forward compatibility.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[PriceAdExtension](priceadextension.md)  
