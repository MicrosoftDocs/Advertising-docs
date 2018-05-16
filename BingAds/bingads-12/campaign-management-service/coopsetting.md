---
title: CoOpSetting Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the ad group level settings for feed-based cooperative bidding campaigns.
---
# CoOpSetting Data Object - Campaign Management
Defines the ad group level settings for feed-based cooperative bidding campaigns.

This setting is only applicable for ad groups in Bing Shopping campaigns.

> [!NOTE]
> Not everyone is enabled for Cooperative bidding yet. If you don't, don't worry. It's coming soon. 

## Syntax
```xml
<xs:complexType name="CoOpSetting" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Setting">
      <xs:sequence>
        <xs:element minOccurs="0" name="BidBoostValue" nillable="true" type="xs:double" />
        <xs:element minOccurs="0" name="BidMaxValue" nillable="true" type="xs:double" />
        <xs:element minOccurs="0" name="BidOption" nillable="true" type="tns:BidOption" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="bidboostvalue"></a>BidBoostValue|The percentage that allows your cooperative bid to flex.<br/><br/>For example, let's say your partner bids $5 USD on a keyword. If your bid boost set to 20 percent and your maximum value is 50 cents, your share would be 50 cents and not $1 USD.|**double**|
|<a name="bidmaxvalue"></a>BidMaxValue|The flat amount of your cooperative bid.|**double**|
|<a name="bidoption"></a>BidOption|Determines whether or not to amplify your partner's bid.<br/><br/>A bid value ad group allows you to bid on products that your merchandising partner doesn't target. A bid boost allows you to amplify your partner's bid.|[BidOption](bidoption.md)|

The [CoOpSetting](coopsetting.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementssetting"></a>Inherited Elements from Setting
The [CoOpSetting](coopsetting.md) object derives from the [Setting](setting.md) object, and inherits the following elements. The descriptions below are specific to [CoOpSetting](coopsetting.md), and might not apply to other objects that inherit the same elements from the [Setting](setting.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of the setting. This value is *CoOp* when you retrieve a cooperative setting. For more information about setting types, see the [Setting Data Object Remarks](setting.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

