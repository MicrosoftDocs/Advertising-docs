---
title: ConversionGoal Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the base object of a conversion goal.
---
# ConversionGoal Data Object - Campaign Management
Defines the base object of a conversion goal.

Do not try to instantiate a *ConversionGoal*. You can create one or more following objects that derive from it.
- [AppInstallGoal](appinstallgoal.md)
- [DurationGoal](durationgoal.md)
- [EventGoal](eventgoal.md) 
- [InStoreTransactionGoal](instoretransactiongoal.md) 
- [OfflineConversionGoal](offlineconversiongoal.md) 
- [PagesViewedPerVisitGoal](pagesviewedpervisitgoal.md)
- [UrlGoal](urlgoal.md)

## Syntax
```xml
<xs:complexType name="ConversionGoal" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="ConversionWindowInMinutes" nillable="true" type="xs:int" />
    <xs:element minOccurs="0" name="CountType" nillable="true" type="tns:ConversionGoalCountType" />
    <xs:element minOccurs="0" name="Id" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="Name" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Revenue" nillable="true" type="tns:ConversionGoalRevenue" />
    <xs:element minOccurs="0" name="Scope" nillable="true" type="tns:EntityScope" />
    <xs:element minOccurs="0" name="Status" nillable="true" type="tns:ConversionGoalStatus" />
    <xs:element minOccurs="0" name="TagId" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="TrackingStatus" nillable="true" type="tns:ConversionGoalTrackingStatus" />
    <xs:element minOccurs="0" name="Type" nillable="true" type="tns:ConversionGoalType" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="conversionwindowinminutes"></a>ConversionWindowInMinutes|The conversion window is the length of time in minutes after a click that you want to track conversions. If you set this value to 43200 minutes (30 days), then conversions that happen within 30 days after a click are tracked. Past conversions aren't affected. The minimum value supported is 1 minute, although keep in mind that a shorter conversion window will reduce the number of conversions your account records. The maximum value supported is 129600 minutes (90 days).|**int**|
|<a name="counttype"></a>CountType|This determines how your conversions are recorded within your chosen conversion window.<br/><br/>There are two choices, and if you do not set a value the default is *All*:<br/><br/>- *All*:  All conversions that happen after an ad click will be counted. This is a common choice for sales. <br/><br/>-  *Unique*:  Only one conversion that happens after an ad click will be counted. This is a common choice for leads.<br/><br/>For example:  You track two conversions: leads and sales. You pick *Unique* for leads and *All* for sales. When one ad click turns into two leads and two sales, it's counted as three conversions: one for the unique lead, and two for all the sales.<br/><br/>This element is not applicable for the [AppInstallGoal](appinstallgoal.md).|[ConversionGoalCountType](conversiongoalcounttype.md)|
|<a name="id"></a>Id|The unique Microsoft Advertising identifier for the conversion goal.|**long**|
|<a name="name"></a>Name|The conversion goal name.<br/><br/>The maximum length of the name is 100, and the name must be unique among all conversion goals belonging to the same customer.|**string**|
|<a name="revenue"></a>Revenue|Determines how much each conversion is worth to your business.<br/><br/>When adding a conversion goal if you do not specify any revenue tracking preferences, then each [ConversionGoalRevenue](conversiongoalrevenue.md) will be set to their respective default values.<br/><br/>When updating a conversion goal, if the *Revenue* element is nil or empty then none of the nested properties will be updated. However, if this element is not nil or empty then you are effectively replacing any existing revenue properties.<br/><br/>The *VariableValue* option is not available for the [AppInstallGoal](appinstallgoal.md), [DurationGoal](durationgoal.md), or [PagesViewedPerVisitGoal](pagesviewedpervisitgoal.md).|[ConversionGoalRevenue](conversiongoalrevenue.md)|
|<a name="scope"></a>Scope|Determines if the goal applies to all accounts or only the account specified in the required *CustomerAccountId* header element. If you have multiple Microsoft Advertising accounts, you can track conversions across all of those accounts. If you associate a goal with one account, conversions will be tracked for that account only.<br/><br/>Possible values are *Account* and *Customer*.<br/><br/>Once you set scope, you can't change it. If you want to change the scope, you need to create a new conversion goal and pause the old one.<br/><br/>Only the *Customer* scope is supported for the [AppInstallGoal](appinstallgoal.md).|[EntityScope](entityscope.md)|
|<a name="status"></a>Status|Defines the possible user-determined status values of a conversion goal. These are the status values that a user can decide to set, for example a goal can be set to *Paused* if you no longer wish to track conversions for that goal.<br/><br/>For status values that can be set by the system, for example whether or not the UET tag is verified, see the *TrackingStatus* element.|[ConversionGoalStatus](conversiongoalstatus.md)|
|<a name="tagid"></a>TagId|The unique Microsoft Advertising identifier of the UET tag that you added to your website to allow Microsoft Advertising to collect actions people take on your website.<br/><br/>This element is not applicable for the [AppInstallGoal](appinstallgoal.md) and [OfflineConversionGoal](offlineconversiongoal.md).|**long**|
|<a name="trackingstatus"></a>TrackingStatus|Defines the possible system-determined status values of a conversion goal. These are the status values that can be set by the system, for example the system sets the status to *TagUnverified* if the UET tag has not yet been verified.<br/><br/>For status values that a user can decide to set, for example setting the status to *Paused* if you no longer wish to track conversions for that goal, see the *Status* element.<br/><br/>Only the *NoRecentConversions* and *RecordingConversions* statuses are applicable for the [AppInstallGoal](appinstallgoal.md) and [OfflineConversionGoal](offlineconversiongoal.md).|[ConversionGoalTrackingStatus](conversiongoaltrackingstatus.md)|
|<a name="type"></a>Type|The type of the conversion goal. For more information about conversion goal types, see the [Remarks](#remarks).|[ConversionGoalType](conversiongoaltype.md)|

## <a name="remarks"></a>Remarks
For Java and the .NET languages, do not set the *Type* element because the value is determined by which type of conversion goal you instantiate.

If you generate the SOAP manually, use the *type* attribute of the `<ConversionGoal>` node as shown in the following example, to specify the type of the conversion goal.

```xml
<ConversionGoals i:nil="false">
  <ConversionGoal i:type="UrlGoal">
    <ConversionWindowInMinutes i:nil="false"></ConversionWindowInMinutes>
    <CountType i:nil="false">Unique</CountType>
    <Id i:nil="true" />
    <Name i:nil="false">My Url Conversion Goal</Name>
    <Revenue i:nil="false">
      <CurrencyCode i:nil="false">USDollar</CurrencyCode>
      <Type i:nil="false">FixedValue</Type>
      <Value i:nil="false">10.00</Value>
    </Revenue>
    <Scope i:nil="false">Customer</Scope>
    <Status i:nil="true" />
    <TagId i:nil="false"></TagId>
    <TrackingStatus i:nil="true" />
    <UrlExpression i:nil="false">contoso</UrlExpression>
    <UrlOperator i:nil="false">Contains</UrlOperator>
  </ConversionGoal>
</ConversionGoals>
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[AddConversionGoals](addconversiongoals.md)  
[GetConversionGoalsByIds](getconversiongoalsbyids.md)  
[GetConversionGoalsByTagIds](getconversiongoalsbytagids.md)  
[UpdateConversionGoals](updateconversiongoals.md)  
