---
title: CustomParameters Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a collection of key and value custom parameters for URL tracking.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# CustomParameters Data Object - Campaign Management
Defines a collection of key and value custom parameters for URL tracking. Used for campaign, ad group, ad, keyword, sitelink, and ad group criterion URL custom parameters.

## Syntax
```xml
<xs:complexType name="CustomParameters" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element name="Parameters" nillable="true" type="tns:ArrayOfCustomParameter" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="parameters"></a>Parameters|The collection of key and value custom parameters for URL tracking.<br /><br />You can have a maximum of 3 [CustomParameter](customparameter.md) key and value pairs.<br/><br/>**Add:** Required<br/>**Update:** Optional. Once you create this CustomParameters object, the existing custom parameters will be removed or replaced. To remove all existing custom parameters create this CustomParameters object and set the Parameters element to nil. To replace or append to the list of custom parameters, create this CustomParameters object and assign to the Parameters element a new list of [CustomParameter](customparameter.md) objects, including any previous custom parameters that you want to retain. To retain all of the existing custom parameters, set the element that uses this CustomParameters object to nil. For example set the [UrlCustomParameters](expandedtextad.md#urlcustomparameters) element of an [ExpandedTextAd](expandedtextad.md) to nil if you do not want to update any of the custom parameters.[CustomParameter](customparameter.md) array|[CustomParameter](customparameter.md) array|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[Ad](ad.md)  
[AdGroup](adgroup.md)  
[AppAdExtension](appadextension.md)  
[BiddableAdGroupCriterion](biddableadgroupcriterion.md)  
[Campaign](campaign.md)  
[ImageAdExtension](imageadextension.md)  
[Keyword](keyword.md)  
[PriceAdExtension](priceadextension.md)  
[SitelinkAdExtension](sitelinkadextension.md)  
