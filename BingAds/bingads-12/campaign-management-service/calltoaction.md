---
title: CallToAction Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible values for a brief, punchy reason for customers to click your ad right now.
---
# CallToAction Value Set - Campaign Management
Defines the possible values for a brief, punchy reason for customers to click your ad right now.

Each of the values correspond to a friendly and readable call to action in a responsive ad. 

## Syntax
```xml
<xs:simpleType name="CallToAction" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="AddToCart" />
    <xs:enumeration value="ApplyNow" />
    <xs:enumeration value="BookNow" />
    <xs:enumeration value="BookTravel" />
    <xs:enumeration value="Buy" />
    <xs:enumeration value="BuyNow" />
    <xs:enumeration value="ContactUs" />
    <xs:enumeration value="Download" />
    <xs:enumeration value="GetQuote" />
    <xs:enumeration value="Install" />
    <xs:enumeration value="LearnMore" />
    <xs:enumeration value="NoButton" />
    <xs:enumeration value="OpenLink" />
    <xs:enumeration value="OrderNow" />
    <xs:enumeration value="RegisterNow" />
    <xs:enumeration value="SeeMore" />
    <xs:enumeration value="ShopNow" />
    <xs:enumeration value="SignUp" />
    <xs:enumeration value="Subscribe" />
    <xs:enumeration value="Unknown" />
    <xs:enumeration value="VisitSite" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="addtocart"></a>AddToCart|The corresponding call to action in the ad.|
|<a name="applynow"></a>ApplyNow|The corresponding call to action in the ad.|
|<a name="booknow"></a>BookNow|The corresponding call to action in the ad.|
|<a name="booktravel"></a>BookTravel|The corresponding call to action in the ad.|
|<a name="buy"></a>Buy|The corresponding call to action in the ad.|
|<a name="buynow"></a>BuyNow|The corresponding call to action in the ad.|
|<a name="contactus"></a>ContactUs|The corresponding call to action in the ad.|
|<a name="download"></a>Download|The corresponding call to action in the ad.|
|<a name="getquote"></a>GetQuote|The corresponding call to action in the ad.|
|<a name="install"></a>Install|The corresponding call to action in the ad.|
|<a name="learnmore"></a>LearnMore|The corresponding call to action in the ad.|
|<a name="nobutton"></a>NoButton|The corresponding call to action in the ad.|
|<a name="openlink"></a>OpenLink|The corresponding call to action in the ad.|
|<a name="ordernow"></a>OrderNow|The corresponding call to action in the ad.|
|<a name="registernow"></a>RegisterNow|The corresponding call to action in the ad.|
|<a name="seemore"></a>SeeMore|The corresponding call to action in the ad.|
|<a name="shopnow"></a>ShopNow|The corresponding call to action in the ad.|
|<a name="signup"></a>SignUp|The corresponding call to action in the ad.|
|<a name="subscribe"></a>Subscribe|The corresponding call to action in the ad.|
|<a name="unknown"></a>Unknown|The corresponding call to action in the ad.|
|<a name="visitsite"></a>VisitSite|The corresponding call to action in the ad.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[ResponsiveAd](responsivead.md)  
