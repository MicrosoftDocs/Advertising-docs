---
title: CampaignCriterionType Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible types of campaign criterions.
---
# CampaignCriterionType Value Set - Campaign Management
Defines the possible types of campaign criterions.

## Syntax
```xml
<xs:simpleType name="CampaignCriterionType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="ProductScope" />
        <xs:enumeration value="Webpage">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">4</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="Targets">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">8</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="Age">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">16</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="DayTime">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">32</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="Gender">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">64</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="Location">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">128</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="Radius">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">256</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="Device">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">512</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="LocationIntent">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1024</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="age"></a>Age|The campaign criterion is an age criterion.<br/><br/>The *Criterion* element of a [CampaignCriterion](campaigncriterion.md) can be an instance of [AgeCriterion](agecriterion.md), but age criterion are not supported with [NegativeCampaignCriterion](negativecampaigncriterion.md).<br/><br/>The *CriterionBid* element of a [BiddableCampaignCriterion](biddablecampaigncriterion.md) must be an instance of [BidMultiplier](bidmultiplier.md) when paired with this criterion type.|
|<a name="daytime"></a>DayTime|The campaign criterion is a day and time criterion.<br/><br/>The *Criterion* element of a [CampaignCriterion](campaigncriterion.md) can be an instance of [DayTimeCriterion](daytimecriterion.md), but day and time criterion are not supported with [NegativeCampaignCriterion](negativecampaigncriterion.md).<br/><br/>The *CriterionBid* element of a [BiddableCampaignCriterion](biddablecampaigncriterion.md) must be an instance of [BidMultiplier](bidmultiplier.md) when paired with this criterion type.|
|<a name="device"></a>Device|The campaign criterion is a device criterion.<br/><br/>The *Criterion* element of a [CampaignCriterion](campaigncriterion.md) can be an instance of [DeviceCriterion](devicecriterion.md), but device criterion are not supported with [NegativeCampaignCriterion](negativecampaigncriterion.md).<br/><br/>The *CriterionBid* element of a [BiddableCampaignCriterion](biddablecampaigncriterion.md) must be an instance of [BidMultiplier](bidmultiplier.md) when paired with this criterion type.|
|<a name="gender"></a>Gender|The campaign criterion is a gender criterion.<br/><br/>The *Criterion* element of a [CampaignCriterion](campaigncriterion.md) can be an instance of [GenderCriterion](gendercriterion.md), but gender criterion are not supported with [NegativeCampaignCriterion](negativecampaigncriterion.md).<br/><br/>The *CriterionBid* element of a [BiddableCampaignCriterion](biddablecampaigncriterion.md) must be an instance of [BidMultiplier](bidmultiplier.md) when paired with this criterion type.|
|<a name="location"></a>Location|The campaign criterion is a location criterion.<br/><br/>The *Criterion* element of either a [CampaignCriterion](campaigncriterion.md) or [NegativeCampaignCriterion](negativecampaigncriterion.md) can be an instance of [LocationCriterion](locationcriterion.md). In other words you can include some locations, and exclude other locations.<br/><br/>The *CriterionBid* element of a [BiddableCampaignCriterion](biddablecampaigncriterion.md) must be an instance of [BidMultiplier](bidmultiplier.md) when paired with this criterion type.|
|<a name="locationintent"></a>LocationIntent|The campaign criterion is a location intent criterion.<br/><br/>The *Criterion* element of a [CampaignCriterion](campaigncriterion.md) can be an instance of [LocationIntentCriterion](locationintentcriterion.md), but location intent criterion are not supported with [NegativeCampaignCriterion](negativecampaigncriterion.md).<br/><br/>The *CriterionBid* element of a [BiddableCampaignCriterion](biddablecampaigncriterion.md) must be nil or empty when paired with this criterion type.|
|<a name="productscope"></a>ProductScope|The campaign criterion is a product scope criterion.<br/><br/>The *Criterion* element of a [CampaignCriterion](campaigncriterion.md) can be an instance of [ProductScope](productscope.md), but product scope criterion are not supported with [NegativeCampaignCriterion](negativecampaigncriterion.md).<br/><br/>This criterion type is only used with Bing Shopping campaigns.<br/><br/>The *CriterionBid* element of a [BiddableCampaignCriterion](biddablecampaigncriterion.md) must be an instance of [FixedBid](fixedbid.md) when paired with this criterion type.|
|<a name="radius"></a>Radius|The campaign criterion is a radius criterion.<br/><br/>The *Criterion* element of a [CampaignCriterion](campaigncriterion.md) can be an instance of [RadiusCriterion](radiuscriterion.md), but radius criterion are not supported with [NegativeCampaignCriterion](negativecampaigncriterion.md).<br/><br/>The *CriterionBid* element of a [BiddableCampaignCriterion](biddablecampaigncriterion.md) must be an instance of [BidMultiplier](bidmultiplier.md) when paired with this criterion type.|
|<a name="targets"></a>Targets|Represents one or more [AgeCriterion](agecriterion.md), [DayTimeCriterion](daytimecriterion.md), [DeviceCriterion](devicecriterion.md), [GenderCriterion](gendercriterion.md), [LocationCriterion](locationcriterion.md), [LocationIntentCriterion](locationintentcriterion.md), and [RadiusCriterion](radiuscriterion.md) objects that can be managed together to show ads based on your target criteria.<br/><br/>To add, delete, or update target criterions i.e., age, day and time, device, gender, location, location intent, and radius criterions, you must specify the *Targets* value. To retrieve these target criterions via [GetCampaignCriterionsByIds](getcampaigncriterionsbyids.md) you must request the specific type i.e., *Age*, *DayTime*, *Device*, *Gender*, *Location*, *LocationIntent*, and *Radius*.|
|<a name="webpage"></a>Webpage|The campaign criterion is a webpage criterion.<br/><br/>The *Criterion* element of a [NegativeCampaignCriterion](negativecampaigncriterion.md) can be an instance of [Webpage](webpage.md), but webpage criterion are not supported with [CampaignCriterion](campaigncriterion.md).<br/><br/>This criterion type is only used with Dynamic Search Ads campaigns.<br/><br/>The *CriterionBid* element of a [BiddableCampaignCriterion](biddablecampaigncriterion.md) must be an instance of [FixedBid](fixedbid.md) when paired with this criterion type.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[AddCampaignCriterions](addcampaigncriterions.md)  
[DeleteCampaignCriterions](deletecampaigncriterions.md)  
[GetCampaignCriterionsByIds](getcampaigncriterionsbyids.md)  
[UpdateCampaignCriterions](updatecampaigncriterions.md)  
