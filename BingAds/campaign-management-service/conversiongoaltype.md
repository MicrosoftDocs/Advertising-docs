---
title: ConversionGoalType Value Set
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the current possible types of conversion goals.
---
# ConversionGoalType Value Set
Defines the current possible types of conversion goals. 

## Syntax
```xml
<xs:simpleType name="ConversionGoalType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="Url" />
        <xs:enumeration value="Duration" />
        <xs:enumeration value="PagesViewedPerVisit" />
        <xs:enumeration value="Event" />
        <xs:enumeration value="AppInstall" />
        <xs:enumeration value="OfflineConversion" />
        <xs:enumeration value="InStoreTransaction" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="appinstall"></a>AppInstall|Refers to an [AppInstallGoal](../campaign-management-service/appinstallgoal.md)|
|<a name="duration"></a>Duration|Refers to a [DurationGoal](../campaign-management-service/durationgoal.md)|
|<a name="event"></a>Event|Refers to an [EventGoal](../campaign-management-service/eventgoal.md)|
|<a name="instoretransaction"></a>InStoreTransaction|Refers to an [InStoreTransactionGoal](../campaign-management-service/instoretransactiongoal.md)|
|<a name="offlineconversion"></a>OfflineConversion|Refers to an [OfflineConversionGoal](../campaign-management-service/offlineconversiongoal.md)|
|<a name="pagesviewedpervisit"></a>PagesViewedPerVisit|Refers to a [PagesViewedPerVisitGoal](../campaign-management-service/pagesviewedpervisitgoal.md)|
|<a name="url"></a>Url|Refers to a [UrlGoal](../campaign-management-service/urlgoal.md)|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[ConversionGoal](conversiongoal.md)  
[GetConversionGoalsByIds](getconversiongoalsbyids.md)  
[GetConversionGoalsByTagIds](getconversiongoalsbytagids.md)  
