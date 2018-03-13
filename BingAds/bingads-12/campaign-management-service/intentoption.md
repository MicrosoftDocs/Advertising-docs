---
title: IntentOption Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible intent options for location criterion, for example to target people in, searching for, or viewing pages about your targeted location.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# IntentOption Value Set - Campaign Management
Defines the possible intent options for location criterion, for example to target people in, searching for, or viewing pages about your targeted location.

## Syntax
```xml
<xs:simpleType name="IntentOption" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:annotation>
    <xs:appinfo>
      <ActualType Name="short" Namespace="http://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
    </xs:appinfo>
  </xs:annotation>
  <xs:restriction base="xs:string">
    <xs:enumeration value="PeopleInOrSearchingForOrViewingPages" />
    <xs:enumeration value="PeopleIn" />
    <xs:enumeration value="PeopleSearchingForOrViewingPages" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="peoplein"></a>PeopleIn|Show ads to people in your targeted location.|
|<a name="peopleinorsearchingfororviewingpages"></a>PeopleInOrSearchingForOrViewingPages|Show ads to people in, searching for, or viewing pages about your targeted location.|
|<a name="peoplesearchingfororviewingpages"></a>PeopleSearchingForOrViewingPages|Show ads to people searching for or viewing pages about your targeted location.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[LocationIntentCriterion](locationintentcriterion.md)  
