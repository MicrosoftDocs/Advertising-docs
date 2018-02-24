---
title: AdGroupCriterionType Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible types of ad group criterions.
---
# AdGroupCriterionType Value Set - Campaign Management
Defines the possible types of ad group criterions.

## Syntax
```xml
<xs:simpleType name="AdGroupCriterionType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="ProductPartition">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">2</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
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
        <xs:enumeration value="Gender">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">32</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="DayTime">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">64</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="Device">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">128</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="Location">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">256</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="LocationIntent">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">512</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="Radius">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1024</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="Audience">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">2048</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="CustomAudience">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">4096</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="InMarketAudience">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">8192</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="RemarketingList">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">16384</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="CompanyName">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">32768</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="JobFunction">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">65536</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="Industry">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">131072</EnumerationValue>
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
|<a name="age"></a>Age|The ad group criterion is an age criterion.<br/><br/>The *Criterion* element of a [BiddableAdGroupCriterion](/bingads/campaign-management-service/biddableadgroupcriterion.md) can be an instance of [AgeCriterion](/bingads/campaign-management-service/agecriterion.md), but age criterion are not supported with [NegativeAdGroupCriterion](/bingads/campaign-management-service/negativeadgroupcriterion.md).<br/><br/>The *CriterionBid* element of a [BiddableAdGroupCriterion](/bingads/campaign-management-service/biddableadgroupcriterion.md) must be an instance of [BidMultiplier](/bingads/campaign-management-service/bidmultiplier.md) when paired with this criterion type.|
|<a name="audience"></a>Audience|The ad group criterion is an audience criterion.<br/><br/>The *Criterion* element of either an [BiddableAdGroupCriterion](/bingads/campaign-management-service/biddableadgroupcriterion.md) or [NegativeAdGroupCriterion](/bingads/campaign-management-service/negativeadgroupcriterion.md) can be an instance of [AudienceCriterion](/bingads/campaign-management-service/audiencecriterion.md). In other words you can include some audiences, and exclude other audiences.<br/><br/>The *CriterionBid* element of a [BiddableAdGroupCriterion](/bingads/campaign-management-service/biddableadgroupcriterion.md) must be an instance of [BidMultiplier](/bingads/campaign-management-service/bidmultiplier.md) when paired with this criterion type.<br/><br/>To add, delete, or update audience criterions i.e., custom audiences, in-market audiences, and remarketing lists, you must specify the *Audience* value. To retrieve these audience criterions via [GetAdGroupCriterionsByIds](/bingads/campaign-management-service/getadgroupcriterionsbyids.md) you must request the specific type i.e., *Custom*, *InMarket*, and *RemarketingList*.|
|<a name="companyname"></a>CompanyName|Reserved.|
|<a name="customaudience"></a>CustomAudience|The ad group criterion is a custom audience association.<br/><br/>This criterion type value is only used by the [GetAdGroupCriterionsByIds](/bingads/campaign-management-service/getadgroupcriterionsbyids.md) operation to request the custom audience associations represented by the [AudienceCriterion](/bingads/campaign-management-service/audiencecriterion.md) objects. To manage the custom audience, see [CustomAudience](/bingads/campaign-management-service/customaudience.md). |
|<a name="daytime"></a>DayTime|The ad group criterion is a day and time criterion.<br/><br/>The *Criterion* element of a [BiddableAdGroupCriterion](/bingads/campaign-management-service/biddableadgroupcriterion.md) can be an instance of [DayTimeCriterion](/bingads/campaign-management-service/daytimecriterion.md), but day and time criterion are not supported with [NegativeAdGroupCriterion](/bingads/campaign-management-service/negativeadgroupcriterion.md).<br/><br/>The *CriterionBid* element of a [BiddableAdGroupCriterion](/bingads/campaign-management-service/biddableadgroupcriterion.md) must be an instance of [BidMultiplier](/bingads/campaign-management-service/bidmultiplier.md) when paired with this criterion type.|
|<a name="device"></a>Device|The ad group criterion is a device criterion.<br/><br/>The *Criterion* element of a [BiddableAdGroupCriterion](/bingads/campaign-management-service/biddableadgroupcriterion.md) can be an instance of [DeviceCriterion](/bingads/campaign-management-service/devicecriterion.md), but device criterion are not supported with [NegativeAdGroupCriterion](/bingads/campaign-management-service/negativeadgroupcriterion.md).<br/><br/>The *CriterionBid* element of a [BiddableAdGroupCriterion](/bingads/campaign-management-service/biddableadgroupcriterion.md) must be an instance of [BidMultiplier](/bingads/campaign-management-service/bidmultiplier.md) when paired with this criterion type.|
|<a name="gender"></a>Gender|The ad group criterion is a gender criterion.<br/><br/>The *Criterion* element of a [BiddableAdGroupCriterion](/bingads/campaign-management-service/biddableadgroupcriterion.md) can be an instance of [GenderCriterion](/bingads/campaign-management-service/gendercriterion.md), but gender criterion are not supported with [NegativeAdGroupCriterion](/bingads/campaign-management-service/negativeadgroupcriterion.md).<br/><br/>The *CriterionBid* element of a [BiddableAdGroupCriterion](/bingads/campaign-management-service/biddableadgroupcriterion.md) must be an instance of [BidMultiplier](/bingads/campaign-management-service/bidmultiplier.md) when paired with this criterion type.|
|<a name="industry"></a>Industry|Reserved.|
|<a name="inmarketaudience"></a>InMarketAudience|The ad group criterion is an in-market audience association.<br/><br/>This criterion type value is only used by the [GetAdGroupCriterionsByIds](/bingads/campaign-management-service/getadgroupcriterionsbyids.md) operation to request the in-market audience associations represented by the [AudienceCriterion](/bingads/campaign-management-service/audiencecriterion.md) objects. To manage the in-market audience, see [InMarketAudience](/bingads/campaign-management-service/inmarketaudience.md). |
|<a name="jobfunction"></a>JobFunction|Reserved.|
|<a name="location"></a>Location|The ad group criterion is a location criterion.<br/><br/>The *Criterion* element of either an [BiddableAdGroupCriterion](/bingads/campaign-management-service/biddableadgroupcriterion.md) or [NegativeAdGroupCriterion](/bingads/campaign-management-service/negativeadgroupcriterion.md) can be an instance of [LocationCriterion](/bingads/campaign-management-service/locationcriterion.md). In other words you can include some locations, and exclude other locations.<br/><br/>The *CriterionBid* element of a [BiddableAdGroupCriterion](/bingads/campaign-management-service/biddableadgroupcriterion.md) must be an instance of [BidMultiplier](/bingads/campaign-management-service/bidmultiplier.md) when paired with this criterion type.|
|<a name="locationintent"></a>LocationIntent|The ad group criterion is a location intent criterion.<br/><br/>The *Criterion* element of a [BiddableAdGroupCriterion](/bingads/campaign-management-service/biddableadgroupcriterion.md) can be an instance of [LocationIntentCriterion](/bingads/campaign-management-service/locationintentcriterion.md), but location intent criterion are not supported with [NegativeAdGroupCriterion](/bingads/campaign-management-service/negativeadgroupcriterion.md).<br/><br/>The *CriterionBid* element of a [BiddableAdGroupCriterion](/bingads/campaign-management-service/biddableadgroupcriterion.md) must be nil or empty when paired with this criterion type.|
|<a name="productpartition"></a>ProductPartition|The ad group criterion is a product partition criterion.<br/><br/>The *Criterion* element of either an [BiddableAdGroupCriterion](/bingads/campaign-management-service/biddableadgroupcriterion.md) or [NegativeAdGroupCriterion](/bingads/campaign-management-service/negativeadgroupcriterion.md) can be an instance of [ProductPartition](/bingads/campaign-management-service/productpartition.md). In other words you can include some product partitions, and exclude other product partitions.<br/><br/>This criterion type is only used with Bing Shopping campaigns.<br/><br/>The *CriterionBid* element of a [BiddableAdGroupCriterion](/bingads/campaign-management-service/biddableadgroupcriterion.md) must be an instance of [FixedBid](/bingads/campaign-management-service/fixedbid.md) when paired with this criterion type.|
|<a name="radius"></a>Radius|The ad group criterion is a radius criterion.<br/><br/>The *Criterion* element of a [BiddableAdGroupCriterion](/bingads/campaign-management-service/biddableadgroupcriterion.md) can be an instance of [RadiusCriterion](/bingads/campaign-management-service/radiuscriterion.md), but radius criterion are not supported with [NegativeAdGroupCriterion](/bingads/campaign-management-service/negativeadgroupcriterion.md).<br/><br/>The *CriterionBid* element of a [BiddableAdGroupCriterion](/bingads/campaign-management-service/biddableadgroupcriterion.md) must be an instance of [BidMultiplier](/bingads/campaign-management-service/bidmultiplier.md) when paired with this criterion type.|
|<a name="remarketinglist"></a>RemarketingList|The ad group criterion is a remarketing list association.<br/><br/>This criterion type value is only used by the [GetAdGroupCriterionsByIds](/bingads/campaign-management-service/getadgroupcriterionsbyids.md) operation to request the remarketing list associations represented by the [AudienceCriterion](/bingads/campaign-management-service/audiencecriterion.md) objects. To manage the remarketing list, see [RemarketingList](/bingads/campaign-management-service/remarketinglist.md).|
|<a name="targets"></a>Targets|Represents one or more [AgeCriterion](/bingads/campaign-management-service/agecriterion.md), [DayTimeCriterion](/bingads/campaign-management-service/daytimecriterion.md), [DeviceCriterion](/bingads/campaign-management-service/devicecriterion.md), [GenderCriterion](/bingads/campaign-management-service/gendercriterion.md), [LocationCriterion](/bingads/campaign-management-service/locationcriterion.md), [LocationIntentCriterion](/bingads/campaign-management-service/locationintentcriterion.md), and [RadiusCriterion](/bingads/campaign-management-service/radiuscriterion.md) objects that can be managed together to show ads based on your target criteria.<br/><br/>To add, delete, or update target criterions i.e., age, day and time, device, gender, location, location intent, and radius criterions, you must specify the *Targets* value. To retrieve these target criterions via [GetAdGroupCriterionsByIds](/bingads/campaign-management-service/getadgroupcriterionsbyids.md) you must request the specific type i.e., *Age*, *DayTime*, *Device*, *Gender*, *Location*, *LocationIntent*, and *Radius*.|
|<a name="webpage"></a>Webpage|The ad group criterion is a webpage criterion.<br/><br/>The *Criterion* element of either an [BiddableAdGroupCriterion](/bingads/campaign-management-service/biddableadgroupcriterion.md) or [NegativeAdGroupCriterion](/bingads/campaign-management-service/negativeadgroupcriterion.md) can be an instance of [Webpage](/bingads/campaign-management-service/webpage.md), but webpage criterion are not supported with [BiddableAdGroupCriterion](/bingads/campaign-management-service/biddableadgroupcriterion.md). In other words you can include some webpages, and exclude other webpages.<br/><br/>This criterion type is only used with Dynamic Search Ads campaigns.<br/><br/>The *CriterionBid* element of a [BiddableAdGroupCriterion](/bingads/campaign-management-service/biddableadgroupcriterion.md) must be an instance of [FixedBid](/bingads/campaign-management-service/fixedbid.md) when paired with this criterion type.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[AddAdGroupCriterions](addadgroupcriterions.md)  
[DeleteAdGroupCriterions](deleteadgroupcriterions.md)  
[GetAdGroupCriterionsByIds](getadgroupcriterionsbyids.md)  
[UpdateAdGroupCriterions](updateadgroupcriterions.md)  
