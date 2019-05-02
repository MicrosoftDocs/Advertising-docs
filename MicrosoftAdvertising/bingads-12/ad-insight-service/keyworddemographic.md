---
title: KeywordDemographic Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains the device, age and gender of the user who entered the search query, if known.
---
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
|<a name="eighteentotwentyfour"></a>EighteenToTwentyFour|The percentage of time that users 18 through 24 years of age searched for the keyword. The value is specified in the range 0.0 through 1.0.|**double**|
|<a name="female"></a>Female|The percentage of time that female users searched for the keyword. The value is specified in the range 0.0 through 1.0.|**double**|
|<a name="fiftytosixtyfour"></a>FiftyToSixtyFour|The percentage of time that users 50 through 64 years of age searched for the keyword. The value is specified in the range 0.0 through 1.0.|**double**|
|<a name="genderunknown"></a>GenderUnknown|Not Used.|**double**|
|<a name="male"></a>Male|The percentage of time that male users searched for the keyword. The value is specified in the range 0.0 through 1.0.|**double**|
|<a name="sixtyfiveandabove"></a>SixtyFiveAndAbove|The percentage of time that users 65 years of age or older searched for the keyword. The value is specified in the range 0.0 through 1.0.|**double**|
|<a name="thirtyfivetofourtynine"></a>ThirtyFiveToFourtyNine|The percentage of time that users 35 through 49 years of age searched for the keyword. The value is specified in the range 0.0 through 1.0.|**double**|
|<a name="twentyfivetothirtyfour"></a>TwentyFiveToThirtyFour|The percentage of time that users 25 through 34 years of age searched for the keyword. The value is specified in the range 0.0 through 1.0.|**double**|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity  

## Used By
[KeywordDemographicResult](keyworddemographicresult.md)  
