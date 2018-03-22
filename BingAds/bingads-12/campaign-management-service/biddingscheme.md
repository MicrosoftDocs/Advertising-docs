---
title: BiddingScheme Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the base object of a bidding scheme for how you want to manage your bids.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# BiddingScheme Data Object - Campaign Management
Defines the base object of a bidding scheme for how you want to manage your bids. A bidding scheme is known as a *bid strategy type* in the Bing Ads web application.

Do not try to instantiate a *BiddingScheme*. You can create one or more following objects that derive from it.
- [EnhancedCpcBiddingScheme](enhancedcpcbiddingscheme.md)
- [InheritFromParentBiddingScheme](inheritfromparentbiddingscheme.md)
- [ManualCpcBiddingScheme](manualcpcbiddingscheme.md) 
- [MaxClicksBiddingScheme](maxclicksbiddingscheme.md)
- [MaxConversionsBiddingScheme](maxconversionsbiddingscheme.md)
- [TargetCpaBiddingScheme](targetcpabiddingscheme.md) 

> [!IMPORTANT]
> If the campaign bid strategy type is set to *MaxClicks*, *MaxConversions*, or *TargetCpa*, the behavior of existing features will change unless you set an individual ad group's or keyword's bid strategy to *ManualCpc*. For more details, see [Budget and Bid Strategies](../guides/budget-bid-strategies.md).
 -  You can continue to set the ad group and keyword bids; however they will not be used by Bing Ads.
 -  Bing Ads will periodically change your stored ad group or keyword bid settings. You can continue to set new bids, however Bing Ads may change them at any type using this bid strategy type.
 -  You can continue to set bid adjustments e.g. for age, gender, or location; however, the multiplier will inform rather than directly modify or override the automated bid. For auto bidding the multiplier is used as a weighted percentage to inform Bing Ads about how much you value the criterion relative to other criteria. For example, a -50% bid multiplier for a mobile device criterion with the Max Conversions bid strategy to indicate that you value conversions from mobile traffic half as much as other device types. The same bid multiplier with the Max Clicks bid strategy would indicate that you value clicks on mobile half as much as other device types. The valid range of values that you can use to inform auto bidding is -100.00 through 30.00.
 -  Whether you chose the *DailyBudgetAccelerated* or *DailyBudgetStandard* budget type, Bing Ads will use the *DailyBudgetStandard* budget type.

Also note that you must have conversion tracking (a UET tag and a conversion goal) set up for the *EnhancedCpc*, *MaxConversions*, and *TargetCpa* bid strategy types to work. See [Universal Event Tracking](../guides/universal-event-tracking.md) for more information.

To set the *MaxConversions* or *TargetCpa* bid strategy types, the campaign must have at least 15 conversions in the last 30 days. If you try to add or update a campaign to use one of these strategy types, the requested operation will fail if there is not enough conversion history. If an active campaign uses one of these bid strategy types, and then ceases to meet the minimum conversion history requirement at any time, Bing Ads will stop auto bidding but will continue to use the *DailyBudgetStandard* budget type. For a new campaign we recommend that you start with *EnhancedCpc* and then when the campaign has enough conversion history, you can update it to use either the *MaxConversions* or *TargetCpa* bid strategy.

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
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[AdGroup](adgroup.md)  
[Campaign](campaign.md)  
[Keyword](keyword.md)  
