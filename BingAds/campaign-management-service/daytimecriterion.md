---
title: DayTimeCriterion Data Object
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a criterion that can be used to show ads to users during a specific day and time range.
---
# DayTimeCriterion Data Object
Defines a criterion that can be used to show ads to users during a specific day and time range.

The *DayTimeCriterion* criterion can be included within [AdGroupCriterion](../campaign-management-service/adgroupcriterion.md) and [CampaignCriterion](../campaign-management-service/campaigncriterion.md) objects. If ad group level day and time criterions are specified, the campaign level day and time criterions are ignored for that ad group. In other words the ad group day and time criterions override the campaign day and time criterions, and are not applied as a union.   

## Syntax
```xml
<xs:complexType name="DayTimeCriterion" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Criterion">
      <xs:sequence>
        <xs:element minOccurs="0" name="Day" nillable="true" type="tns:Day" />
        <xs:element minOccurs="0" name="FromHour" nillable="true" type="xs:int" />
        <xs:element minOccurs="0" name="FromMinute" nillable="true" type="tns:Minute" />
        <xs:element minOccurs="0" name="ToHour" nillable="true" type="xs:int" />
        <xs:element minOccurs="0" name="ToMinute" nillable="true" type="tns:Minute" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="day"></a>Day|The day of the week to target. For example, you can target the ads to run only on Friday or Saturday.<br/><br/>**Add:** Required<br/>**Update:** Not allowed. If you specify this element it must match the existing setting. |[Day](day.md)|
|<a name="fromhour"></a>FromHour|The starting hour range to target.<br/><br/>The possible values range from 0 to 23.<br/><br/>**Add:** Required<br/>**Update:** Not allowed. If you specify this element it must match the existing setting. |**int**|
|<a name="fromminute"></a>FromMinute|The starting minute of the hour to target.<br/><br/>**Add:** Required<br/>**Update:** Not allowed. If you specify this element it must match the existing setting. |[Minute](minute.md)|
|<a name="tohour"></a>ToHour|The ending hour range to target.<br/><br/>The possible values range from 0 to 23.<br/><br/>**Add:** Required<br/>**Update:** Not allowed. If you specify this element it must match the existing setting. |**int**|
|<a name="tominute"></a>ToMinute|The ending minute of the hour to target.<br/><br/>**Add:** Required<br/>**Update:** Not allowed. If you specify this element it must match the existing setting. |[Minute](minute.md)|

The [DayTimeCriterion](daytimecriterion.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementscriterion"></a>Inherited Elements from Criterion
The [DayTimeCriterion](daytimecriterion.md) object derives from the [Criterion](criterion.md) object, and inherits the following elements. The descriptions below are specific to [DayTimeCriterion](daytimecriterion.md), and might not apply to other objects that inherit the same elements from the [Criterion](criterion.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of the criterion. This value is *DayTime* when you retrieve a day and time criterion. For more information about criterion types, see the [Criterion Data Object Remarks](../campaign-management-service/criterion.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

