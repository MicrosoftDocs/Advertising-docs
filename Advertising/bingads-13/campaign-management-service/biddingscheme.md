---
title: BiddingScheme Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the base object of a bidding scheme for how you want to manage your bids.
---
# BiddingScheme Data Object - Campaign Management
Defines the base object of a bidding scheme for how you want to manage your bids. A bidding scheme is known as a *bid strategy type* in the Microsoft Advertising web application.

Do not try to instantiate a *BiddingScheme*. You can create one or more following objects that derive from it.
- [EnhancedCpcBiddingScheme](enhancedcpcbiddingscheme.md)
- [InheritFromParentBiddingScheme](inheritfromparentbiddingscheme.md)
- [ManualCpcBiddingScheme](manualcpcbiddingscheme.md) 
- [MaxClicksBiddingScheme](maxclicksbiddingscheme.md)
- [MaxConversionsBiddingScheme](maxconversionsbiddingscheme.md)  
- [TargetCpaBiddingScheme](targetcpabiddingscheme.md) 
- [TargetRoasBiddingScheme](targetroasbiddingscheme.md) 

> [!IMPORTANT] 
> For some bid strategy types your bid and ad rotation settings are ignored and conversion tracking (via [Universal Event Tracking](../guides/universal-event-tracking.md) tag and a conversion goal) is required. For more information including supported locations, see [Let Microsoft Advertising manage your bids with bid strategies](https://help.ads.microsoft.com/#apex/3/en/56786/1). 

> [!TIP] 
> You can set your campaign's bid strategy to EnhancedCpc, MaxClicks, MaxConversions, TargetCpa, or TargetRoas and then, at any time, set an individual ad group's or keyword's bid strategy to ManualCpc.  

## Syntax
```xml
<xs:complexType name="BiddingScheme" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Type" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of bidding scheme that is set for this campaign, ad group, or keyword. <br/><br/>For more information about bidding scheme types, see the [Remarks](#remarks).|**string**|

## <a name="remarks"></a>Remarks
For Java and the .NET languages, do not set the *Type* element because the value is determined by the object instance.

If you generate the SOAP manually, use the *type* attribute of the `<BiddingScheme>` node as shown in the following example.

```xml
<ns1:BiddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
    <ns1:Type xsi:nil="true"/>
</ns1:BiddingScheme>
```

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[AdGroup](adgroup.md)  
[Campaign](campaign.md)  
[Keyword](keyword.md)  
