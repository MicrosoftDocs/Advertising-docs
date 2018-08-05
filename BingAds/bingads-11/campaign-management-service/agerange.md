---
title: AgeRange Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible age range values that you can use to target ads to People.
---
# AgeRange Value Set - Campaign Management
Defines the possible age range values that you can use to target ads to People.

## Syntax
```xml
<xs:simpleType name="AgeRange" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Unknown" />
    <xs:enumeration value="ZeroToSeventeen" />
    <xs:enumeration value="EighteenToTwentyFour" />
    <xs:enumeration value="TwentyFiveToThirtyFour" />
    <xs:enumeration value="ThirtyFiveToFourtyNine" />
    <xs:enumeration value="FiftyToSixtyFour" />
    <xs:enumeration value="SixtyFiveAndAbove" />
    <xs:enumeration value="ThirteenToSeventeen" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="eighteentotwentyfour"></a>EighteenToTwentyFour|People from the ages of 18 through 24 years.|
|<a name="fiftytosixtyfour"></a>FiftyToSixtyFour|People from the ages of 50 through 64 years.|
|<a name="sixtyfiveandabove"></a>SixtyFiveAndAbove|People 65 years of age and older.|
|<a name="thirteentoseventeen"></a>ThirteenToSeventeen|People from the ages of 13 through 17 years.<br/><br/>In many countries, online advertisers are not supposed to target any users less than 18 years old. Bing Ads does not deliver interest-based advertising to children whose birthdate in their Microsoft account identifies them as under 13 years of age. For more information see the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).<br/><br/>Currently people ages 13 to 17 can see your ads, although you cannot adjust the bid for that age range. Soon in Bing Ads you will be enabled to specifically exclude ages 13 to 17. The age range value of *ThirteenToSeventeen* will be supported with negative bid adjustments between -100 and 0. We will announce more specific dates within the next few months.|
|<a name="thirtyfivetofourtynine"></a>ThirtyFiveToFourtyNine|People from the ages of 35 through 49 years.|
|<a name="twentyfivetothirtyfour"></a>TwentyFiveToThirtyFour|People from the ages of 25 through 34 years.|
|<a name="unknown"></a>Unknown|People with unknown ages.<br/><br/>This option is only available for ad groups in Audience campaigns.|
|<a name="zerotoseventeen"></a>ZeroToSeventeen|People 17 years of age and younger.<br/><br/>Reserved for internal use. This value will be removed in a future version of the API.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[AgeCriterion](agecriterion.md)  
