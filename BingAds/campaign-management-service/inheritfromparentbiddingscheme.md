---
title: InheritFromParentBiddingScheme Data Object
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that represents the inherit from parent bid strategy type.
---
# InheritFromParentBiddingScheme Data Object
Defines an object that represents the inherit from parent bid strategy type.

This is the default bid strategy type for your ad groups and keywords. Use this bid strategy type to inherit the bid strategy type of the respective parent campaign or ad group.

## Syntax
```xml
<xs:complexType name="InheritFromParentBiddingScheme" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:BiddingScheme">
      <xs:sequence>
        <xs:element minOccurs="0" name="InheritedBidStrategyType" nillable="true" type="xs:string">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="inheritedbidstrategytype"></a>InheritedBidStrategyType|The type of bidding scheme (a.k.a. bid strategy type) that is inherited from the parent campaign or ad group. This value is equal to the *Type* element of the campaign or ad group's [BiddingScheme](../campaign-management-service/biddingscheme.md) object. Possible values are *EnhancedCpc*, *ManualCpc*, *MaxClicks*, *MaxConversions*, and *TargetCpa*.<br/><br/> Not everyone has this feature yet. If you don't, don't worry. It's coming soon.<br /><br /> This element is not returned by default. You must include *InheritedBidStrategyType* in the *ReturnAdditionalFields* optional request element when calling [GetAdGroupsByCampaignId](../campaign-management-service/getadgroupsbycampaignid.md), [GetAdGroupsByIds](../campaign-management-service/getadgroupsbyids.md), [GetKeywordsByAdGroupId](../campaign-management-service/getkeywordsbyadgroupid.md), [GetKeywordsByEditorialStatus](../campaign-management-service/getkeywordsbyeditorialstatus.md), and [GetKeywordsByIds](../campaign-management-service/getkeywordsbyids.md).|**string**|

The [InheritFromParentBiddingScheme](inheritfromparentbiddingscheme.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsbiddingscheme"></a>Inherited Elements from BiddingScheme
The [InheritFromParentBiddingScheme](inheritfromparentbiddingscheme.md) object derives from the [BiddingScheme](biddingscheme.md) object, and inherits the following elements. The descriptions below are specific to [InheritFromParentBiddingScheme](inheritfromparentbiddingscheme.md), and might not apply to other objects that inherit the same elements from the [BiddingScheme](biddingscheme.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of the bidding scheme. This value is *InheritFromParentBiddingScheme* when you retrieve an "inherit from parent" bidding scheme. For more information about bidding scheme types, see the [BiddingScheme Data Object Remarks](../campaign-management-service/biddingscheme.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

