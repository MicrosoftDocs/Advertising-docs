---
title: PriceQualifier Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines price qualifiers for price ad extensions.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# PriceQualifier Value Set - Campaign Management
Defines price qualifiers for price ad extensions.

## Syntax
```xml
<xs:simpleType name="PriceQualifier" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Unknown" />
    <xs:enumeration value="From" />
    <xs:enumeration value="UpTo" />
    <xs:enumeration value="None" />
    <xs:enumeration value="Average" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="average"></a>Average|The price of the [PriceAdExtension](priceadextension.md) is prefixed with price qualifier text *Average*, for example *Average $9.99*.|
|<a name="from"></a>From|The price of the [PriceAdExtension](priceadextension.md) is prefixed with price qualifier text *From*, for example *From $9.99*.|
|<a name="none"></a>None|The price of the [PriceAdExtension](priceadextension.md) is not prefixed with price qualifier text.|
|<a name="unknown"></a>Unknown|Reserved for forward compatibility.|
|<a name="upto"></a>UpTo|The price of the [PriceAdExtension](priceadextension.md) is prefixed with the price qualifier text *Up to*, for example *Up to $9.99*.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[PriceTableRow](pricetablerow.md)  
