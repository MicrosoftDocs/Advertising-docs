---
title: ConversionGoalCategory Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Reserved.
---
# ConversionGoalCategory Value Set - Campaign Management
Reserved.

## Syntax
```xml
<xs:simpleType name="ConversionGoalCategory" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Unknown" />
    <xs:enumeration value="None" />
    <xs:enumeration value="Purchase" />
    <xs:enumeration value="AddToCart" />
    <xs:enumeration value="BeginCheckout" />
    <xs:enumeration value="Subscribe" />
    <xs:enumeration value="SubmitLeadForm" />
    <xs:enumeration value="BookAppointment" />
    <xs:enumeration value="Signup" />
    <xs:enumeration value="RequestQuote" />
    <xs:enumeration value="GetDirections" />
    <xs:enumeration value="OutboundClick" />
    <xs:enumeration value="Contact" />
    <xs:enumeration value="PageView" />
    <xs:enumeration value="Download" />
    <xs:enumeration value="Other" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

The [ConversionGoalCategory](conversiongoalcategory.md) value set has the following values: [AddToCart](#addtocart), [BeginCheckout](#begincheckout), [BookAppointment](#bookappointment), [Contact](#contact), [Download](#download), [GetDirections](#getdirections), [None](#none), [Other](#other), [OutboundClick](#outboundclick), [PageView](#pageview), [Purchase](#purchase), [RequestQuote](#requestquote), [Signup](#signup), [SubmitLeadForm](#submitleadform), [Subscribe](#subscribe), [Unknown](#unknown).

|Value|Description|
|-----------|---------------|
|<a name="addtocart"></a>AddToCart|Reserved.|
|<a name="begincheckout"></a>BeginCheckout|Reserved.|
|<a name="bookappointment"></a>BookAppointment|Reserved.|
|<a name="contact"></a>Contact|Reserved.|
|<a name="download"></a>Download|Reserved.|
|<a name="getdirections"></a>GetDirections|Reserved.|
|<a name="none"></a>None|Reserved.|
|<a name="other"></a>Other|Reserved.|
|<a name="outboundclick"></a>OutboundClick|Reserved.|
|<a name="pageview"></a>PageView|Reserved.|
|<a name="purchase"></a>Purchase|Reserved.|
|<a name="requestquote"></a>RequestQuote|Reserved.|
|<a name="signup"></a>Signup|Reserved.|
|<a name="submitleadform"></a>SubmitLeadForm|Reserved.|
|<a name="subscribe"></a>Subscribe|Reserved.|
|<a name="unknown"></a>Unknown|Reserved.|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[ConversionGoal](conversiongoal.md)  
