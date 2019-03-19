---
title: CoOpSetting Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the ad group level settings for feed-based cooperative bidding campaigns.
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# CoOpSetting Data Object - Campaign Management
Defines the ad group level settings for feed-based cooperative bidding campaigns.

> [!NOTE]
> This setting is only applicable for ad groups in Bing Shopping campaigns that are setup for Cooperative bidding. Not everyone is enabled for Cooperative bidding yet. If you don't, don't worry. It's coming soon.

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
|<a name="bidboostvalue"></a>BidBoostValue|The percentage (greater than zero) that allows your cooperative bid to flex.<br/><br/>For example, let's say your partner bids $5 USD on a keyword. If your bid boost set to 20 percent and your maximum value is 50 cents, your share would be 50 cents and not $1 USD.<br/><br/>**Add:** Required if the bid option is set to BidBoost, and otherwise you may not set this element.<br/>**Update:** Required if the bid option is set to BidBoost, and otherwise you may not set this element.|**double**|
|<a name="bidmaxvalue"></a>BidMaxValue|The flat amount of your cooperative bid.<br/><br/>**Add:** Required if the bid option is set to BidBoost, and otherwise you may not set this element.<br/>**Update:** Optional if the bid option is set to BidBoost, and otherwise you may not set this element.|**double**|
|<a name="bidoption"></a>BidOption|Determines whether or not to amplify your partner's bid.<br/><br/>A bid value ad group allows you to bid on products that your merchandising partner doesn't target. A bid boost allows you to amplify your partner's bid.<br/><br/>**Add:** If this element is not set, the default Cooperative bidding option for the ad group is "bid value" i.e., the auction will use the fixed bid that you set for each [BiddableAdGroupCriterion](biddableadgroupcriterion.md).<br/>**Update:** Read-only. If you attempt to change the previous bid option an error will be returned.|[BidOption](bidoption.md)|

The [CoOpSetting](coopsetting.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementssetting"></a>Inherited Elements from Setting
The [CoOpSetting](coopsetting.md) object derives from the [Setting](setting.md) object, and inherits the following elements. The descriptions below are specific to [CoOpSetting](coopsetting.md), and might not apply to other objects that inherit the same elements from the [Setting](setting.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of the setting. This value is *CoOp* when you retrieve a cooperative setting. For more information about setting types, see the [Setting Data Object Remarks](setting.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

