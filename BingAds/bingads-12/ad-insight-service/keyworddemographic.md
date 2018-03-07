---
title: KeywordDemographic Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains the device, age and gender of the user who entered the search query, if known.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# KeywordDemographic Data Object - Ad Insight
Defines an object that contains the device, age and gender of the user who entered the search query, if known.

## Syntax
```xml
<xs:complexType name="KeywordDemographic" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Device" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="EighteenToTwentyFour" type="xs:double" />
    <xs:element minOccurs="0" name="TwentyFiveToThirtyFour" type="xs:double" />
    <xs:element minOccurs="0" name="ThirtyFiveToFourtyNine" type="xs:double" />
    <xs:element minOccurs="0" name="FiftyToSixtyFour" type="xs:double" />
    <xs:element minOccurs="0" name="SixtyFiveAndAbove" type="xs:double" />
    <xs:element minOccurs="0" name="AgeUnknown" type="xs:double" />
    <xs:element minOccurs="0" name="Female" type="xs:double" />
    <xs:element minOccurs="0" name="Male" type="xs:double" />
    <xs:element minOccurs="0" name="GenderUnknown" type="xs:double" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="ageunknown"></a>AgeUnknown|Not used.|**double**|
|<a name="device"></a>Device|The device of the user who entered the search query.|**string**|
|<a name="eighteentotwentyfour"></a>EighteenToTwentyFour|Reserved.|**double**|
|<a name="female"></a>Female|The percentage of time that female users searched for the keyword. The value is specified in the range 0.0 through 1.0.|**double**|
|<a name="fiftytosixtyfour"></a>FiftyToSixtyFour|Reserved.|**double**|
|<a name="genderunknown"></a>GenderUnknown|Not Used.|**double**|
|<a name="male"></a>Male|The percentage of time that male users searched for the keyword. The value is specified in the range 0.0 through 1.0.|**double**|
|<a name="sixtyfiveandabove"></a>SixtyFiveAndAbove|Reserved.|**double**|
|<a name="thirtyfivetofourtynine"></a>ThirtyFiveToFourtyNine|Reserved.|**double**|
|<a name="twentyfivetothirtyfour"></a>TwentyFiveToThirtyFour|Reserved.|**double**|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity  

## Used By
[KeywordDemographicResult](keyworddemographicresult.md)  
