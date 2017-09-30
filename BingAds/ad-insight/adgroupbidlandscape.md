---
title: AdGroupBidLandscape Data Object
ms.service: bing-ads-ad-insight
ms.topic: article
author: eric-urban
ms.author: eur
---
# AdGroupBidLandscape Data Object
Defines an object that contains a list of estimated clicks, cost, and impressions from 1 to 7 days for the ad group identifier given the suggested bid.

> [!NOTE]
> The estimates are not a prediction or guarantee of future performance.

## Syntax
```xml
<xs:complexType name="AdGroupBidLandscape" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AdGroupId" type="xs:long" />
    <xs:element minOccurs="0" name="AdGroupBidLandscapeType" type="tns:AdGroupBidLandscapeType" />
    <xs:element minOccurs="0" name="StartDate" nillable="true" type="tns:DayMonthAndYear" />
    <xs:element minOccurs="0" name="EndDate" nillable="true" type="tns:DayMonthAndYear" />
    <xs:element minOccurs="0" name="BidLandscapePoints" nillable="true" type="tns:ArrayOfBidLandscapePoint" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupid"></a>AdGroupId|The ad group identifier.|**long**|
|<a name="adgroupbidlandscapetype"></a>AdGroupBidLandscapeType|Indicates whether all or a subset of an ad group's existing keywords were used to determine the bid landscape.|[AdGroupBidLandscapeType](adgroupbidlandscapetype.md)|
|<a name="startdate"></a>StartDate|The first date used to calculate the bid landscape. The start date is usually seven days prior to the end date.<br /><br />The difference between the start and end dates could be less than seven if performance data is not available, for example with a new ad group.|[DayMonthAndYear](daymonthandyear.md)|
|<a name="enddate"></a>EndDate|The most recent date used to calculate the bid landscape. The end date should be approximately 2 days prior to today's date when the service is called.|[DayMonthAndYear](daymonthandyear.md)|
|<a name="bidlandscapepoints"></a>BidLandscapePoints|The list of the total estimated clicks, cost, and impressions from *StartDate* to *EndDate* given the suggested bid.|[BidLandscapePoint](bidlandscapepoint.md) array|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity  

## Used By
[GetBidLandscapeByAdGroupIds](getbidlandscapebyadgroupids.md)  
