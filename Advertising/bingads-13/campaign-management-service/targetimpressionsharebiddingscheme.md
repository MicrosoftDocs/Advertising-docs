---
title: TargetImpressionShareBiddingScheme Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Reserved for future use.
---
# TargetImpressionShareBiddingScheme Data Object - Campaign Management
Reserved for future use.

## Syntax
```xml
<xs:complexType name="TargetImpressionShareBiddingScheme" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:BiddingScheme">
      <xs:sequence>
        <xs:element minOccurs="0" name="MaxCpc" nillable="true" type="tns:Bid" />
        <xs:element minOccurs="0" name="TargetAdPosition" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="TargetImpressionShare" nillable="true" type="xs:double" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [TargetImpressionShareBiddingScheme](targetimpressionsharebiddingscheme.md) object has the following elements: [MaxCpc](#maxcpc), [TargetAdPosition](#targetadposition), [TargetImpressionShare](#targetimpressionshare).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="maxcpc"></a>MaxCpc|Reserved.|[Bid](bid.md)|
|<a name="targetadposition"></a>TargetAdPosition|Reserved.|**string**|
|<a name="targetimpressionshare"></a>TargetImpressionShare|Reserved.|**double**|

The [TargetImpressionShareBiddingScheme](targetimpressionsharebiddingscheme.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsbiddingscheme"></a>Inherited Elements from BiddingScheme
The [TargetImpressionShareBiddingScheme](targetimpressionsharebiddingscheme.md) object derives from the [BiddingScheme](biddingscheme.md) object, and inherits the following elements: [Type](#type). The descriptions below are specific to [TargetImpressionShareBiddingScheme](targetimpressionsharebiddingscheme.md), and might not apply to other objects that inherit the same elements from the [BiddingScheme](biddingscheme.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|Reserved.|**string**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

