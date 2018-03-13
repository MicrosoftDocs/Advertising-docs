---
title: AgeRange Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible age range values that you can use to target ads to People.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# AgeRange Value Set - Campaign Management
Defines the possible age range values that you can use to target ads to People.

## Syntax
```xml
<xs:simpleType name="AgeRange" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Unknown" />
    <xs:enumeration value="EighteenToTwentyFour" />
    <xs:enumeration value="TwentyFiveToThirtyFour" />
    <xs:enumeration value="ThirtyFiveToFourtyNine" />
    <xs:enumeration value="FiftyToSixtyFour" />
    <xs:enumeration value="SixtyFiveAndAbove" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="eighteentotwentyfour"></a>EighteenToTwentyFour|People from the ages of 18 through 24 years.|
|<a name="fiftytosixtyfour"></a>FiftyToSixtyFour|People from the ages of 50 through 64 years.|
|<a name="sixtyfiveandabove"></a>SixtyFiveAndAbove|People 65 years of age and older.|
|<a name="thirtyfivetofourtynine"></a>ThirtyFiveToFourtyNine|People from the ages of 35 through 49 years.|
|<a name="twentyfivetothirtyfour"></a>TwentyFiveToThirtyFour|People from the ages of 25 through 34 years.|
|<a name="unknown"></a>Unknown|Reserved.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[AgeCriterion](agecriterion.md)  
