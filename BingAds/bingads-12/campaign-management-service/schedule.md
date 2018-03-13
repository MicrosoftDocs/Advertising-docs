---
title: Schedule Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the start and end date ranges for ad extension scheduling.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# Schedule Data Object - Campaign Management
Defines the start and end date ranges for ad extension scheduling. 

Use the *StartDate* and *EndDate* elements for calendar level scheduling, and then use *DayTimeRanges* to limit scheduling by day of the week, hour, and minute. 

## Syntax
```xml
<xs:complexType name="Schedule" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="DayTimeRanges" nillable="true" type="tns:ArrayOfDayTime" />
    <xs:element minOccurs="0" name="EndDate" nillable="true" type="tns:Date" />
    <xs:element minOccurs="0" name="StartDate" nillable="true" type="tns:Date" />
    <xs:element minOccurs="0" name="UseSearcherTimeZone" nillable="true" type="xs:boolean" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="daytimeranges"></a>DayTimeRanges|The list of day and time ranges. Each day and time range includes the scheduled day of week, start/end hour, and start/end minute.<br/><br/>**Add:** Optional. If you set this element to null, then ad extensions will be eligible for scheduling anytime during the calendar start and end dates.<br/>**Update:** Optional. The individual [DayTime](daytime.md) objects cannot be updated. You can effectively update the day and time ranges by sending a new list of all [DayTime](daytime.md) settings that should replace the prior set. If you set this element to null, then you are effectively removing all existing day and time ranges.|[DayTime](daytime.md) array|
|<a name="enddate"></a>EndDate|The scheduled end date. <br /><br />The end date is inclusive. For example, if you set *EndDate* to 3/10/2017, the ad extensions will stop being shown at 11:59 PM on 3/10/2017.<br/><br/>**Add:** Optional. If you do not specify an end date, the ad extensions will continue to be delivered unless you pause the associated campaigns, ad groups, or ads.<br/>**Update:** Optional. The end date can be shortened or extended, as long as the start date is either null or occurs before the new end date. If you set the end date to null, then you are effectively removing the end date and the ad extensions will continue to be delivered unless you pause the associated campaigns, ad groups, or ads. |[Date](date.md)|
|<a name="startdate"></a>StartDate|The scheduled start date. <br /><br />The start date is inclusive. For example, if you set *StartDate* to 3/5/2017, the ad extensions will start being shown at 12:00 AM on 3/5/2017.<br/><br/>**Add:** Optional. If you do not specify a start date, the ad extensions are immediately eligible to be scheduled during the day and time ranges.<br/>**Update:** Optional. The start date can be shortened or extended, as long as the end date is either null or occurs after the new start date. If set the start date to null, then you are effectively removing the start date and the ad extensions are immediately eligible to be scheduled during the day and time ranges.|[Date](date.md)|
|<a name="usesearchertimezone"></a>UseSearcherTimeZone|Determines whether to use the account time zone or the time zone of the search user where the ads could be delivered. Set this property to *true* if you want the ad extensions to be shown in the search user's time zone, and otherwise set it to *false*. <br/><br/>**Add:** Optional. If you do not specify this element or leave it null, the default value of *false* will be set and the account time zone will be used. <br/>**Update:** When you update a schedule the existing settings are replaced with the new setting. Thus if you update a schedule and leave this element null, then you are effectively resetting to the default value of *false*. |**boolean**|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[AdExtension](adextension.md)  
[SiteLink](sitelink.md)  
