---
title: Webpage Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a webpage parameter that contains a list of webpage conditions or criteria that help determine whether you want to show dynamic search ads.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# Webpage Data Object - Campaign Management
Defines a webpage parameter that contains a list of webpage conditions or criteria that help determine whether you want to show dynamic search ads.

The *Webpage* criterion can be included within [BiddableAdGroupCriterion](biddableadgroupcriterion.md), [NegativeAdGroupCriterion](negativeadgroupcriterion.md), and [NegativeCampaignCriterion](negativecampaigncriterion.md) objects. If ad group level negative webpage criterions are specified, the campaign level negative webpage criterions are ignored for that ad group. In other words the ad group negative webpage criterions override the campaign negative webpage criterions, and are not applied as a union.   

> [!NOTE]
> Not everyone has this feature yet. If you don't, don't worry. It's coming soon.

## Syntax
```xml
<xs:complexType name="Webpage" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Criterion">
      <xs:sequence>
        <xs:element minOccurs="0" name="Parameter" nillable="true" type="tns:WebpageParameter" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="parameter"></a>Parameter|The webpage parameter that contains a list of webpage conditions or criteria.<br/><br/>**Add:** Required<br/>**Update:** Optional. You can update the criterion name, but cannot update the webpage conditions. To update the conditions you must delete the criterion and add a new criterion.|[WebpageParameter](webpageparameter.md)|

The [Webpage](webpage.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementscriterion"></a>Inherited Elements from Criterion
The [Webpage](webpage.md) object derives from the [Criterion](criterion.md) object, and inherits the following elements. The descriptions below are specific to [Webpage](webpage.md), and might not apply to other objects that inherit the same elements from the [Criterion](criterion.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of the criterion. This value is *Webpage* when you retrieve a webpage criterion. For more information about criterion types, see the [Criterion Data Object Remarks](criterion.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

