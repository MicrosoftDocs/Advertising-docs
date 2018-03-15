---
title: ConversionGoalRevenue Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines properties for revenue that can be tracked by a conversion goal.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# ConversionGoalRevenue Data Object - Campaign Management
Defines properties for revenue that can be tracked by a conversion goal.

## Syntax
```xml
<xs:complexType name="ConversionGoalRevenue" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="CurrencyCode" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Type" nillable="true" type="tns:ConversionGoalRevenueType" />
    <xs:element minOccurs="0" name="Value" nillable="true" type="xs:decimal" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="currencycode"></a>CurrencyCode|The currency type that you want the conversion goal revenue to be reported.<br/><br/>For a list of possible string values see [Bing Ads Currencies](../guides/currencies.md).<br/><br/>For [EventGoal](eventgoal.md), [InStoreTransactionGoal](instoretransactiongoal.md), and [UrlGoal](urlgoal.md) objects, if their *Scope* element is set to *Customer*, this property will be ignored and by default the account level billing currency will be used to report conversion goal revenue. For an [OfflineConversionGoal](offlineconversiongoal.md) if the *Scope* is set to *Customer*, then the currency code must be set.  If the *Scope* element of any [ConversionGoal](conversiongoal.md) is set to *Account* and you do not specify the *CurrencyCode*, then by default the account level billing currency will be used to report conversion goal revenue.<br/><br/> For the [OfflineConversionGoal](offlineconversiongoal.md), the *ConversionCurrencyCode* element of the applied [OfflineConversion](offlineconversion.md) data takes precedence over this currency code.<br/><br/>This element is not available for the [AppInstallGoal](appinstallgoal.md), [DurationGoal](durationgoal.md), or [PagesViewedPerVisitGoal](pagesviewedpervisitgoal.md). You cannot set this property for those goal types.<br/><br/>**Add:** Required. If the *Type* is *NoValue* (the default type), then the currency code is ignored.<br/>**Update:**  Required. If the *Type* is *NoValue* (the default type), then the currency code is ignored.|**string**|
|<a name="type"></a>Type|Determines how revenue is tracked. The possible types are *FixedValue*, *NoValue* (the default type), and *VariableValue*. <br/><br/>If the type is *FixedValue* then you must specify the *Value* element.<br/><br/>If the type is *NoValue* then you must not specify the *Value* element.<br/><br/>If the type is *VariableValue* then you can optionally specify a default value with the *Value* element.|[ConversionGoalRevenueType](conversiongoalrevenuetype.md)|
|<a name="value"></a>Value|The revenue value or amount.  If you assign values to your conversions, you'll be able to see the total value driven by your advertising across different conversions, rather than simply the number of conversions that have happened.<br/><br/>The default value is effectively 0, and possible values range from 0 to 999,9999. Accepted values depend on the revenue type, so please see the *Type* element for details.<br/><br/> For the [OfflineConversionGoal](offlineconversiongoal.md), the *ConversionValue* element of the applied [OfflineConversion](offlineconversion.md) data takes precedence over this currency value.|**decimal**|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[ConversionGoal](conversiongoal.md)  
