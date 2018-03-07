---
title: AutoTagType Value Set - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines possible values for an account level setting that determines whether to append or replace the supported UTM tracking codes.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# AutoTagType Value Set - Customer Management
Defines possible values for an account level setting that determines whether to append or replace the supported UTM tracking codes.

Bing Ads can automatically add UTM tags to your destination URL so you can use your website analytics tool, for example Google Analytics, to track how people got to your website. Auto-tags are applied for example to expanded text ads, keywords, Bing Shopping Campaigns, and Sitelink Extensions. For details about auto-tagging, please see the Bing Ads help article [How do I add UTM tags to my landing page URL?](http://help.bingads.microsoft.com/#apex/3/en/56762/-1).

## Syntax
```xml
<xs:simpleType name="AutoTagType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Inactive" />
    <xs:enumeration value="Preserve" />
    <xs:enumeration value="Replace" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="inactive"></a>Inactive|Bing Ads will not append any UTM tracking codes to your ad or keyword final URL.|
|<a name="preserve"></a>Preserve|Bing Ads will automatically append the supported UTM tracking codes, and preserve any existing UTM tracking codes that you added to your ad or keyword's final URL.|
|<a name="replace"></a>Replace|Bing Ads will automatically append the supported UTM tracking codes, and replace any of the existing and supported UTM tracking codes that you added to your ad or keyword's final URL.|

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12  

## Used By
[AdvertiserAccount](advertiseraccount.md)  
