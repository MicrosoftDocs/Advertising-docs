---
title: EventGoal Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a custom event conversion goal.
---
# EventGoal Data Object - Campaign Management
Defines a custom event conversion goal. Use this type of goal to count every time someone completes a specific action such as, subscribing to newsletter or downloading white paper, as a conversion. 

By default, the UET tag logs user visits to pages on your website that allows Microsoft Advertising to support goal types such as [UrlGoal](urlgoal.md), [DurationGoal](durationgoal.md) and [PagesViewedPerVisitGoal](pagesviewedpervisitgoal.md). However, you may want to track other types of events such as downloading white papers or subscribing to newsletters as conversions. Microsoft Advertising enables this scenario with the *EventGoal*. In addition to creating an *EventGoal*, you must customize your UET tag tracking code to report the values for one or more of the custom event parameters. To learn more, see [How to report custom events with UET](https://help.ads.microsoft.com/#apex/3/en/56684/2). 

> [!TIP]
> For an implementation overview, see the [Universal Event Tracking](../guides/universal-event-tracking.md) technical guide.

> [!IMPORTANT]
> Every time you add or update a new [DurationGoal](durationgoal.md), [EventGoal](eventgoal.md), [OfflineConversionGoal](offlineconversiongoal.md), [PagesViewedPerVisitGoal](pagesviewedpervisitgoal.md) or [UrlGoal](urlgoal.md) via either the Microsoft Advertising web application or Campaign Management API, the *MSCLKIDAutoTaggingEnabled* value of the corresponding [AccountProperty](accountproperty.md) is set to *True* automatically. If the Scope of the goal is set to *Customer* level, then the [AccountProperty](accountproperty.md) for all accounts under the Customer will be set. 

## Syntax
```xml
<xs:complexType name="EventGoal" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:ConversionGoal">
      <xs:sequence>
        <xs:element minOccurs="0" name="ActionExpression" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="ActionOperator" nillable="true" type="tns:ExpressionOperator" />
        <xs:element minOccurs="0" name="CategoryExpression" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="CategoryOperator" nillable="true" type="tns:ExpressionOperator" />
        <xs:element minOccurs="0" name="LabelExpression" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="LabelOperator" nillable="true" type="tns:ExpressionOperator" />
        <xs:element minOccurs="0" name="Value" nillable="true" type="xs:decimal" />
        <xs:element minOccurs="0" name="ValueOperator" nillable="true" type="tns:ValueOperator" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="actionexpression"></a>ActionExpression|The type of user interaction you want to track. For example 'play' or 'pause'.<br/><br/>If this element is specified during an add or update operation, then the *ActionOperator* element is also required.<br/><br/>The string cannot exceed the maximum length of 100.<br/><br/>**Add:** Optional if you include one or more of the other events; You must include one or more of the following event operator pairs: (*ActionOperator* and *ActionExpression*), (*CategoryOperator* and *CategoryExpression*), (*LabelOperator* and *LabelExpression*), (*ValueOperator* and *Value*).<br/>**Update:** Optional if you include one or more of the other events; If you do not include *ActionOperator* and *ActionExpression* during update, any existing *ActionOperator* and *ActionExpression* settings will be deleted.|**string**|
|<a name="actionoperator"></a>ActionOperator|The operator that can be applied to the value of the *ActionExpression* element.<br/><br/>If this element is specified during an add or update operation, then the *ActionExpression* element is also required.<br/><br/>**Add:** Optional if you include one or more of the other events; You must include one or more of the following event operator pairs: (*ActionOperator* and *ActionExpression*), (*CategoryOperator* and *CategoryExpression*), (*LabelOperator* and *LabelExpression*), (*ValueOperator* and *Value*).<br/>**Update:** Optional if you include one or more of the other events; If you do not include *ActionOperator* and *ActionExpression* during update, any existing *ActionOperator* and *ActionExpression* settings will be deleted.|[ExpressionOperator](expressionoperator.md)|
|<a name="categoryexpression"></a>CategoryExpression|The category of event you want to track. For example, 'video'.<br/><br/>If this element is specified during an add or update operation, then the *CategoryOperator* element is also required.<br/><br/>The string cannot exceed the maximum length of 100.<br/><br/>**Add:** Optional if you include one or more of the other events; You must include one or more of the following event operator pairs: (*ActionOperator* and *ActionExpression*), (*CategoryOperator* and *CategoryExpression*), (*LabelOperator* and *LabelExpression*), (*ValueOperator* and *Value*).<br/>**Update:** Optional if you include one or more of the other events; If you do not include *CategoryOperator* and *CategoryExpression* during update, any existing *CategoryOperator* and *CategoryExpression* settings will be deleted.|**string**|
|<a name="categoryoperator"></a>CategoryOperator|The operator that can be applied to the value of the *CategoryExpression* element.<br/><br/>**Add:** Optional if you include one or more of the other events; You must include one or more of the following event operator pairs: (*ActionOperator* and *ActionExpression*), (*CategoryOperator* and *CategoryExpression*), (*LabelOperator* and *LabelExpression*), (*ValueOperator* and *Value*).<br/>**Update:** Optional if you include one or more of the other events; If you do not include *CategoryOperator* and *CategoryExpression* during update, any existing *CategoryOperator* and *CategoryExpression* settings will be deleted.|[ExpressionOperator](expressionoperator.md)|
|<a name="labelexpression"></a>LabelExpression|The name of the element that caused the action. For example 'trailer' or 'behindthescenes'.<br/><br/>If this element is specified during an add or update operation, then the *LabelOperator* element is also required.<br/><br/>The string cannot exceed the maximum length of 100.<br/><br/>**Add:** Optional if you include one or more of the other events; You must include one or more of the following event operator pairs: (*ActionOperator* and *ActionExpression*), (*CategoryOperator* and *CategoryExpression*), (*LabelOperator* and *LabelExpression*), (*ValueOperator* and *Value*).<br/>**Update:** Optional if you include one or more of the other events; If you do not include *LabelOperator* and *LabelExpression* during update, any existing *LabelOperator* and *LabelExpression* settings will be deleted.|**string**|
|<a name="labeloperator"></a>LabelOperator|The operator that can be applied to the value of the *LabelExpression* element.<br/><br/>**Add:** Optional if you include one or more of the other events; You must include one or more of the following event operator pairs: (*ActionOperator* and *ActionExpression*), (*CategoryOperator* and *CategoryExpression*), (*LabelOperator* and *LabelExpression*), (*ValueOperator* and *Value*).<br/>**Update:** Optional if you include one or more of the other events; If you do not include *LabelOperator* and *LabelExpression* during update, any existing *LabelOperator* and *LabelExpression* settings will be deleted.|[ExpressionOperator](expressionoperator.md)|
|<a name="value"></a>Value|A numerical value associated with that event. For example the value could be the duration of time that the video played.<br/><br/>If this element is specified during an add or update operation, then the *ValueOperator* element is also required.<br/><br/>**Add:** Optional if you include one or more of the other events; You must include one or more of the following event operator pairs: (*ActionOperator* and *ActionExpression*), (*CategoryOperator* and *CategoryExpression*), (*LabelOperator* and *LabelExpression*), (*ValueOperator* and *Value*).<br/>**Update:** Optional if you include one or more of the other events; If you do not include *ValueOperator* and *Value* during update, any existing *ValueOperator* and *Value* settings will be deleted|**decimal**|
|<a name="valueoperator"></a>ValueOperator|The operator that can be applied to the value of the *Value* element.<br/><br/>**Add:** Optional if you include one or more of the other events; You must include one or more of the following event operator pairs: (*ActionOperator* and *ActionExpression*), (*CategoryOperator* and *CategoryExpression*), (*LabelOperator* and *LabelExpression*), (*ValueOperator* and *Value*).<br/>**Update:** Optional if you include one or more of the other events; If you do not include *ValueOperator* and *Value* during update, any existing *ValueOperator* and *Value* settings will be deleted.|[ValueOperator](valueoperator.md)|

The [EventGoal](eventgoal.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsconversiongoal"></a>Inherited Elements from ConversionGoal
The [EventGoal](eventgoal.md) object derives from the [ConversionGoal](conversiongoal.md) object, and inherits the following elements. The descriptions below are specific to [EventGoal](eventgoal.md), and might not apply to other objects that inherit the same elements from the [ConversionGoal](conversiongoal.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="conversionwindowinminutes"></a>ConversionWindowInMinutes|The conversion window is the length of time in minutes after a click that you want to track conversions. If you set this value to 43200 minutes (30 days), then conversions that happen within 30 days after a click are tracked. Past conversions aren't affected. The minimum value supported is 1 minute, although keep in mind that a shorter conversion window will reduce the number of conversions your account records. The maximum value supported is 129600 minutes (90 days).<br/><br/>**Add:** Optional<br/>**Update:** Optional|**int**|
|<a name="counttype"></a>CountType|This determines how your conversions are recorded within your chosen conversion window.<br/><br/>There are two choices, and if you do not set a value the default is *All*:<br/><br/>- *All*:  All conversions that happen after an ad click will be counted. This is a common choice for sales. <br/><br/>-  *Unique*:  Only one conversion that happens after an ad click will be counted. This is a common choice for leads.<br/><br/>For example:  You track two conversions: leads and sales. You pick *Unique* for leads and *All* for sales. When one ad click turns into two leads and two sales, it's counted as three conversions: one for the unique lead, and two for all the sales.<br/><br/>**Add:** Optional<br/>**Update:** Optional|[ConversionGoalCountType](conversiongoalcounttype.md)|
|<a name="id"></a>Id|The unique Microsoft Advertising identifier for the conversion goal.<br/><br/>**Add:** Read-only<br/>**Update:** Required and Read-Only|**long**|
|<a name="name"></a>Name|The conversion goal name.<br/><br/>The maximum length of the name is 100, and the name must be unique among all conversion goals belonging to the same customer.|**string**|
|<a name="revenue"></a>Revenue|Determines how much each conversion is worth to your business.<br/><br/>When adding a conversion goal if you do not specify any revenue tracking preferences, then each [ConversionGoalRevenue](conversiongoalrevenue.md) will be set to their respective default values.<br/><br/>When updating a conversion goal, if the *Revenue* element is nil or empty then none of the nested properties will be updated. However, if this element is not nil or empty then you are effectively replacing any existing revenue properties.<br/><br/>**Add:** Optional<br/>**Update:** Optional|[ConversionGoalRevenue](conversiongoalrevenue.md)|
|<a name="scope"></a>Scope|Determines if the goal applies to all accounts or only the account specified in the required *CustomerAccountId* header element. If you have multiple Microsoft Advertising accounts, you can track conversions across all of those accounts. If you associate a goal with one account, conversions will be tracked for that account only.<br/><br/>Possible values are *Account* and *Customer*. If not specified, the scope will be set to *Customer* by default. <br/><br/>Once you set scope, you can't change it. If you want to change the scope, you need to create a new conversion goal and pause the old one.<br/><br/>**Add:** Optional<br/>**Update:** Optional|[EntityScope](entityscope.md)|
|<a name="status"></a>Status|Defines the possible user-determined status values of a conversion goal. These are the status values that a user can decide to set, for example a goal can be set to *Paused* if you no longer wish to track conversions for that goal.<br/><br/>For status values that can be set by the system, for example whether or not the UET tag is verified, see the *TrackingStatus* element.<br/><br/>**Add:** Optional<br/>**Update:** Optional|[ConversionGoalStatus](conversiongoalstatus.md)|
|<a name="tagid"></a>TagId|The unique Microsoft Advertising identifier of the UET tag that you added to your website to allow Microsoft Advertising to collect actions people take on your website.<br/><br/>**Add:** Required<br/>**Update:** Optional|**long**|
|<a name="trackingstatus"></a>TrackingStatus|Defines the possible system-determined status values of a conversion goal. These are the status values that can be set by the system, for example the system sets the status to *TagUnverified* if the UET tag has not yet been verified.<br/><br/>For status values that a user can decide to set, for example setting the status to *Paused* if you no longer wish to track conversions for that goal, see the *Status* element.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[ConversionGoalTrackingStatus](conversiongoaltrackingstatus.md)|
|<a name="type"></a>Type|The type of the conversion goal. This value is *Event* when you retrieve an event goal. For more information about conversion goal types, see the [ConversionGoal Data Object Remarks](conversiongoal.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[ConversionGoalType](conversiongoaltype.md)|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

