---
title: OfflineConversionGoal Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an offline conversion goal.
---
# OfflineConversionGoal Data Object - Campaign Management
Defines an offline conversion goal. Use this type of goal if you have lead generation as an objective. Lead generation is when potential customers fill out a form or quote of interest, and then the sale is completed offline in person or over the phone (for example, car purchases, insurance quotes, mortgages, etc.).  

To set up offine conversion tracking, create an [OfflineConversionGoal](offlineconversiongoal.md), wait two hours, and then send Bing Ads the [OfflineConversion](offlineconversion.md) data via the [ApplyOfflineConversions](applyofflineconversions.md) operation.

> [!TIP]
> For more information, see [Tracking offline conversions](https://help.bingads.microsoft.com/#apex/3/en/help:app54554/1/en-US/#ext:ConversionTracking_Load).

> [!IMPORTANT]
> Every time you add or update a new [DurationGoal](durationgoal.md), [EventGoal](eventgoal.md), [OfflineConversionGoal](offlineconversiongoal.md), [PagesViewedPerVisitGoal](pagesviewedpervisitgoal.md) or [UrlGoal](urlgoal.md) via either the Bing Ads web application or Campaign Management API, the *MSCLKIDAutoTaggingEnabled* value of the corresponding [AccountProperty](accountproperty.md) is set to *True* automatically. If the Scope of the goal is set to *Customer* level, then the [AccountProperty](accountproperty.md) for all accounts under the Customer will be set. 

## Syntax
```xml
<xs:complexType name="OfflineConversionGoal" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:ConversionGoal">
      <xs:sequence />
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [OfflineConversionGoal](offlineconversiongoal.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsconversiongoal"></a>Inherited Elements from ConversionGoal
The [OfflineConversionGoal](offlineconversiongoal.md) object derives from the [ConversionGoal](conversiongoal.md) object, and inherits the following elements. The descriptions below are specific to [OfflineConversionGoal](offlineconversiongoal.md), and might not apply to other objects that inherit the same elements from the [ConversionGoal](conversiongoal.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="conversionwindowinminutes"></a>ConversionWindowInMinutes|The conversion window is the length of time in minutes after a click that you want to track conversions. If you set this value to 43200 minutes (30 days), then conversions that happen within 30 days after a click are tracked. Past conversions aren't affected. The minimum value supported is 1 minute, although keep in mind that a shorter conversion window will reduce the number of conversions your account records. The maximum value supported is 129600 minutes (90 days).<br/><br/>**Add:** Optional<br/>**Update:** Optional|**int**|
|<a name="counttype"></a>CountType|This determines how your conversions are recorded within your chosen conversion window.<br/><br/>There are two choices, and if you do not set a value the default is *All*:<br/><br/>- *All*:  All conversions with different offline conversion times that happen after an ad click will be counted. This is a common choice for sales. <br/><br/>-  *Unique*:  Only the first conversion that happens after an ad click will be counted. This is a common choice for leads.<br/><br/>For example:  You track two conversions: leads and sales. You pick *Unique* for leads and *All* for sales. When one ad click turns into two leads and two sales, it's counted as three conversions: one for the unique lead, and two for all the sales.<br/><br/> Duplicate offline conversions with the same *MicrosoftClickId* and *ConversionTime* will be ignored. In other words only the first offline conversion for a given *MicrosoftClickId* and *ConversionTime* will be counted.<br/><br/>**Add:** Optional<br/>**Update:** Optional|[ConversionGoalCountType](conversiongoalcounttype.md)|
|<a name="id"></a>Id|The unique Bing Ads identifier for the conversion goal.<br/><br/>**Add:** Read-only<br/>**Update:** Required and Read-Only|**long**|
|<a name="name"></a>Name|The conversion goal name.<br/><br/>The maximum length of the name is 100, and the name must be unique among all conversion goals belonging to the same customer.|**string**|
|<a name="revenue"></a>Revenue|Determines how much each conversion is worth to your business.<br/><br/>When adding a conversion goal if you do not specify any revenue tracking preferences, then each [ConversionGoalRevenue](conversiongoalrevenue.md) will be set to their respective default values.<br/><br/>When updating a conversion goal, if the *Revenue* element is nil or empty then none of the nested properties will be updated. However, if this element is not nil or empty then you are effectively replacing any existing revenue properties.<br/><br/> If the revenue type is *FixedValue* or *VariableValue*, then the *ConversionCurrencyCode* and *ConversionValue* elements of the applied [OfflineConversion](offlineconversion.md) data takes precedence over the [ConversionGoalRevenue](conversiongoalrevenue.md) currency code and value.<br/><br/>**Add:** Optional<br/>**Update:** Optional|[ConversionGoalRevenue](conversiongoalrevenue.md)|
|<a name="scope"></a>Scope|Determines if the goal applies to all accounts or only the account specified in the required *CustomerAccountId* header element. If you have multiple Bing Ads accounts, you can track conversions across all of those accounts. If you associate a goal with one account, conversions will be tracked for that account only.<br/><br/>Possible values are *Account* and *Customer*.<br/><br/>Once you set scope, you can't change it. If you want to change the scope, you need to create a new conversion goal and pause the old one.<br/><br/>**Add:** Optional. If not specified, the scope will be set to *Account* by default.<br/>**Update:** Read-only. You cannot update the offline conversion goal scope.|[EntityScope](entityscope.md)|
|<a name="status"></a>Status|Defines the possible user-determined status values of a conversion goal. These are the status values that a user can decide to set, for example a goal can be set to *Paused* if you no longer wish to track conversions for that goal.<br/><br/>For status values that can be set by the system, see the *TrackingStatus* element.<br/><br/>**Add:** Optional<br/>**Update:** Optional|[ConversionGoalStatus](conversiongoalstatus.md)|
|<a name="tagid"></a>TagId|Not applicable for offline conversion goals.|**long**|
|<a name="trackingstatus"></a>TrackingStatus|Not applicable for offline conversion goals.|[ConversionGoalTrackingStatus](conversiongoaltrackingstatus.md)|
|<a name="type"></a>Type|The type of the conversion goal. This value is *OfflineConversion* when you retrieve an offline conversion goal. For more information about conversion goal types, see the [ConversionGoal Data Object Remarks](conversiongoal.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[ConversionGoalType](conversiongoaltype.md)|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

