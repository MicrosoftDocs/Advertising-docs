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
|<a name="parameters"></a>Parameters|The collection of key and value custom parameters for URL tracking.<br /><br />You can have a maximum of 3 [CustomParameter](customparameter.md) key and value pairs.<br/><br/>**Add:** Required<br/>**Update:** Optional|[CustomParameter](customparameter.md) array|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V12  

## Used By
[Ad](ad.md)  
[AdGroup](adgroup.md)  
[AppAdExtension](appadextension.md)  
[BiddableAdGroupCriterion](biddableadgroupcriterion.md)  
[Campaign](campaign.md)  
[ImageAdExtension](imageadextension.md)  
[Keyword](keyword.md)  
[PriceAdExtension](priceadextension.md)  
[SiteLink](sitelink.md)  
[Sitelink2AdExtension](sitelink2adextension.md)  
