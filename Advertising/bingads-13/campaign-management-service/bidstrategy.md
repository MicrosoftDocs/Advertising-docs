---
title: BidStrategy Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the BidStrategy Data Object.
---
# BidStrategy Data Object - Campaign Management
Defines the BidStrategy Data Object.

> [!NOTE]
> This object is reserved for future use. 
> 
> You can set campaign and ad group level bid strategies using the [AddCampaigns](addcampaigns.md)], [UpdateCampaigns](updatecampaigns.md)], [AddAdGroups](addadgroups.md)], and [UpdateAdGroups](updateadgroups.md)] operations. 

## Syntax
```xml
<xs:complexType name="BidStrategy" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AssociatedCampaignType" nillable="true" type="tns:CampaignType" />
    <xs:element minOccurs="0" name="AssociationCount" nillable="true" type="xs:int" />
    <xs:element minOccurs="0" name="BiddingScheme" nillable="true" type="tns:BiddingScheme" />
    <xs:element minOccurs="0" name="Id" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="Name" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [BidStrategy](bidstrategy.md) object has the following elements: [AssociatedCampaignType](#associatedcampaigntype), [AssociationCount](#associationcount), [BiddingScheme](#biddingscheme), [Id](#id), [Name](#name).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="associatedcampaigntype"></a>AssociatedCampaignType|Reserved.|[CampaignType](campaigntype.md)|
|<a name="associationcount"></a>AssociationCount|Reserved.|**int**|
|<a name="biddingscheme"></a>BiddingScheme|Reserved.|[BiddingScheme](biddingscheme.md)|
|<a name="id"></a>Id|Reserved.|**long**|
|<a name="name"></a>Name|Reserved.|**string**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[AddBidStrategies](addbidstrategies.md)  
[GetBidStrategiesByIds](getbidstrategiesbyids.md)  
[UpdateBidStrategies](updatebidstrategies.md)  
